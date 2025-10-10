<template>
  <section class="ai-modules-section">
    <div class="page-header">
      <h1 class="page-title">AI 大模型对话</h1>
      <p class="page-description">
        如何使用AI智能对话，将从三个对接系统分别介绍使用方法：
      </p>
    </div>

    <div class="ai-modules-content">
      <ul>
        <li>规则系统</li>
        <li>外包考勤系统</li>
        <li>阳光灵思图</li>
      </ul>
      <!-- <div class="modules-grid">
        <div class="module-card" @click="navigateToModule('rules')">
          <div class="module-icon">
            <i class="fas fa-brain"></i>
          </div>
          <h3 class="module-title">规则系统</h3>
          <p class="module-description">
            基于规则的智能决策引擎，支持复杂业务逻辑的自动化处理
          </p>
          <div class="module-link">
            <span>了解更多</span>
            <i class="fas fa-arrow-right"></i>
          </div>
        </div>

        <div class="module-card" @click="navigateToModule('attendance')">
          <div class="module-icon">
            <i class="fas fa-calendar-check"></i>
          </div>
          <h3 class="module-title">外包考勤系统</h3>
          <p class="module-description">
            智能考勤管理，支持多种考勤规则和自动化处理流程
          </p>
          <div class="module-link">
            <span>了解更多</span>
            <i class="fas fa-arrow-right"></i>
          </div>
        </div>

        <div class="module-card" @click="navigateToModule('sunshine')">
          <div class="module-icon">
            <i class="fas fa-lightbulb"></i>
          </div>
          <h3 class="module-title">阳光灵思图</h3>
          <p class="module-description">
            AI辅助创意工具，提供智能分析和创意生成功能
          </p>
          <div class="module-link">
            <span>了解更多</span>
            <i class="fas fa-arrow-right"></i>
          </div>
        </div>
      </div> -->
    </div>
  </section>
</template>

<script>
export default {
  name: 'AIModulesSection',
  methods: {
    navigateToModule(module) {
      this.$emit('page-change', module)
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

/* AI模块内容 */
.ai-modules-content {
  margin-left: 24px;
  color: #2563eb;
}

ul li {
  margin-bottom: 8px;
}

.modules-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
}

.module-card {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: all 0.3s;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.module-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.module-icon {
  width: 64px;
  height: 64px;
  background-color: rgba(37, 99, 235, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.module-icon i {
  font-size: 32px;
  color: #2563eb;
}

.module-title {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 8px;
  color: #1f2937;
}

.module-description {
  color: #4b5563;
  line-height: 1.5;
  flex-grow: 1;
}

.module-link {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  gap: 6px;
  color: #2563eb;
  font-weight: 500;
  transition: gap 0.2s;
}

.module-card:hover .module-link {
  gap: 10px;
}
</style>
