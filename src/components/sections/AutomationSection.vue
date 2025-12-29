<template>
  <section class="automation-section">
    <div class="page-header">
      <h1 class="page-title">脚本自动化</h1>
      <p class="page-description">
        通过录制和执行脚本，实现重复性工作的自动化，提高工作效率
      </p>
    </div>

    <div class="automation-content">
      <div class="automation-sidebar">
        <div class="sidebar-menu">
          <h3>功能导航</h3>
          <ul>
            <li
              class="sidebar-item active"
              data-tab="layout"
              @click="switchTab('layout')"
            >
              布局介绍
            </li>
            <li
              class="sidebar-item"
              data-tab="recording"
              @click="switchTab('recording')"
            >
              登录 & 首页
            </li>
            <li
              class="sidebar-item"
              data-tab="management"
              @click="switchTab('management')"
            >
              录制脚本
            </li>
            <li
              class="sidebar-item"
              data-tab="variables"
              @click="switchTab('variables')"
            >
              手动添加脚本
            </li>
            <li
              class="sidebar-item"
              data-tab="plugins"
              @click="switchTab('plugins')"
            >
              编辑脚本
            </li>
          </ul>
        </div>
      </div>

      <div class="main-content">
        <div class="recordSteps autoLayout">
          <h3>✅晓阳AI平台介绍</h3>
          <br />
          本平台是一款集成了脚本自动化与AI大模型的综合工具，
          减少重复性劳动，帮助用户提高工作效率；对接内部系统，利用AI大模型技术处理综合性问题，实现业务流程的智能化升级。
        </div>

        <!-- 首页步骤 -->
        <div class="recordSteps autoIndex">
          <h3>✅ 登录及首页介绍</h3>
          <ul>
            <li>
              1. 打开应用后，使用企业微信扫码登录，登录成功后即可进入首页
              <div>
                <img
                  style="max-height: 50vh; margin: 16px 6px"
                  src="@/assets/login-pic.png"
                  alt=""
                />
              </div>
            </li>
            <li>
              2.
              登录成功后跳转首页，会显示本地已有的脚本，可以根据名字模糊匹配进行搜索🔍
              <br />
              &nbsp;&nbsp;&nbsp;运行脚本即可执行自动化任务，脚本卡片右上角有当前运行状态，例如：<span
                style="color: #5366a6; font-weight: 700"
                >运行中、成功、失败</span
              >
              等
              <div>
                <img
                  style="max-height: 50vh; margin: 16px 6px"
                  src="@/assets/ai-index.png"
                  alt=""
                />
              </div>
            </li>
            <li>
              3. 点击标题，可以跳转到脚本详情页面;<br />
              &nbsp;&nbsp;&nbsp;
              在这里可以单独测试、编辑和删除具体某一条步骤，也可以更改脚本名称
              <div>
                <img
                  style="max-height: 50vh; margin: 16px 6px"
                  src="@/assets/auto-detaile.png"
                  alt=""
                />
              </div>
            </li>
          </ul>
        </div>

        <!-- 录制脚本步骤 -->
        <div class="recordSteps autoRecord">
          <h3>✅ 如何录制脚本</h3>
          <ul>
            <li>
              1. 点击下方第二个菜单图标，进入新建页面，支持两种方式：
              <span><img src="@/assets/record.svg" alt="" /> 录制脚本</span
              >和手动<span><img src="@/assets/add.svg" alt="" /> 添加脚本</span>
            </li>
            <li>
              2.
              可以直接点击录制按钮，屏幕右下角会出现三个按钮，从左到右分别是停止、录制、返回按钮
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              3. 点击录制按钮就可以开始录制屏幕的操作了
              <div class="tip-box">
                <span class="tip-icon">提示：</span>
                <span class="tip-content">
                  录制过程中，需要操作慢一点，当左下角显示"识别中..."时，请不要操作，否则步骤可能会丢失</span
                >
              </div>
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              4.录制完成后点击停止录制，再次点击返回，可以看见页面上出现刚刚录制的步骤
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              5.点击执行程序可以自动执行刚刚手动操作的步骤
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 添加脚本步骤 -->
        <div class="recordSteps autoAdd">
          <h3>✅ 如何手动添加脚本</h3>
          <ul>
            <li>
              1. 点击下方添加步骤按钮，在弹出的插件指令中选择指令
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              2.
              将鼠标悬浮到已添加的步骤上时，会自动悬浮显示添加按钮，点击后即可在该步骤后添加新步骤
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 编辑脚本步骤 -->
        <div class="recordSteps autoEdit">
          <h3>✅ 如何编辑已有脚本</h3>
          <ul>
            <li>
              1.
              首先进入首页，点击想要编辑的脚本，进入编辑页面，这里支持修改脚本名称，新增、修改、删除、移动步骤
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              2.
              新增：与手动添加步骤类似，悬浮到已有步骤上，点击新增动画图标，可以添加新的步骤
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              3. 修改：悬浮到已有步骤上，点击修改图标，可以修改该步骤
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              4. 删除：悬浮到已有步骤上，点击删除图标，可以删除该步骤
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              5.
              移动：悬浮到已有步骤名称上，点击可以拖动该步骤到指定位置，其余步骤顺序顺移
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              6. 录制：点击后，可以在弹出框中，选择覆盖或追加步骤
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              7. 执行：上方蓝色执行按钮表示执行该脚本全部内容
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
            <li>
              8. 测试：点击后单步执行当前步骤
              <br />
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
  name: 'AutomationSection',
  data() {
    return {
      activeTab: 'layout'
    }
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
        recording: 'autoIndex',
        management: 'autoRecord',
        variables: 'autoAdd',
        plugins: 'autoEdit',
        layout: 'autoLayout'
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
        autoIndex: 'recording',
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

/* 脚本自动化页面样式 */
.automation-section {
  display: flex;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
  height: 100%;
}

.automation-content {
  display: flex;
  flex: 1;
  gap: 24px;
  overflow: hidden;
  background-color: white;
  border-radius: 16px;
}

.automation-sidebar {
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
  background-color: #f3f4f6;
  color: #333;
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
  font-size: 16px;
  line-height: 28px;
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

.recordSteps li img {
  vertical-align: middle;
  margin-top: -2px;
}

.imgStyle {
  margin: 16px 6px;
  width: 80px;
}

/* .imgStyle img {
  width: 260%;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
} */
</style>
