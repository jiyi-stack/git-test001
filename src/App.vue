<template>
  <div class="main-container">
    <!-- 左侧菜单 -->
    <SidebarMenu :current-page="currentPage" @page-change="handlePageChange" />

    <!-- 右侧内容区 -->
    <MainContent :current-page="currentPage" @page-change="handlePageChange" />
  </div>
</template>

<script>
import SidebarMenu from './components/SidebarMenu.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
    SidebarMenu,
    MainContent
  },
  data() {
    return {
      currentPage: 'home' // 默认显示首页
    }
  },
  methods: {
    handlePageChange(page) {
      this.currentPage = page
      // 这里可以添加页面切换逻辑，例如路由导航
    }
  }
}
</script>

<style>
/* 基础样式 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
    'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  color: #201f23;
  background-color: #f9fafb;
}

/* 主布局 */
.main-container {
  display: flex;
  min-height: 100vh;
}
</style>
