<template>
  <section class="rules-section">
    <div class="page-header">
      <h1 class="page-title">规则系统</h1>
      <p class="page-description">基于规则的智能决策引擎，支持复杂业务逻辑的自动化处理</p>
    </div>

    <div class="rules-content">
      <div class="rules-overview">
        <div class="rules-intro">
          <div class="intro-text">
            <h2>规则系统概述</h2>
            <p>规则系统是一个强大的业务规则引擎，允许您定义和管理复杂的业务规则，实现自动化决策和流程控制。通过直观的界面和丰富的功能，您可以轻松构建和管理各类业务规则。</p>
          </div>

          <div class="intro-features">
            <div class="feature-item">
              <i class="fas fa-check-circle"></i>
              <span>可视化规则编辑器</span>
            </div>
            <div class="feature-item">
              <i class="fas fa-check-circle"></i>
              <span>条件分支逻辑</span>
            </div>
            <div class="feature-item">
              <i class="fas fa-check-circle"></i>
              <span>规则版本管理</span>
            </div>
            <div class="feature-item">
              <i class="fas fa-check-circle"></i>
              <span>规则执行日志</span>
            </div>
          </div>
        </div>

        <div class="rules-stats">
          <div class="stat-card">
            <div class="stat-value">24</div>
            <div class="stat-label">规则总数</div>
          </div>
          <div class="stat-card">
            <div class="stat-value">18</div>
            <div class="stat-label">已激活</div>
          </div>
          <div class="stat-card">
            <div class="stat-value">6</div>
            <div class="stat-label">待审核</div>
          </div>
          <div class="stat-card">
            <div class="stat-value">1,542</div>
            <div class="stat-label">今日执行</div>
          </div>
        </div>
      </div>

      <div class="rules-list">
        <div class="list-header">
          <h3>规则列表</h3>
          <div class="list-actions">
            <button class="btn btn-primary"><i class="fas fa-plus"></i> 新建规则</button>
            <button class="btn btn-secondary"><i class="fas fa-filter"></i> 筛选</button>
          </div>
        </div>

        <div class="rules-table">
          <table>
            <thead>
              <tr>
                <th>规则名称</th>
                <th>状态</th>
                <th>最后执行</th>
                <th>执行次数</th>
                <th>操作</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>订单审核流程</td>
                <td><span class="status active">激活</span></td>
                <td>2024-01-15 10:30</td>
                <td>1,248</td>
                <td>
                  <button class="btn-icon"><i class="fas fa-edit"></i></button>
                  <button class="btn-icon"><i class="fas fa-play"></i></button>
                  <button class="btn-icon"><i class="fas fa-trash"></i></button>
                </td>
              </tr>
              <tr>
                <td>客户信用评估</td>
                <td><span class="status active">激活</span></td>
                <td>2024-01-15 09:15</td>
                <td>856</td>
                <td>
                  <button class="btn-icon"><i class="fas fa-edit"></i></button>
                  <button class="btn-icon"><i class="fas fa-play"></i></button>
                  <button class="btn-icon"><i class="fas fa-trash"></i></button>
                </td>
              </tr>
              <tr>
                <td>库存预警规则</td>
                <td><span class="status pending">待审核</span></td>
                <td>从未执行</td>
                <td>0</td>
                <td>
                  <button class="btn-icon"><i class="fas fa-eye"></i></button>
                  <button class="btn-icon"><i class="fas fa-check"></i></button>
                  <button class="btn-icon"><i class="fas fa-times"></i></button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'RulesSection'
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
  gap: 24px;
}

.rules-intro {
  flex: 1;
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

/* 规则统计 */
.rules-stats {
  width: 320px;
  flex-shrink: 0;
}

.stat-card {
  background-color: #fff;
  border-radius: 8px;
  padding: 16px;
  margin-bottom: 16px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  gap: 16px;
}

.stat-value {
  font-size: 24px;
  font-weight: 600;
  color: #2563eb;
}

.stat-label {
  color: #4b5563;
  font-size: 14px;
}

/* 规则列表 */
.list-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}

.list-header h3 {
  font-size: 20px;
  font-weight: 600;
  color: #1f2937;
}

.list-actions {
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

/* 规则表格 */
.rules-table {
  background-color: #fff;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

table {
  width: 100%;
  border-collapse: collapse;
}

thead {
  background-color: #f9fafb;
}

th {
  padding: 12px 16px;
  text-align: left;
  font-weight: 600;
  color: #374151;
  border-bottom: 1px solid #e5e7eb;
}

td {
  padding: 16px;
  border-bottom: 1px solid #f3f4f6;
}

.status {
  display: inline-block;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}

.status.active {
  background-color: #d1fae5;
  color: #065f46;
}

.status.pending {
  background-color: #fef3c7;
  color: #92400e;
}
</style>
