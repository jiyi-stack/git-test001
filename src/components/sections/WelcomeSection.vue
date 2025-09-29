<template>
  <section class="welcome-section">
    <div class="welcome-header">
      <img src="@/assets/logo.png" alt="Logo" class="welcome-logo" />
      <h2>欢迎使用晓阳AI</h2>
    </div>
    <div class="welcome-card">
      <p class="welcome-text">
        本平台是一款集成了脚本自动化与AI大模型的综合工具，
        减少重复性劳动，帮助用户提高工作效率；对接内部系统，利用AI大模型技术处理综合性问题，实现业务流程的智能化升级。
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
            对接多个系统，包含规则系统、考勤管理、智能分析等，助力AI协助工作，提升效率。
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
</template>

<script>
export default {
  name: 'WelcomeSection'
}
</script>

<style scoped>
/* 欢迎区域标题 */
.welcome-header {
  /* position: sticky; */
  top: 0;
  z-index: 10;
  display: flex;
  align-items: center;
  margin-bottom: 24px;
  height: 60px;
  background-color: #f9fafb;
}

.welcome-logo {
  width: 48px;
  height: auto;
  margin-right: 16px;
  flex-shrink: 0;
}

.welcome-header h2 {
  margin: 0;
  font-size: 24px;
  font-weight: bold;
}

/* 页面标题 */
.page-title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 24px;
  color: #1f2937;
}

/* 卡片样式 */
.welcome-card {
  background-color: #fff;
  border-radius: 8px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  margin-bottom: 32px;
}

.welcome-text {
  color: #4b5563;
  line-height: 1.6;
  margin-bottom: 24px;
}

/* 功能卡片网格 */
.feature-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
}

.feature-card {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 24px;
  transition: transform 0.2s;
}

.feature-card:hover {
  transform: translateY(-5px);
  background-color: #f4f5f7;
}

.feature-icon {
  width: 48px;
  height: 48px;
  background-color: rgba(37, 99, 235, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 16px;
}

.feature-icon i {
  color: #2563eb;
  font-size: 24px;
}

/* 为不同feature-card设置不同颜色 */
.feature-card-1 .feature-icon {
  background-color: rgba(139, 92, 246, 0.1);
  /* 紫色背景 */
}

.feature-card-1 .feature-icon i {
  color: #8b5cf6;
  /* 紫色图标 */
}

.feature-card-2 .feature-icon {
  background-color: rgba(245, 158, 11, 0.1);
  /* 黄色背景 */
}

.feature-card-2 .feature-icon i {
  color: #f59e0b;
  /* 黄色图标 */
}

.feature-card-3 .feature-icon {
  background-color: rgba(37, 99, 235, 0.1);
  /* 蓝色背景 */
}

.feature-card-3 .feature-icon i {
  color: #2563eb;
  /* 蓝色图标 */
}

.feature-title {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 12px;
  color: #1f2937;
}

.feature-description {
  color: #4b5563;
  line-height: 1.5;
}
</style>
