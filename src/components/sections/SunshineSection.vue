<template>
  <section class="sunshine-section">
    <div class="page-header">
      <h1 class="page-title">阳光灵思图</h1>
      <p class="page-description">AI辅助创意工具，提供智能分析和创意生成功能</p>
    </div>

    <div class="sunshine-content">
      <div class="sunshine-intro">
        <div class="intro-text">
          <h2>创意无限，灵感之源</h2>
          <p>阳光灵思图是一款基于人工智能的创意辅助工具，通过深度学习和自然语言处理技术，帮助您快速生成创意内容、分析文本情感、提取关键信息，让创意工作更加高效。</p>
        </div>

        <div class="intro-features">
          <div class="feature-card">
            <div class="feature-icon">
              <i class="fas fa-lightbulb"></i>
            </div>
            <h3>创意生成</h3>
            <p>基于主题和关键词，快速生成创意内容</p>
          </div>

          <div class="feature-card">
            <div class="feature-icon">
              <i class="fas fa-brain"></i>
            </div>
            <h3>智能分析</h3>
            <p>分析文本情感、提取关键信息、总结要点</p>
          </div>

          <div class="feature-card">
            <div class="feature-icon">
              <i class="fas fa-chart-line"></i>
            </div>
            <h3>数据可视化</h3>
            <p>将分析结果以图表形式直观展示</p>
          </div>
        </div>
      </div>

      <div class="sunshine-tools">
        <div class="tools-header">
          <h3>创意工具</h3>
          <div class="tools-actions">
            <button class="btn btn-primary"><i class="fas fa-plus"></i> 新建项目</button>
          </div>
        </div>

        <div class="tools-grid">
          <div class="tool-card" @click="selectTool('idea-generator')">
            <div class="tool-icon">
              <i class="fas fa-magic"></i>
            </div>
            <h4>创意生成器</h4>
            <p>输入主题和关键词，快速生成创意内容</p>
          </div>

          <div class="tool-card" @click="selectTool('text-analyzer')">
            <div class="tool-icon">
              <i class="fas fa-search"></i>
            </div>
            <h4>文本分析</h4>
            <p>分析文本情感、提取关键信息、总结要点</p>
          </div>

          <div class="tool-card" @click="selectTool('mind-map')">
            <div class="tool-icon">
              <i class="fas fa-project-diagram"></i>
            </div>
            <h4>思维导图</h4>
            <p>创建可视化思维导图，整理思路和结构</p>
          </div>

          <div class="tool-card" @click="selectTool('content-optimizer')">
            <div class="tool-icon">
              <i class="fas fa-tasks"></i>
            </div>
            <h4>内容优化</h4>
            <p>优化内容结构，提高表达效果</p>
          </div>
        </div>
      </div>

      <div class="sunshine-workspace" v-if="selectedTool">
        <div class="workspace-header">
          <h3>{{ selectedToolTitle }}</h3>
          <div class="workspace-actions">
            <button class="btn btn-secondary" @click="clearWorkspace">
              <i class="fas fa-trash"></i> 清空
            </button>
            <button class="btn btn-primary" @click="generateResult">
              <i class="fas fa-magic"></i> 生成
            </button>
          </div>
        </div>

        <div class="workspace-content">
          <!-- 创意生成器工具 -->
          <div v-if="selectedTool === 'idea-generator'" class="idea-generator">
            <div class="generator-inputs">
              <div class="input-group">
                <label>主题</label>
                <input type="text" v-model="ideaTopic" placeholder="输入创意主题">
              </div>

              <div class="input-group">
                <label>关键词</label>
                <div class="keywords-container">
                  <div v-for="(keyword, index) in ideaKeywords" :key="index" class="keyword-tag">
                    {{ keyword }}
                    <button class="keyword-remove" @click="removeKeyword(index)">
                      <i class="fas fa-times"></i>
                    </button>
                  </div>
                  <input
                    type="text"
                    v-model="newKeyword"
                    @keyup.enter="addKeyword"
                    placeholder="添加关键词"
                    class="keyword-input"
                  >
                </div>
              </div>

              <div class="input-group">
                <label>创意类型</label>
                <select v-model="ideaType">
                  <option value="marketing">营销文案</option>
                  <option value="product">产品创意</option>
                  <option value="design">设计方案</option>
                  <option value="story">故事情节</option>
                  <option value="other">其他</option>
                </select>
              </div>
            </div>

            <div class="generator-output" v-if="generatedIdeas.length > 0">
              <h4>生成的创意</h4>
              <div class="ideas-list">
                <div v-for="(idea, index) in generatedIdeas" :key="index" class="idea-item">
                  <div class="idea-content">{{ idea }}</div>
                  <div class="idea-actions">
                    <button class="btn-icon"><i class="fas fa-copy"></i></button>
                    <button class="btn-icon"><i class="fas fa-edit"></i></button>
                    <button class="btn-icon"><i class="fas fa-trash"></i></button>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- 文本分析工具 -->
          <div v-if="selectedTool === 'text-analyzer'" class="text-analyzer">
            <div class="analyzer-input">
              <label>输入文本</label>
              <textarea v-model="analysisText" rows="6" placeholder="输入要分析的文本内容"></textarea>
            </div>

            <div class="analyzer-output" v-if="analysisResult">
              <div class="analysis-tabs">
                <button
                  class="tab-button"
                  :class="{ active: activeAnalysisTab === 'sentiment' }"
                  @click="activeAnalysisTab = 'sentiment'"
                >
                  情感分析
                </button>
                <button
                  class="tab-button"
                  :class="{ active: activeAnalysisTab === 'keywords' }"
                  @click="activeAnalysisTab = 'keywords'"
                >
                  关键词提取
                </button>
                <button
                  class="tab-button"
                  :class="{ active: activeAnalysisTab === 'summary' }"
                  @click="activeAnalysisTab = 'summary'"
                >
                  文本摘要
                </button>
              </div>

              <div class="analysis-content">
                <!-- 情感分析 -->
                <div v-if="activeAnalysisTab === 'sentiment'" class="sentiment-analysis">
                  <div class="sentiment-chart">
                    <div class="sentiment-bars">
                      <div class="sentiment-item positive">
                        <div class="sentiment-label">正面</div>
                        <div class="sentiment-bar">
                          <div class="sentiment-fill" :style="{ width: analysisResult.sentiment.positive + '%' }"></div>
                        </div>
                        <div class="sentiment-value">{{ analysisResult.sentiment.positive }}%</div>
                      </div>

                      <div class="sentiment-item neutral">
                        <div class="sentiment-label">中性</div>
                        <div class="sentiment-bar">
                          <div class="sentiment-fill" :style="{ width: analysisResult.sentiment.neutral + '%' }"></div>
                        </div>
                        <div class="sentiment-value">{{ analysisResult.sentiment.neutral }}%</div>
                      </div>

                      <div class="sentiment-item negative">
                        <div class="sentiment-label">负面</div>
                        <div class="sentiment-bar">
                          <div class="sentiment-fill" :style="{ width: analysisResult.sentiment.negative + '%' }"></div>
                        </div>
                        <div class="sentiment-value">{{ analysisResult.sentiment.negative }}%</div>
                      </div>
                    </div>
                  </div>

                  <div class="sentiment-summary">
                    <h4>情感总结</h4>
                    <p>{{ analysisResult.sentiment.summary }}</p>
                  </div>
                </div>

                <!-- 关键词提取 -->
                <div v-if="activeAnalysisTab === 'keywords'" class="keywords-analysis">
                  <div class="keywords-cloud">
                    <div
                      v-for="(keyword, index) in analysisResult.keywords"
                      :key="index"
                      class="keyword-cloud-item"
                      :style="{ fontSize: keyword.weight * 20 + 12 + 'px' }"
                    >
                      {{ keyword.text }}
                    </div>
                  </div>
                </div>

                <!-- 文本摘要 -->
                <div v-if="activeAnalysisTab === 'summary'" class="summary-analysis">
                  <div class="summary-content">
                    <h4>摘要</h4>
                    <p>{{ analysisResult.summary }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
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
          `基于"${this.ideaTopic}"的${this.ideaType === 'marketing' ? '营销' : this.ideaType === 'product' ? '产品' : this.ideaType === 'design' ? '设计' : this.ideaType === 'story' ? '故事' : '创意'}创意：结合${this.ideaKeywords.join('、')}，打造独特方案`,
          `针对"${this.ideaTopic}"的创新思路：将${this.ideaKeywords.join('、')}融入其中，创造差异化优势`,
          `关于"${this.ideaTopic}"的创意灵感：利用${this.ideaKeywords.join('、')}，探索全新可能性`
        ]
      } else if (this.selectedTool === 'text-analyzer' && this.analysisText.trim() !== '') {
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
          summary: '该文本主要讨论了产品的各个方面，包括质量、服务和价格等，整体评价较为积极。'
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

.page-description {
  color: #6b7280;
  font-size: 16px;
}

/* 阳光灵思图内容 */
.sunshine-content {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

/* 介绍部分 */
.sunshine-intro {
  display: flex;
  flex-direction: column;
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
}

.intro-features {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.feature-card {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 16px;
}

.feature-icon {
  width: 64px;
  height: 64px;
  background-color: rgba(37, 99, 235, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.feature-icon i {
  font-size: 32px;
  color: #2563eb;
}

.feature-card h3 {
  font-size: 18px;
  font-weight: 600;
  color: #1f2937;
}

.feature-card p {
  color: #4b5563;
  line-height: 1.5;
}

/* 工具部分 */
.sunshine-tools {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.tools-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
}

.tools-header h3 {
  font-size: 20px;
  font-weight: 600;
  color: #1f2937;
}

.tools-actions {
  display: flex;
  gap: 12px;
}

.btn {
  padding: 8px 16px;
  border: none;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 6px;
  transition: background-color 0.2s;
}

.btn-primary {
  background-color: #2563eb;
  color: white;
}

.btn-primary:hover {
  background-color: #1d4ed8;
}

.btn-secondary {
  background-color: #f3f4f6;
  color: #374151;
}

.btn-secondary:hover {
  background-color: #e5e7eb;
}

.tools-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.tool-card {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 24px;
  cursor: pointer;
  transition: all 0.2s;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 16px;
}

.tool-card:hover {
  background-color: #f3f4f6;
  transform: translateY(-5px);
}

.tool-icon {
  width: 48px;
  height: 48px;
  background-color: rgba(37, 99, 235, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.tool-icon i {
  font-size: 24px;
  color: #2563eb;
}

.tool-card h4 {
  font-size: 16px;
  font-weight: 600;
  color: #1f2937;
}

.tool-card p {
  color: #4b5563;
  line-height: 1.5;
}

/* 工作区 */
.sunshine-workspace {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.workspace-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
  padding-bottom: 16px;
  border-bottom: 1px solid #e5e7eb;
}

.workspace-header h3 {
  font-size: 20px;
  font-weight: 600;
  color: #1f2937;
}

.workspace-actions {
  display: flex;
  gap: 12px;
}

/* 创意生成器 */
.idea-generator {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.generator-inputs {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.input-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.input-group label {
  font-weight: 500;
  color: #374151;
}

.input-group input,
.input-group select,
.input-group textarea {
  padding: 8px 12px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  font-size: 14px;
}

.keywords-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  padding: 8px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  min-height: 42px;
}

.keyword-tag {
  background-color: #eff6ff;
  color: #1d4ed8;
  padding: 4px 8px;
  border-radius: 4px;
  display: flex;
  align-items: center;
  gap: 4px;
}

.keyword-remove {
  background: none;
  border: none;
  color: #1d4ed8;
  cursor: pointer;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.keyword-input {
  border: none;
  background: transparent;
  outline: none;
  flex: 1;
  min-width: 100px;
}

.generator-output {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 16px;
}

.generator-output h4 {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 16px;
  color: #1f2937;
}

.ideas-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.idea-item {
  background-color: #fff;
  border-radius: 6px;
  padding: 12px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.idea-content {
  flex: 1;
  line-height: 1.5;
  color: #4b5563;
}

.idea-actions {
  display: flex;
  gap: 8px;
}

.btn-icon {
  width: 32px;
  height: 32px;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  background-color: #f3f4f6;
  color: #374151;
  cursor: pointer;
  transition: background-color 0.2s;
}

.btn-icon:hover {
  background-color: #e5e7eb;
}

/* 文本分析器 */
.text-analyzer {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.analyzer-input textarea {
  width: 100%;
  resize: vertical;
}

.analysis-tabs {
  display: flex;
  gap: 12px;
  margin-bottom: 16px;
}

.tab-button {
  padding: 8px 16px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  background-color: #fff;
  color: #374151;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s;
}

.tab-button:hover {
  background-color: #f3f4f6;
}

.tab-button.active {
  background-color: #2563eb;
  color: white;
  border-color: #2563eb;
}

.analysis-content {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 16px;
}

/* 情感分析 */
.sentiment-chart {
  margin-bottom: 24px;
}

.sentiment-bars {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.sentiment-item {
  display: flex;
  align-items: center;
  gap: 12px;
}

.sentiment-label {
  width: 50px;
  font-weight: 500;
}

.sentiment-bar {
  flex: 1;
  height: 20px;
  background-color: #e5e7eb;
  border-radius: 10px;
  overflow: hidden;
}

.sentiment-fill {
  height: 100%;
  border-radius: 10px;
}

.sentiment-item.positive .sentiment-fill {
  background-color: #10b981;
}

.sentiment-item.neutral .sentiment-fill {
  background-color: #6b7280;
}

.sentiment-item.negative .sentiment-fill {
  background-color: #ef4444;
}

.sentiment-value {
  width: 50px;
  text-align: right;
  font-weight: 500;
}

.sentiment-summary {
  background-color: #fff;
  border-radius: 8px;
  padding: 16px;
}

.sentiment-summary h4 {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 8px;
  color: #1f2937;
}

.sentiment-summary p {
  color: #4b5563;
  line-height: 1.5;
}

/* 关键词云 */
.keywords-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
  padding: 20px;
  background-color: #fff;
  border-radius: 8px;
}

.keyword-cloud-item {
  padding: 8px 12px;
  background-color: #eff6ff;
  color: #1d4ed8;
  border-radius: 4px;
  font-weight: 500;
  transition: all 0.2s;
}

.keyword-cloud-item:hover {
  background-color: #2563eb;
  color: white;
  transform: scale(1.05);
}

/* 文本摘要 */
.summary-analysis {
  background-color: #fff;
  border-radius: 8px;
  padding: 16px;
}

.summary-content h4 {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 8px;
  color: #1f2937;
}

.summary-content p {
  color: #4b5563;
  line-height: 1.5;
}
</style>
