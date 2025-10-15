<template>
  <section class="aiSection">
    <div class="pageHead">
      <h1 class="pageTitle">AI 大模型对话</h1>
      <p class="pageDesc">
        如何使用AI智能对话，将从以下几个方面分别介绍使用方法：
      </p>
    </div>

    <div class="aiModules">
      <ul>
        <li>规则系统</li>
        <li>外包考勤系统</li>
        <li>智能运维平台</li>
        <li>阳光灵思图</li>
        <li>PDF工具</li>
      </ul>
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
.pageHead {
  margin-bottom: 32px;
}

.pageHead h1 {
  font-size: 28px;
  margin-bottom: 8px;
  color: #1f2937;
}

.pageDesc {
  color: #6b7280;
  font-size: 16px;
}

/* AI模块内容 */
.aiModules {
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
