<template>
  <section class="attendance-section">
    <div class="page-header">
      <h1 class="page-title">外包考勤系统</h1>
      <p class="page-description">
        智能考勤管理，支持多种考勤规则和自动化处理流程
      </p>
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
</style>
