<template>
  <section class="rule-section">
    <div class="page-header">
      <h1 class="page-title">PDF工具页面</h1>
      <p class="page-description">支持pdf对ppt、word、图片等处理</p>
    </div>
    <div class="rule-content">
      <div class="rule-sidebar">
        <div class="sidebar-menu">
          <h3>功能导航</h3>
          <ul>
            <li
              class="sidebar-item active"
              data-tab="recording"
              @click="switchTab('recording')"
            >
              代码生成
            </li>
            <li
              class="sidebar-item"
              data-tab="management"
              @click="switchTab('management')"
            >
              规则检索
            </li>
            <li
              class="sidebar-item"
              data-tab="variables"
              @click="switchTab('variables')"
            >
              工具方法检索
            </li>
          </ul>
        </div>
      </div>

      <div class="main-content">
        <!-- <FontDecration>操作步骤如下：</FontDecration> -->

        <!-- 首页步骤 -->
        <div class="recordSteps ruleIndex">
          <h3>✅ 规则代码生成</h3>
          <ul>
            <li>
              1. 进入晓阳AI对话模块，点击卡片，选择“规则代码生成”。
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              2.
              在已有模板中，用户可以通过输入特定的规则描述，自动生成相应的规则代码。
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              3. 这是生成的代码，可以直接插入使用
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
          <p></p>
        </div>

        <!-- 录制脚本步骤 -->
        <div class="recordSteps autoRecord">
          <h3>✅ 如何规则检索</h3>
          <ul>
            <li>
              1.
              在对话框中输入规则描述，点击“规则检索”按钮，系统会根据描述进行规则检索。
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              2. 用户可以搜索已有的规则，快速找到所需的信息。
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 添加脚本步骤 -->
        <div class="recordSteps autoAdd">
          <h3>✅ 规则工具方法检索</h3>
          <ul>
            <li>
              1. 用户可以查找和使用各种规则工具方法，提高工作效率。
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
// import FontDecration from '@/components/FontDecration.vue'

export default {
  name: 'RulesSection',
  components: {
    // FontDecration
  },
  mounted() {
    this.setupScrollSpy()
  },
  methods: {
    // 切换标签
    switchTab(tab) {
      this.activeTab = tab

      // 更新菜单激活状态
      const menuItems = document.querySelectorAll('.sidebar-item')
      menuItems.forEach((item) => {
        item.classList.remove('active')
        if (item.getAttribute('data-tab') === tab) {
          item.classList.add('active')
        }
      })

      // 滚动到对应区域
      const sectionMap = {
        recording: 'ruleIndex',
        management: 'autoRecord',
        variables: 'autoAdd',
        plugins: 'autoEdit'
      }
      const targetSection = document.querySelector(`.${sectionMap[tab]}`)
      if (targetSection) {
        targetSection.scrollIntoView({ behavior: 'smooth' })
      }
    },
    // 设置滚动监听
    setupScrollSpy() {
      const sections = document.querySelectorAll('.recordSteps')
      const menuItems = document.querySelectorAll('.sidebar-item')

      // 滚动监听
      window.addEventListener('scroll', () => {
        let current = ''
        let maxVisibility = 0

        sections.forEach((section) => {
          const sectionTop = section.offsetTop
          const sectionHeight = section.clientHeight
          const sectionBottom = sectionTop + sectionHeight

          // 计算当前区域的可见比例
          const viewportHeight = window.innerHeight
          // const visibleTop = Math.max(0, sectionTop - pageYOffset)
          const visibleBottom =
            Math.min(sectionBottom, pageYOffset + viewportHeight) - sectionTop
          const visibility = visibleBottom / sectionHeight

          if (visibility > maxVisibility) {
            maxVisibility = visibility
            current = section.className.split(' ')[1]
          }
        })

        // 更新菜单高亮状态
        menuItems.forEach((item) => {
          item.classList.remove('active')
          if (
            item.getAttribute('data-tab') === this.getTabFromSection(current)
          ) {
            item.classList.add('active')
          }
        })
      })

      // 初始加载时设置第一个为激活状态
      if (menuItems.length > 0) {
        menuItems[0].classList.add('active')
      }
    },
    // 根据区域类名获取对应的标签
    getTabFromSection(sectionClass) {
      const sectionToTabMap = {
        ruleIndex: 'recording',
        autoRecord: 'management',
        autoAdd: 'variables',
        autoEdit: 'plugins'
      }
      return sectionToTabMap[sectionClass] || 'recording'
    }
  }
}
</script>
<style scoped>
/* 页面标题 */
.page-header {
  margin-bottom: 32px;
}
.page-header h1 {
  font-size: 28px;
  margin-bottom: 8px;
  color: #1f2937;
}

.page-description {
  color: #6b7280;
  font-size: 16px;
}

.rule-content {
  display: flex;
  flex: 1;
  gap: 24px;
  overflow: hidden;
  background-color: white;
  border-radius: 16px;
}

.rule-sidebar {
  width: 240px;
  flex-shrink: 0;
  position: sticky;
  top: 0;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 24px;
  padding: 24px;
  overflow-y: hidden;
  border-right: 1px solid #eeeef0;
}

.sidebar-menu h3 {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 12px;
  color: #374151;
  margin-bottom: 14px;
}

.sidebar-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.sidebar-item {
  padding: 10px 16px;
  margin-bottom: 4px;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.sidebar-item:hover {
  background-color: #f3f4f6;
}

.sidebar-item.active {
  background-color: #eff6ff;
  color: #2563eb;
  font-weight: 500;
}

.main-content {
  padding: 30px 0;
  flex: 1;
  display: flex;
  flex-direction: column;
  overflow-y: auto;
  height: 100%;
  /* 隐藏滚动条但保持滚动功能 */
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE and Edge */
}
/* 隐藏Webkit浏览器的滚动条 */
.main-content::-webkit-scrollbar {
  display: none;
}

.recordSteps {
  padding: 16px;
  /* 隐藏滚动条但保持滚动功能 */
  scrollbar-width: none;
  -ms-overflow-style: none;
}

.tip-box {
  background-color: #fffbeb;
  border-left: 4px solid #f59e0b;
  padding: 12px 16px;
  margin: 16px 0;
  border-radius: 4px;
  display: flex;
  align-items: center;
}

.tip-icon {
  font-weight: bold;
  color: #d97706;
  margin-right: 8px;
}

.tip-content {
  color: #92400e;
  line-height: 1.5;
}

.recordSteps li {
  padding: 8px 24px;
  list-style: none;
}

.imgStyle {
  margin: 16px 6px;
  width: 80px;
}

.imgStyle img {
  width: 260%;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

/* 自定义滚动条 */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f5f9;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: #cbd5e1;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #94a3b8;
}

/* 脚本自动化页面样式 */
.rule-section {
  display: flex;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
  height: 100%;
}
</style>
