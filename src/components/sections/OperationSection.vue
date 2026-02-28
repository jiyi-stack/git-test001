<template>
  <section class="rule-section">
    <div class="page-header">
      <h1 class="page-title">智能运维平台</h1>
      <p class="page-description">
        智能运维平台是一个处理一些契约日常运维功能，晓阳ai可以访问查询查询保单数据、轨迹、报文等。智能运维平台地址：<a
          href="https://www.iconfont.cn/"
          target="_blank"
          >https://sunshine-ideas.xmind.net/</a
        >
      </p>
    </div>
    <div class="rule-content">
      <div class="rule-sidebar">
        <div class="sidebar-menu">
          <h3>功能导航</h3>
          <ul>
            <li
              class="sidebar-item active"
              data-tab="policyInfo"
              @click="switchTab('policyInfo')"
            >
              保单信息
            </li>
            <li
              class="sidebar-item"
              data-tab="policyTrack"
              @click="switchTab('policyTrack')"
            >
              保单轨迹
            </li>
            <li
              class="sidebar-item"
              data-tab="policyMsg"
              @click="switchTab('policyMsg')"
            >
              保单交互报文
            </li>
            <li
              class="sidebar-item"
              data-tab="policyReq"
              @click="switchTab('policyReq')"
            >
              保单请求数据
            </li>
            <li
              class="sidebar-item"
              data-tab="policyHistory"
              @click="switchTab('policyHistory')"
            >
              历史保单信息
            </li>
          </ul>
        </div>
      </div>

      <div class="main-content">
        <!-- 查询保单信息 -->
        <div class="recordSteps policyInfo">
          <h3>✅ 查询保单信息</h3>
          <ul>
            <li>
              1.
              进入晓阳AI对话模块，点击智能运维平台卡片，在对话框选择模板，这里包含查询保单信息、查询保单轨迹、查询保单交互报文、查询保单请求数据、查询历史保单信息的模板。
              <div>
                <img
                  src="@/assets/policytepm.png"
                  alt=""
                  style="width: 50%; margin-top: 12px"
                />
              </div>
            </li>
            <li>
              2.
              选择查询保单信息模板，会出现“查询投保单号为xxxx的保单信息”，替换xxxx为具体的投保单号，发送给晓阳ai，它会返回该投保单号的具体信息。
              <br />
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 保单轨迹 -->
        <div class="recordSteps policyTrack">
          <h3>✅ 查询保单轨迹</h3>
          <ul>
            <li>
              选择查询保单轨迹模板，会出现“查询投保单号为xxxx的保单处理轨迹”，同上，替换具体的投保单号，发送给晓阳ai，便会查询该投保单号的轨迹信息。
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 保单交互报文 -->
        <div class="recordSteps policyMsg">
          <h3>✅ 查询保单交互报文</h3>
          <ul>
            <li>
              选择查询保单交互报文模板，会出现“查询投保单号为xxxx的保单交互报文”，同上，替换具体的投保单号，发送给晓阳ai，便会查询该投保单号的交互报文。
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 保单请求数据 -->
        <div class="recordSteps policyReq">
          <h3>✅ 查询保单请求数据</h3>
          <ul>
            <li>
              选择模板，“查询投保单号为xxxx的保单请求数据”，替换具体的投保单号，发送给晓阳ai，便会查询该投保单号的请求数据。
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
        </div>

        <!-- 历史保单信息 -->
        <div class="recordSteps policyHistory">
          <h3>✅ 查询历史保单信息</h3>
          <ul>
            <li>
              选择查询历史保单信息模板，同上，替换具体的投保单号，发送给晓阳ai，便会查询该投保单号的历史保单信息。
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
export default {
  name: 'OperationSection',
  components: {
    // FontDecration
  },
  data() {
    return {
      activeTab: 'policyInfo'
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
        policyInfo: 'policyInfo',
        policyTrack: 'policyTrack',
        policyMsg: 'policyMsg',
        policyReq: 'policyReq',
        policyHistory: 'policyHistory'
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
        policyInfo: 'policyInfo',
        policyTrack: 'policyTrack',
        policyMsg: 'policyMsg',
        policyReq: 'policyReq',
        policyHistory: 'policyHistory'
      }
      // 确保输入是字符串类型，防止undefined或null导致的问题
      if (typeof sectionClass !== 'string') {
        return 'policyInfo'
      }
      return sectionToTabMap[sectionClass] || 'policyInfo'
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
