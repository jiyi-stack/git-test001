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
              data-tab="recording"
              @click="switchTab('recording')"
            >
              登录
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
        <!-- <FontDecration>操作步骤如下：</FontDecration> -->

        <!-- 首页步骤 -->
        <div class="recordSteps autoIndex">
          <h3>✅ 如何登录到首页</h3>
          <ul>
            <li>
              1. 打开应用后，使用企业微信扫码登录，登录成功后即可进入首页
              <div class="imgStyle">
                <img src="@/assets/capture2.png" alt="" />
              </div>
            </li>
            <li>
              2.
              登录成功后跳转首页，首页是首显示本地已有的脚本，可以根据名字模糊匹配
              <br />
              <div class="imgStyle">
                <img src="@/assets/capture1.png" alt="" />
              </div>
            </li>
            <li>
              3. 点击标题，可以跳转到脚本详情页面
              <div class="imgStyle">
                <img src="@/assets/img.png" alt="" />
              </div>
            </li>
          </ul>
          <p></p>
        </div>

        <!-- 录制脚本步骤 -->
        <div class="recordSteps autoRecord">
          <h3>✅ 如何录制脚本</h3>
          <ul>
            <li>
              1.
              点击下方第二个菜单图标，进入新建页面，支持两种方式：录制脚本和手动添加脚本
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
          <p></p>
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
          <p></p>
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
          <p></p>
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
      activeTab: 'recording'
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
  /* border-right: 1px solid #e5e7eb; */
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
  /* background-color: rgb(245, 245, 245); */
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
.record-step {
  padding: 16px;
  margin-bottom: 16px;
  border-radius: 8px;
  background-color: #f9fafb;
  display: flex;
  align-items: center;
  gap: 16px;
}

.tab-content {
  display: none;
  flex-direction: column;
  flex: 1;
}

.tab-content.active {
  display: flex;
}

