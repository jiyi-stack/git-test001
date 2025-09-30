<template>
  <section class="attendance-section">
    <header class="pageHeader">
      <h1 class="pageTitle">外包考勤系统</h1>
      <p class="pageDescription">
        智能考勤管理，支持多种考勤规则和自动化处理流程
      </p>
    </header>

    <!-- 数据展示，可不要 -->
    <div class="overviewCards">
      <div
        v-for="(card, index) in overviewCards"
        :key="index"
        class="overviewCard"
      >
        <div class="cardIcon">
          <i :class="card.icon"></i>
        </div>
        <div class="cardContent">
          <div class="cardValue">{{ card.value }}</div>
          <div class="cardLabel">{{ card.label }}</div>
        </div>
      </div>
    </div>

    <!-- 考勤规则说明 -->
    <div class="attendanceRules">
      <div class="main-content">
        <FontDecration>操作步骤</FontDecration>
      </div>
    </div>
  </section>
</template>

<script>
import FontDecration from '@/components/FontDecration.vue'

export default {
  name: 'AttendanceSection',
  components: {
    FontDecration
  },
  data() {
    return {
      activeTab: 'daily',
      overviewCards: [
        {
          icon: 'fas fa-users',
          value: '19',
          label: '外包人员'
        },
        {
          icon: 'fas fa-calendar-day',
          value: '21',
          label: '本月出勤天数'
        },
        {
          icon: 'fas fa-clock',
          value: '8.5%',
          label: '考勤异常率'
        },
        {
          icon: 'fas fa-exclamation-triangle',
          value: '3',
          label: '考勤异常次数'
        }
      ]
    }
  }
}
</script>

<style scoped>
/* 页面标题 */
.pageHeader {
  margin-bottom: 32px;
}

.pageHeader h1 {
  font-size: 28px;
  margin-bottom: 8px;
  color: #1f2937;
}

.pageDescription {
  color: #6b7280;
  font-size: 16px;
}

/* 考勤内容 */
.overviewCards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
}

.overviewCard {
  background-color: #fff;
  border-radius: 8px;
  padding: 16px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  gap: 16px;
}

.cardIcon {
  width: 48px;
  height: 48px;
  background-color: rgba(37, 99, 235, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.cardIcon i {
  font-size: 24px;
  color: #2563eb;
}

.cardValue {
  font-size: 24px;
  font-weight: 600;
  color: #1f2937;
}

.cardLabel {
  color: #6b7280;
  font-size: 14px;
}

.main-content {
  margin-top: 28px;
  flex: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}
</style>
