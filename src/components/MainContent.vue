<template>
  <main class="contentWrapper">
    <!-- 首页内容 -->
    <WelcomeSection v-if="currentPage === 'home'" />

    <!-- 脚本自动化页面 -->
    <AutomationSection v-if="currentPage === 'automation'" />

    <!-- 展示插件页面 -->
    <PluginTable v-if="currentPage === 'plugins'" />

    <!-- AI模块页面 -->
    <AIModulesSection v-if="currentPage === 'ai-modules'" />

    <!-- 规则系统页面 -->
    <RulesSection v-if="currentPage === 'rules'" />

    <!-- 外包考勤系统页面 -->
    <AttendanceSection v-if="currentPage === 'attendance'" />

    <!-- 阳光灵思图页面 -->
    <SunshineSection v-if="currentPage === 'sunshine'" />

    <!-- 最近更新 -->
    <UpdatesSection v-if="currentPage === 'home'" />
  </main>
</template>

<script>
import WelcomeSection from './sections/WelcomeSection.vue'
import AutomationSection from './sections/AutomationSection.vue'
import PluginTable from './PluginTable.vue'
import AIModulesSection from './sections/AIModulesSection.vue'
import RulesSection from './sections/RulesSection.vue'
import AttendanceSection from './sections/AttendanceSection.vue'
import SunshineSection from './sections/SunshineSection.vue'
import UpdatesSection from './sections/UpdatesSection.vue'

export default {
  name: 'MainContent',
  props: {
    currentPage: {
      type: String,
      default: 'home'
    }
  },
  components: {
    WelcomeSection,
    AutomationSection,
    PluginTable,
    AIModulesSection,
    RulesSection,
    AttendanceSection,
    SunshineSection,
    UpdatesSection
  }
}
</script>

<style scoped>
/* 右侧内容区 */
.contentWrapper {
  margin-left: 256px;
  flex: 1;
  padding: 26px;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .contentWrapper {
    margin-left: 0;
    padding: 16px;
  }
}
</style>
