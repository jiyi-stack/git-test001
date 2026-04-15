<template>
  <section class="sunshine-section">
    <div class="page-header">
      <h1 class="page-title">阳光灵思图</h1>
      <p style="color: #666">
        阳光灵思图核心功能涵盖思维导图、鱼骨图、组织结构图等多样化图表绘制，
        支持导出至Word、PPT、JPEG等多种格式，支持在线协同编辑思维导图，新增评论功能，更多功能正在开发中，敬请期待！
        点击即可免密登录阳光灵思图、流程图：<a
          href="https://www.iconfont.cn/"
          target="_blank"
          >https://sunshine-ideas.xmind.net/</a
        >
      </p>
    </div>

    <div class="sunshine-content">
      <div class="sunshine-tools">
        <video src="@/assets/graphMind.mp4" @click="goXmind" controls></video>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SunshineSection',
  methods: {
    goXmind() {
      console.log('跳转到阳光灵思图') // 在此处添加跳转到阳光灵思图的逻辑
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

/* 工具部分 */
.sunshine-tools {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.sunshine-tools video {
  max-width: 100%;
  max-height: 600px;
  object-fit: contain;
  cursor: pointer;
  transition: transform 0.2s;
}

.sunshine-tools video:hover {
  transform: scale(1.02);
}
</style>
