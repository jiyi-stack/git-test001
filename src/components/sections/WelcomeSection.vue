<template>
  <section class="welcome">
    <h4>晓阳AI是什么？</h4>
    <p>
      本平台是一款集成了脚本自动化与AI大模型的综合工具，
      减少重复性劳动，帮助用户提高工作效率；对接内部系统，利用AI大模型技术处理综合性问题，实现业务流程的智能化升级。
    </p>
    <div class="features">
      <div class="card">
        <div class="icon purple">
          <i class="fas fa-code"></i>
        </div>
        <h3>脚本自动化</h3>
        <p>
          强大的脚本录制与执行功能，轻松实现重复性工作自动化，提升效率降低错误。
        </p>
      </div>
      <div class="card">
        <div class="icon yellow">
          <i class="fas fa-robot"></i>
        </div>
        <h3>AI 模块</h3>
        <p>
          对接多个系统，包含规则系统、考勤管理、智能分析等，助力AI协助工作，提升效率。
        </p>
      </div>
      <div class="card">
        <div class="icon blue">
          <i class="fas fa-puzzle-piece"></i>
        </div>
        <h3>展示插件</h3>
        <p>丰富的插件生态，满足多样化的业务需求，支持自定义开发和场景扩展。</p>
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
.welcome h4 {
  font-size: 20px;
  color: #374151;
  margin-bottom: 16px;
}

.welcome > p {
  color: #4b5563;
  line-height: 1.6;
  margin-bottom: 24px;
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
  padding: 0 32px;
}

.card {
  background: #ffffff;
  border-radius: 8px;
  padding: 24px;
  transition: transform 0.2s;
  box-shadow: 0 4px 20px rgba(133, 133, 143, 0.08);
}

.card:hover {
  transform: translateY(-5px);
  background: #fbfcfd;
}

.icon {
  width: 48px;
  height: 48px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 16px;
}

.icon i {
  font-size: 24px;
}

.purple {
  background: rgba(139, 92, 246, 0.1);
}

.purple i {
  color: #8b5cf6;
}

.yellow {
  background: rgba(245, 158, 11, 0.1);
}

.yellow i {
  color: #f59e0b;
}

.blue {
  background: rgba(37, 99, 235, 0.1);
}

.blue i {
  color: #2563eb;
}

.card h3 {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 12px;
  color: #1f2937;
}

.card p {
  color: #4b5563;
  line-height: 1.5;
}
</style>