/* 录制区域样式 */
.recording-area {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 24px;
  margin-bottom: 24px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.recording-controls {
  display: flex;
  gap: 16px;
  justify-content: center;
}

.control-btn {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: transform 0.1s;
}

.control-btn:hover {
  transform: scale(1.05);
}

.control-btn.record {
  background-color: #ef4444;
  color: white;
}

.control-btn.pause {
  background-color: #f59e0b;
  color: white;
}

.control-btn.stop {
  background-color: #6b7280;
  color: white;
}

.recording-status {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

.status-indicator {
  padding: 6px 12px;
  border-radius: 4px;
  font-weight: 500;
  font-size: 14px;
}

.status-indicator.idle {
  background-color: #e5e7eb;
  color: #6b7280;
}

.status-indicator.recording {
  background-color: #fee2e2;
  color: #dc2626;
}

.status-indicator.paused {
  background-color: #fef3c7;
  color: #d97706;
}

.status-info {
  color: #6b7280;
  font-size: 14px;
}

.recording-options {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.recording-options h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.options-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.option-item {
  display: flex;
  align-items: center;
}

.checkbox-label {
  display: flex;
  align-items: center;
  cursor: pointer;
  font-size: 14px;
  color: #374151;
}

.checkbox-label input[type='checkbox'] {
  margin-right: 8px;
}

/* 执行区域样式 */
.execution-area {
  display: flex;
  flex: 1;
  gap: 24px;
}

.script-list,
.execution-details {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.script-list {
  width: 300px;
  flex-shrink: 0;
}

.execution-details {
  flex: 1;
  display: flex;
  flex-direction: column;
}

.script-list h3,
.execution-details h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.script-items {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.script-item {
  padding: 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  transition: border-color 0.2s;
}

.script-item:hover {
  border-color: #d1d5db;
}

.script-item.selected {
  border-color: #2563eb;
  background-color: #eff6ff;
}

.script-info h4 {
  font-size: 16px;
  font-weight: 500;
  margin-bottom: 4px;
  color: #1f2937;
}

.script-info p {
  font-size: 14px;
  color: #6b7280;
}

.script-actions {
  display: flex;
  gap: 4px;
}

.execution-log {
  flex: 1;
  overflow-y: auto;
  background-color: #1f2937;
  color: #f9fafb;
  border-radius: 6px;
  padding: 16px;
  font-family: monospace;
  font-size: 14px;
}

.log-entry {
  margin-bottom: 4px;
  display: flex;
  gap: 8px;
}

.log-time {
  color: #9ca3af;
}

.log-message {
  color: #f9fafb;
}

/* 脚本管理样式 */
.script-management {
  display: flex;
  flex: 1;
  gap: 24px;
}

.file-tree {
  width: 300px;
  flex-shrink: 0;
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.script-editor {
  flex: 1;
  display: flex;
  flex-direction: column;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.file-tree h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.tree-container {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.tree-folder {
  margin-bottom: 8px;
}

.folder-header {
  display: flex;
  align-items: center;
  padding: 6px 8px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.folder-header:hover {
  background-color: #f3f4f6;
}

.folder-header i {
  margin-right: 8px;
  color: #6b7280;
}

.folder-header i:first-child {
  font-size: 12px;
}

.folder-header i:nth-child(2) {
  margin-right: 8px;
}

.folder-header span {
  font-size: 14px;
  color: #374151;
}

.folder-contents {
  margin-left: 24px;
  display: none;
}

.folder-contents.show {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.tree-file {
  display: flex;
  align-items: center;
  padding: 6px 8px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.tree-file:hover {
  background-color: #f3f4f6;
}

.tree-file i {
  margin-right: 8px;
  color: #6b7280;
}

.tree-file span {
  font-size: 14px;
  color: #374151;
}

.editor-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #e5e7eb;
}

.editor-tabs {
  display: flex;
  gap: 16px;
}

.editor-tab {
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  color: #6b7280;
  cursor: pointer;
  transition: background-color 0.2s;
}

.editor-tab:hover {
  background-color: #f3f4f6;
}

.editor-tab.active {
  background-color: #eff6ff;
  color: #2563eb;
}

.editor-actions {
  display: flex;
  gap: 12px;
}

.editor-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.editor-code,
.editor-variables,
.editor-log {
  display: none;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
}

.editor-code.active,
.editor-variables.active,
.editor-log.active {
  display: flex;
}

.editor-variables h3,
.editor-log h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.editor-code pre {
  flex: 1;
  overflow: auto;
  background-color: #1f2937;
  color: #f9fafb;
  border-radius: 6px;
  padding: 16px;
  font-family: monospace;
  font-size: 14px;
  margin: 0;
}

.editor-code code {
  font-family: monospace;
}

.variables-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
  overflow-y: auto;
  flex: 1;
  padding-right: 8px;
}

.variable-item {
  display: flex;
  align-items: center;
  padding: 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  background-color: #f9fafb;
}

.variable-name {
  width: 120px;
  font-weight: 500;
  color: #1f2937;
}

.variable-value {
  flex: 1;
  font-family: monospace;
  color: #4b5563;
}

.variable-type {
  width: 80px;
  color: #6b7280;
  font-size: 14px;
}

.variable-usage {
  width: 100px;
  color: #6b7280;
  font-size: 14px;
}

.variable-actions {
  display: flex;
  gap: 4px;
}

.log-container {
  flex: 1;
  overflow-y: auto;
  background-color: #1f2937;
  border-radius: 6px;
  padding: 16px;
  font-family: monospace;
  font-size: 14px;
}

.log-entry {
  margin-bottom: 4px;
  display: flex;
  gap: 8px;
}

.log-entry.info .log-time {
  color: #9ca3af;
}

.log-entry.info .log-message {
  color: #f9fafb;
}

.log-entry.success .log-time {
  color: #9ca3af;
}

.log-entry.success .log-message {
  color: #10b981;
}

/* 变量管理样式 */
.variables-management {
  display: flex;
  flex-direction: column;
  gap: 24px;
  flex: 1;
}

.variables-overview {
  display: flex;
  gap: 24px;
}

.stats-cards {
  display: flex;
  gap: 24px;
  width: 100%;
}

.stat-card {
  flex: 1;
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 16px;
  border-radius: 8px;
  background-color: #f9fafb;
  border: 1px solid #e5e7eb;
}

.stat-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  background-color: #eff6ff;
}

.stat-icon i {
  font-size: 24px;
  color: #2563eb;
}

.stat-info {
  display: flex;
  flex-direction: column;
}

.stat-value {
  font-size: 24px;
  font-weight: 600;
  color: #1f2937;
}

.stat-label {
  font-size: 14px;
  color: #6b7280;
}

.variables-list-container {
  display: flex;
  flex-direction: column;
  flex: 1;
  gap: 16px;
}

.variables-filters {
  display: flex;
  gap: 16px;
  align-items: center;
}

.search-box {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  background-color: #fff;
  flex: 1;
}

.search-box i {
  color: #9ca3af;
}

.search-box input {
  border: none;
  background: none;
  outline: none;
  width: 100%;
  font-size: 14px;
  color: #1f2937;
}

.filter-options {
  display: flex;
  gap: 12px;
}

.filter-select {
  padding: 8px 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  background-color: #fff;
  font-size: 14px;
  color: #1f2937;
  cursor: pointer;
}

.variables-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  flex: 1;
  overflow-y: auto;
}

.variable-group {
  border-radius: 8px;
  border: 1px solid #e5e7eb;
  overflow: hidden;
}

.group-header {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  background-color: #f9fafb;
  cursor: pointer;
  transition: background-color 0.2s;
}

.group-header:hover {
  background-color: #f3f4f6;
}

.group-header i {
  margin-right: 8px;
  color: #6b7280;
}

.group-header i:first-child {
  font-size: 12px;
}

.group-header i:nth-child(2) {
  margin-right: 12px;
}

.group-header span {
  font-size: 16px;
  font-weight: 500;
  color: #1f2937;
}

.group-count {
  margin-left: auto;
  font-size: 14px;
  color: #6b7280;
}

.group-variables {
  display: flex;
  flex-direction: column;
}

.variable-row {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  border-top: 1px solid #e5e7eb;
}

.variable-name {
  width: 120px;
  font-weight: 500;
  color: #1f2937;
}

.variable-value {
  flex: 1;
  font-family: monospace;
  color: #4b5563;
}

.variable-type {
  width: 80px;
  color: #6b7280;
  font-size: 14px;
}

.variable-usage {
  width: 100px;
  color: #6b7280;
  font-size: 14px;
}

.variable-actions {
  display: flex;
  gap: 4px;
}

/* 插件管理样式 */
.plugins-management {
  display: flex;
  flex-direction: column;
  gap: 24px;
  flex: 1;
}

.plugins-categories {
  display: flex;
  gap: 12px;
  border-bottom: 1px solid #e5e7eb;
  padding-bottom: 12px;
}

.category-tab {
  padding: 8px 16px;
  border-radius: 6px 6px 0 0;
  font-size: 14px;
  font-weight: 500;
  color: #6b7280;
  cursor: pointer;
  transition: background-color 0.2s;
}

.category-tab:hover {
  color: #1f2937;
}

.category-tab.active {
  color: #2563eb;
  background-color: #eff6ff;
}

.plugins-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  flex: 1;
}

.plugin-card {
  background-color: #fff;
  border-radius: 8px;
  border: 1px solid #e5e7eb;
  padding: 20px;
  transition: box-shadow 0.2s;
}

.plugin-card:hover {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.plugin-header {
  display: flex;
  align-items: center;
  margin-bottom: 12px;
}

.plugin-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  margin-right: 16px;
  background-color: #f3f4f6;
}

.plugin-icon i {
  font-size: 24px;
  color: #6b7280;
}

.plugin-info {
  flex: 1;
}

.plugin-name {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 4px;
  color: #1f2937;
}

.plugin-meta {
  display: flex;
  gap: 12px;
}

.plugin-version {
  font-size: 14px;
  color: #6b7280;
}

.plugin-category {
  font-size: 14px;
  color: #6b7280;
}

.plugin-status {
  margin-left: 16px;
}

.status-badge {
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}

.status-badge.installed {
  background-color: #d1fae5;
  color: #065f46;
}

.status-badge.recommended {
  background-color: #dbeafe;
  color: #1e40af;
}

.plugin-description {
  color: #4b5563;
  line-height: 1.5;
  margin-bottom: 16px;
}

.plugin-actions {
  display: flex;
  gap: 12px;
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
</style>
