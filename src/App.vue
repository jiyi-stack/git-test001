<template>
  <div class="MainContainer">
    <!-- 顶部导航栏 -->
    <TopHeader @search="handleSearch" />

    <!-- 下方内容区域 -->
    <div class="content-wrapper">
      <!-- 左侧菜单 -->
      <SidebarMenu
        :current-page="currentPage"
        @page-change="handlePageChange"
      />

      <!-- 右侧内容区 -->
      <MainContent
        :current-page="currentPage"
        @page-change="handlePageChange"
      />
    </div>
  </div>
</template>

<script>
import SidebarMenu from './components/SidebarMenu.vue'
import MainContent from './components/MainContent.vue'
import TopHeader from './components/sections/TopHeader.vue'

export default {
  name: 'App',
  components: {
    SidebarMenu,
    MainContent,
    TopHeader
  },
  data() {
    return {
      currentPage: 'home' // 默认显示首页
    }
  },
  methods: {
    handlePageChange(page) {
      this.currentPage = page
      // 这里添加页面路由导航
    },
    handleSearch(query) {
      // 处理搜索功能
      console.log('搜索关键词:', query)
      // 这里可以添加实际的搜索逻辑，比如：
      // 1. 过滤页面内容
      // 2. 高亮显示匹配的文本
      // 3. 跳转到包含搜索结果的页面
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
.MainContainer {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.content-wrapper {
  display: flex;
  flex: 1;
  overflow: hidden;
}
</style>
