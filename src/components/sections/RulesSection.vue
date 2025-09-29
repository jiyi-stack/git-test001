<template>
  <section class="rules-section">
    <div class="page-header">
      <h1 class="page-title">规则系统</h1>
      <p class="page-description">
        基于规则的智能决策引擎，支持复杂业务逻辑的自动化处理
      </p>
    </div>

    <div class="intro-features">
      <div class="feature-item">
        <i class="fas fa-check-circle"></i>
        <span>支持各种规则执行流，提供可视化编辑</span>
      </div>
      <div class="feature-item">
        <i class="fas fa-check-circle"></i>
        <span>AI在线代码生成、测试</span>
      </div>
      <div class="feature-item">
        <i class="fas fa-check-circle"></i>
        <span>多维度规则执行统计报表</span>
      </div>
      <div class="feature-item">
        <i class="fas fa-check-circle"></i>
        <span>规则版本回溯，提供各维度规则图谱</span>
      </div>
    </div>
    <div class="main-content">
      <FontDecration>操作步骤</FontDecration>
    </div>
  </section>
</template>

<script>
import FontDecration from '@/components/FontDecration.vue'

export default {
  name: 'RulesSection',
  components: {
    FontDecration
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

/* 规则内容 */
.rules-content {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

/* 规则概述 */
.rules-overview {
  display: flex;
  flex: 1;
  gap: 24px;
}

.intro-text h2 {
  font-size: 22px;
  margin-bottom: 16px;
  color: #1f2937;
}

.intro-text p {
  color: #4b5563;
  line-height: 1.6;
  margin-bottom: 24px;
}

.intro-features {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #4b5563;
}

.feature-item i {
  color: #10b981;
}

.main-content {
  margin-top: 28px;
  flex: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}
</style>
