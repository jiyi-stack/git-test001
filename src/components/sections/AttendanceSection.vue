<template>
  <section class="attendance-section">
    <div class="page-header">
      <h1 class="page-title">外包考勤系统</h1>
      <p class="page-description">智能考勤管理，支持多种考勤规则和自动化处理流程</p>
    </div>

    <div class="attendance-content">
      <div class="attendance-overview">
        <div class="overview-cards">
          <div class="overview-card">
            <div class="card-icon">
              <i class="fas fa-users"></i>
            </div>
            <div class="card-content">
              <div class="card-value">156</div>
              <div class="card-label">外包人员</div>
            </div>
          </div>

          <div class="overview-card">
            <div class="card-icon">
              <i class="fas fa-calendar-day"></i>
            </div>
            <div class="card-content">
              <div class="card-value">142</div>
              <div class="card-label">今日出勤</div>
            </div>
          </div>

          <div class="overview-card">
            <div class="card-icon">
              <i class="fas fa-clock"></i>
            </div>
            <div class="card-content">
              <div class="card-value">98.5%</div>
              <div class="card-label">出勤率</div>
            </div>
          </div>

          <div class="overview-card">
            <div class="card-icon">
              <i class="fas fa-exclamation-triangle"></i>
            </div>
            <div class="card-content">
              <div class="card-value">14</div>
              <div class="card-label">异常考勤</div>
            </div>
          </div>
        </div>
      </div>

      <div class="attendance-tabs">
        <div class="tab-buttons">
          <button
            class="tab-button"
            :class="{ active: activeTab === 'daily' }"
            @click="activeTab = 'daily'"
          >
            考勤日报
          </button>
          <button
            class="tab-button"
            :class="{ active: activeTab === 'monthly' }"
            @click="activeTab = 'monthly'"
          >
            考勤月报
          </button>
          <button
            class="tab-button"
            :class="{ active: activeTab === 'settings' }"
            @click="activeTab = 'settings'"
          >
            考勤设置
          </button>
        </div>

        <div class="tab-content">
          <!-- 考勤日报 -->
          <div v-if="activeTab === 'daily'" class="daily-attendance">
            <div class="daily-header">
              <div class="date-selector">
                <button class="btn-icon"><i class="fas fa-chevron-left"></i></button>
                <span>2024年1月15日</span>
                <button class="btn-icon"><i class="fas fa-chevron-right"></i></button>
              </div>
              <div class="daily-actions">
                <button class="btn btn-secondary"><i class="fas fa-download"></i> 导出报表</button>
                <button class="btn btn-primary"><i class="fas fa-file-excel"></i> 下载表格</button>
              </div>
            </div>

            <div class="daily-summary">
              <div class="summary-card">
                <h3>今日考勤概况</h3>
                <div class="summary-stats">
                  <div class="stat-item">
                    <div class="stat-value">142</div>
                    <div class="stat-label">正常出勤</div>
                  </div>
                  <div class="stat-item">
                    <div class="stat-value">8</div>
                    <div class="stat-label">迟到</div>
                  </div>
                  <div class="stat-item">
                    <div class="stat-value">3</div>
                    <div class="stat-label">早退</div>
                  </div>
                  <div class="stat-item">
                    <div class="stat-value">3</div>
                    <div class="stat-label">缺勤</div>
                  </div>
                </div>
              </div>
            </div>

            <div class="attendance-table">
              <table>
                <thead>
                  <tr>
                    <th>姓名</th>
                    <th>部门</th>
                    <th>签到时间</th>
                    <th>签退时间</th>
                    <th>工作时长</th>
                    <th>状态</th>
                    <th>操作</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>张三</td>
                    <td>开发部</td>
                    <td>08:55</td>
                    <td>18:10</td>
                    <td>9小时15分</td>
                    <td><span class="status normal">正常</span></td>
                    <td>
                      <button class="btn-icon"><i class="fas fa-eye"></i></button>
                    </td>
                  </tr>
                  <tr>
                    <td>李四</td>
                    <td>测试部</td>
                    <td>09:15</td>
                    <td>18:30</td>
                    <td>9小时15分</td>
                    <td><span class="status late">迟到</span></td>
                    <td>
                      <button class="btn-icon"><i class="fas fa-eye"></i></button>
                    </td>
                  </tr>
                  <tr>
                    <td>王五</td>
                    <td>设计部</td>
                    <td>08:50</td>
                    <td>17:45</td>
                    <td>8小时55分</td>
                    <td><span class="status early">早退</span></td>
                    <td>
                      <button class="btn-icon"><i class="fas fa-eye"></i></button>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <!-- 考勤月报 -->
          <div v-if="activeTab === 'monthly'" class="monthly-attendance">
            <div class="monthly-header">
              <div class="date-selector">
                <button class="btn-icon"><i class="fas fa-chevron-left"></i></button>
                <span>2024年1月</span>
                <button class="btn-icon"><i class="fas fa-chevron-right"></i></button>
              </div>
              <div class="monthly-actions">
                <button class="btn btn-secondary"><i class="fas fa-filter"></i> 筛选</button>
                <button class="btn btn-primary"><i class="fas fa-download"></i> 导出报表</button>
              </div>
            </div>

            <div class="monthly-summary">
              <div class="summary-grid">
                <div class="summary-card">
                  <div class="card-header">
                    <h4>工时统计</h4>
                  </div>
                  <div class="card-body">
                    <div class="chart-placeholder">
                      <i class="fas fa-chart-bar"></i>
                      <span>工时统计图表</span>
                    </div>
                  </div>
                </div>

                <div class="summary-card">
                  <div class="card-header">
                    <h4>出勤率分析</h4>
                  </div>
                  <div class="card-body">
                    <div class="chart-placeholder">
                      <i class="fas fa-chart-pie"></i>
                      <span>出勤率分析图表</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="monthly-table">
              <table>
                <thead>
                  <tr>
                    <th>姓名</th>
                    <th>部门</th>
                    <th>应出勤天数</th>
                    <th>实际出勤</th>
                    <th>出勤率</th>
                    <th>总工时</th>
                    <th>加班</th>
                    <th>调休</th>
                    <th>操作</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>张三</td>
                    <td>开发部</td>
                    <td>22</td>
                    <td>21</td>
                    <td>95.5%</td>
                    <td>176小时</td>
                    <td>12小时</td>
                    <td>0小时</td>
                    <td>
                      <button class="btn-icon"><i class="fas fa-eye"></i></button>
                      <button class="btn-icon"><i class="fas fa-download"></i></button>
                    </td>
                  </tr>
                  <tr>
                    <td>李四</td>
                    <td>测试部</td>
                    <td>22</td>
                    <td>20</td>
                    <td>90.9%</td>
                    <td>168小时</td>
                    <td>8小时</td>
                    <td>2小时</td>
                    <td>
                      <button class="btn-icon"><i class="fas fa-eye"></i></button>
                      <button class="btn-icon"><i class="fas fa-download"></i></button>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <!-- 考勤设置 -->
          <div v-if="activeTab === 'settings'" class="attendance-settings">
            <div class="settings-form">
              <h3>考勤规则设置</h3>

              <div class="form-group">
                <label>工作时间</label>
                <div class="time-inputs">
                  <div class="time-input">
                    <span>开始时间</span>
                    <input type="time" value="09:00">
                  </div>
                  <div class="time-input">
                    <span>结束时间</span>
                    <input type="time" value="18:00">
                  </div>
                </div>
              </div>

              <div class="form-group">
                <label>迟到规则</label>
                <div class="rule-inputs">
                  <div class="rule-input">
                    <span>迟到阈值(分钟)</span>
                    <input type="number" value="15">
                  </div>
                  <div class="rule-input">
                    <span>迟到处罚</span>
                    <select>
                      <option>无处罚</option>
                      <option>扣减当日工资</option>
                      <option>记录迟到次数</option>
                    </select>
                  </div>
                </div>
              </div>

              <div class="form-group">
                <label>早退规则</label>
                <div class="rule-inputs">
                  <div class="rule-input">
                    <span>早退阈值(分钟)</span>
                    <input type="number" value="30">
                  </div>
                  <div class="rule-input">
                    <span>早退处罚</span>
                    <select>
                      <option>无处罚</option>
                      <option>扣减当日工资</option>
                      <option>记录早退次数</option>
                    </select>
                  </div>
                </div>
              </div>

              <div class="form-group">
                <label>考假设置</label>
                <div class="holiday-inputs">
                  <div class="holiday-input">
                    <span>年假天数</span>
                    <input type="number" value="10">
                  </div>
                  <div class="holiday-input">
                    <span>病假天数</span>
                    <input type="number" value="5">
                  </div>
                  <div class="holiday-input">
                    <span>事假天数</span>
                    <input type="number" value="3">
                  </div>
                </div>
              </div>

              <div class="form-actions">
                <button class="btn btn-secondary">重置</button>
                <button class="btn btn-primary">保存设置</button>
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
  name: 'AttendanceSection',
  data() {
    return {
      activeTab: 'daily'
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

/* 考勤内容 */
.attendance-content {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

/* 考勤概述 */
.attendance-overview {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.overview-cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
}

.overview-card {
  background-color: #fff;
  border-radius: 8px;
  padding: 16px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  gap: 16px;
}

.card-icon {
  width: 48px;
  height: 48px;
  background-color: rgba(37, 99, 235, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-icon i {
  font-size: 24px;
  color: #2563eb;
}

.card-value {
  font-size: 24px;
  font-weight: 600;
  color: #1f2937;
}

.card-label {
  color: #6b7280;
  font-size: 14px;
}

/* 考勤标签页 */
.attendance-tabs {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.tab-buttons {
  display: flex;
  border-bottom: 1px solid #e5e7eb;
}

.tab-button {
  padding: 12px 24px;
  background: none;
  border: none;
  font-size: 16px;
  font-weight: 500;
  color: #6b7280;
  cursor: pointer;
  transition: all 0.2s;
}

.tab-button:hover {
  color: #374151;
  background-color: #f9fafb;
}

.tab-button.active {
  color: #2563eb;
  border-bottom: 2px solid #2563eb;
}

.tab-content {
  padding: 24px;
}

/* 按钮样式 */
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

/* 考勤日报 */
.daily-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
}

.date-selector {
  display: flex;
  align-items: center;
  gap: 12px;
}

.date-selector span {
  font-weight: 500;
}

.daily-actions {
  display: flex;
  gap: 12px;
}

.daily-summary {
  margin-bottom: 24px;
}

.summary-card {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 20px;
}

.summary-card h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.summary-stats {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
}

.stat-item {
  text-align: center;
}

.stat-value {
  font-size: 24px;
  font-weight: 600;
  color: #2563eb;
}

.stat-label {
  color: #6b7280;
  font-size: 14px;
}

/* 考勤表格 */
.attendance-table {
  overflow-x: auto;
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

.status.normal {
  background-color: #d1fae5;
  color: #065f46;
}

.status.late {
  background-color: #fee2e2;
  color: #991b1b;
}

.status.early {
  background-color: #fef3c7;
  color: #92400e;
}

/* 考勤月报 */
.monthly-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
}

.monthly-actions {
  display: flex;
  gap: 12px;
}

.monthly-summary {
  margin-bottom: 24px;
}

.summary-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.chart-placeholder {
  height: 200px;
  background-color: #f3f4f6;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #9ca3af;
}

.chart-placeholder i {
  font-size: 32px;
  margin-bottom: 8px;
}

/* 考勤设置 */
.settings-form {
  max-width: 600px;
}

.settings-form h3 {
  font-size: 20px;
  margin-bottom: 24px;
  color: #1f2937;
}

.form-group {
  margin-bottom: 24px;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  font-weight: 500;
  color: #374151;
}

.time-inputs,
.rule-inputs,
.holiday-inputs {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.time-input,
.rule-input,
.holiday-input {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.time-input span,
.rule-input span,
.holiday-input span {
  color: #6b7280;
  font-size: 14px;
}

.time-input input,
.rule-input input,
.holiday-input input,
.rule-input select {
  padding: 8px 12px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  font-size: 14px;
}

.form-actions {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
  margin-top: 32px;
}
</style>
