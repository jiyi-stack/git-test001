<template>
  <section class="sunshine-section">
    <div class="page-header">
      <h1 class="page-title">阳光灵思图</h1>
      <p style="color: #666">
        阳光灵思图是基于Eclipse
        RCP架构与Java语言开发，支持Windows、Mac、Linux及移动端操作系统。其核心功能涵盖思维导图、鱼骨图、组织结构图等多样化图表绘制，并提供甘特图转换、云端同步及与Office软件的无缝集成，支持导出至Word、PPT等十余种格式。您可点击访问<a
          href="https://www.iconfont.cn/"
          target="_blank"
          >https://sunshine-ideas.xmind.net/</a
        >
      </p>
    </div>

    <div class="sunshine-content">
      <div class="sunshine-tools">
        <img src="@/assets/xmind.jpg" alt="点击跳转页面" @click="goXmind" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SunshineSection',
  data() {
    return {
      selectedTool: null,
      activeAnalysisTab: 'sentiment',
      ideaTopic: '',
      ideaKeywords: [],
      newKeyword: '',
      ideaType: 'marketing',
      analysisText: '',
      generatedIdeas: [],
      analysisResult: null
    }
  },
  computed: {
    selectedToolTitle() {
      const titles = {
        'idea-generator': '创意生成器',
        'text-analyzer': '文本分析',
        'mind-map': '思维导图',
        'content-optimizer': '内容优化'
      }
      return titles[this.selectedTool] || ''
    }
  },
  methods: {
    goXmind() {
      console.log('跳转到阳光灵思图') // 在此处添加跳转到阳光灵思图的逻辑
    },
    selectTool(tool) {
      this.selectedTool = tool
      this.clearWorkspace()
    },
    clearWorkspace() {
      this.ideaTopic = ''
      this.ideaKeywords = []
      this.newKeyword = ''
      this.ideaType = 'marketing'
      this.analysisText = ''
      this.generatedIdeas = []
      this.analysisResult = null
    },
    addKeyword() {
      if (this.newKeyword.trim() !== '') {
        this.ideaKeywords.push(this.newKeyword.trim())
        this.newKeyword = ''
      }
    },
    removeKeyword(index) {
      this.ideaKeywords.splice(index, 1)
    },
    generateResult() {
      if (this.selectedTool === 'idea-generator') {
        // 模拟生成创意
        this.generatedIdeas = [
          `基于"${this.ideaTopic}"的${
            this.ideaType === 'marketing'
              ? '营销'
              : this.ideaType === 'product'
              ? '产品'
              : this.ideaType === 'design'
              ? '设计'
              : this.ideaType === 'story'
              ? '故事'
              : '创意'
          }创意：结合${this.ideaKeywords.join('、')}，打造独特方案`,
          `针对"${this.ideaTopic}"的创新思路：将${this.ideaKeywords.join(
            '、'
          )}融入其中，创造差异化优势`,
          `关于"${this.ideaTopic}"的创意灵感：利用${this.ideaKeywords.join(
            '、'
          )}，探索全新可能性`
        ]
      } else if (
        this.selectedTool === 'text-analyzer' &&
        this.analysisText.trim() !== ''
      ) {
        // 模拟分析结果
        this.analysisResult = {
          sentiment: {
            positive: 65,
            neutral: 25,
            negative: 10,
            summary: '文本整体呈现积极情感，主要表达了对产品的满意和期待。'
          },
          keywords: [
            { text: '产品', weight: 0.9 },
            { text: '质量', weight: 0.8 },
            { text: '服务', weight: 0.7 },
            { text: '价格', weight: 0.6 },
            { text: '体验', weight: 0.5 }
          ],
          summary:
            '该文本主要讨论了产品的各个方面，包括质量、服务和价格等，整体评价较为积极。'
        }
      }
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

.sunshine-tools img {
  max-width: 100%;
  max-height: 600px;
  object-fit: contain;
  cursor: pointer;
  transition: transform 0.2s;
}

.sunshine-tools img:hover {
  transform: scale(1.02);
}
</style>
