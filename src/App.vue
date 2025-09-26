<template>
  <div class="main-container">
    <!-- 左侧菜单 -->
    <Home></Home>

    <!-- 右侧内容区 -->
    <main class="content-wrapper">
      <!-- 首页内容 -->
      <section class="welcome-section">
        <div class="welcome-header">
          <img src="/src/assets/logo.png" alt="Logo" class="welcome-logo" />
          <h2>欢迎使用晓阳AI</h2>
        </div>
        <div class="welcome-card">
          <p class="welcome-text">
            我们的平台致力于为企业提供全方位的自动化解决方案。通过整合脚本自动化、AI
            智能处理以及丰富的插件系统，帮助您提升工作效率，实现业务流程的智能化升级。
          </p>

          <div class="feature-grid">
            <div class="feature-card feature-card-1">
              <div class="feature-icon">
                <i class="fas fa-code"></i>
              </div>
              <h3 class="feature-title">脚本自动化</h3>
              <p class="feature-description">
                强大的脚本录制与执行功能，轻松实现重复性工作自动化，提升效率降低错误。
              </p>
            </div>

            <div class="feature-card feature-card-2">
              <div class="feature-icon">
                <i class="fas fa-robot"></i>
              </div>
              <h3 class="feature-title">AI 模块</h3>
              <p class="feature-description">
                对接多个，包含规则系统、考勤管理、智能分析等，助力AI协助工作，提升效率。
              </p>
            </div>

            <div class="feature-card feature-card-3">
              <div class="feature-icon">
                <i class="fas fa-puzzle-piece"></i>
              </div>
              <h3 class="feature-title">展示插件</h3>
              <p class="feature-description">
                丰富的插件生态，满足多样化的业务需求，支持自定义开发和场景扩展。
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- 最近更新 -->
      <section class="updates-section">
        <div class="section-header">
          <h2 class="page-title">最近更新功能</h2>
          <button class="check-update-btn">
            <i class="fas fa-sync-alt"></i>
            检查版本
          </button>
        </div>
        <div class="updates-card">
          <div class="update-list">
            <div class="update-item">
              <div class="update-bullet" id="item-1"></div>
              <div class="update-content">
                <h3 class="update-title">
                  外包考勤系统新增考勤信息下载表格功能
                </h3>
                <p class="update-description">
                  下载考勤信息，包含每日打卡数据，每月工时汇总/加班/调休工时等信息
                </p>
                <p class="update-date">2024-01-15</p>
              </div>
            </div>

            <div class="update-item">
              <div class="update-bullet" id="item-2"></div>
              <div class="update-content">
                <h3 class="update-title">脚本录制功能升级</h3>
                <p class="update-description">
                  新增智能操作识别，提高识别速度，减少在录制卡顿的现象
                </p>
                <p class="update-date">2024-01-10</p>
              </div>
            </div>

            <div class="update-item">
              <div class="update-bullet" id="item-3"></div>
              <div class="update-content">
                <h3 class="update-title">新增脚本插件</h3>
                <p class="update-description">
                  新增脚本插件Pdf处理工具插件，支持合并，压缩pdf文件
                </p>
                <p class="update-date">2024-01-05</p>
              </div>
            </div>

            <div class="update-item">
              <div class="update-bullet" id="item-4"></div>
              <div class="update-content">
                <h3 class="update-title">脚本录制跳转交互优化</h3>
                <p class="update-description">
                  跳转逻辑发生变化，点击录制后直接开启全屏记录
                </p>
                <p class="update-date">2024-01-02</p>
              </div>
            </div>

            <div class="update-item">
              <div class="update-bullet" id="item-5"></div>
              <div class="update-content">
                <h3 class="update-title">脚本录制功能升级</h3>
                <p class="update-description">
                  新增智能变量识别，提高时别速度，减少在录制卡顿的现象
                </p>
                <p class="update-date">2024-01-01</p>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
