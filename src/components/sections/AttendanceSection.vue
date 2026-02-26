<template>
  <section class="rule-section">
    <div class="page-header">
      <h1 class="page-title">外包考勤系统</h1>
      <p class="page-description">
        智能考勤管理，支持多种考勤规则和自动化处理流程
      </p>
    </div>
    <div class="rule-content">
      <div class="rule-sidebar">
        <div class="sidebar-menu">
          <h3>功能导航</h3>
          <ul>
            <li
              class="sidebar-item active"
              data-tab="introduction "
              @click="switchTab('introduction')"
            >
              考勤系统功能介绍
            </li>
            <li
              class="sidebar-item"
              data-tab="summary"
              @click="switchTab('summary')"
            >
              考勤详情/汇总
            </li>
            <li
              class="sidebar-item"
              data-tab="handleExceptions"
              @click="switchTab('handleExceptions')"
            >
              考勤异常处理
            </li>
            <li
              class="sidebar-item"
              data-tab="datecheck"
              @click="switchTab('datecheck')"
            >
              调休信息查询
            </li>
            <li
              class="sidebar-item"
              data-tab="leadercheck"
              @click="switchTab('leadercheck')"
            >
              组长审批考勤
            </li>
          </ul>
        </div>
      </div>

      <div class="main-content">
        <FontDecration>操作步骤如下：</FontDecration>

        <!-- 考勤系统介绍 -->
        <div class="recordSteps introduction">
          <h3>✅ 考勤系统功能介绍</h3>
          <ul>
            <li>
              1.
              首先，查看考勤系统的功能介绍页面，了解系统的基本功能和操作流程。
              <div>
                <img
                  src="@/assets/down2.png"
                  alt=""
                  style="width: 700px; padding-top: 12px"
                />
              </div>
            </li>
            <li>
              2.如图所示，我们的考勤系统包含组长端和组员端。组长负责审批组员的考勤信息,并可以设置考勤规则。组员每月查询考勤信息，处理异常数据，查询调休信息，下载考勤表的功能，下面我将依次为您介绍该系统的使用方法
              <br />
            </li>
          </ul>
        </div>

        <!-- 考勤信息汇总 -->
        <div class="recordSteps summary">
          <h3>✅ 考勤详情与汇总信息</h3>
          <ul>
            <li>
              1.在输入框中选择模板，查询当月考勤详情或汇总。
              <div>
                <!-- <img src="@/assets/img.png" alt="" /> -->
                <img
                  src="@/assets/attendenceAll.png"
                  alt=""
                  style="width: 650px; padding-top: 12px"
                />
              </div>
            </li>
            <li>
              2.晓阳ai会根据打卡时间，异常时长，调休时长，正常时长，加班时长，请假时长，缺勤时长等，生成对应的考勤详情或汇总表格。
              <div class="imgStyle">
                <img
                  src="@/assets/attendenceAll.png"
                  alt=""
                  style="width: 1000px; padding-top: 12px"
                />
              </div>
            </li>
          </ul>
        </div>

        <!-- 考勤异常信息处理 -->
        <div class="recordSteps handleExceptions">
          <h3>✅ 考勤异常信息处理</h3>
          <ul>
            <li>
              1.在输入框中选择模板，查询当月考勤汇总。
              <div>
                <!-- <img src="@/assets/img.png" alt="" /> -->
                <img
                  src="@/assets/AIpdf.png"
                  alt=""
                  style="width: 1000px; padding-top: 12px"
                />
              </div>
            </li>
            <li>
              2.等待晓阳ai提供异常数据，查看表格，提交自己的异常原因与时长，批量提交，异常数据处理完成。
              <div>
                <img
                  src="@/assets/AIpdf.png"
                  alt=""
                  style="width: 1000px; padding-top: 12px"
                />
              </div>
            </li>
          </ul>
        </div>

        <!-- 调休信息查询 -->
        <div class="recordSteps datecheck">
          <h3>✅ 调休信息查询</h3>
          <ul>
            <li>
              在输入框中选择模板，查询当月调休信息。晓阳ai会提供调休信息表格。
              <div class="imgStyle">
                <img
                  src="@/assets/AIpdf.png"
                  alt=""
                  style="width: 1000px; padding-top: 12px"
                />
              </div>
            </li>
          </ul>
        </div>

        <!-- 组长审批考勤  -->
        <div class="recordSteps leadercheck">
          <h3>✅ 组长审批考勤</h3>
          <ul>
            <li>
              组长可以后台查看组员的所有考勤信息，对提交的考勤异常信息进行审批。审批状态分为“已审批”和“未审批”两种状态
              <div class="imgStyle">
                <img
                  src="@/assets/AIpdf.png"
                  alt=""
                  style="width: 1000px; padding-top: 12px"
                />
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import FontDecration from '@/components/FontDecration.vue'

export default {
  name: 'AttendanceSection',
  components: {
    FontDecration
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
        introduction: 'introduction',
        summary: 'summary',
        handleExceptions: 'handleExceptions',
        datecheck: 'datecheck',
        leadercheck: 'leadercheck'
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
        introduction: 'introduction',
        summary: 'summary',
        handleExceptions: 'handleExceptions',
        queryTime: 'queryTime'
      }
      return sectionToTabMap[sectionClass] || 'introduction'
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
  background-color: #f3f4f6;
  color: #333;
  font-weight: 500;
}

.main-content {
  padding: 30px 0 0 0;
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
  padding: 4px 16px 16px 16px;
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

/* 脚本自动化页面样式 */
.rule-section {
  display: flex;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
  height: 100%;
}
</style>
