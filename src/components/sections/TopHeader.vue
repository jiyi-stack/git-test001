<template>
  <header class="header">
    <div class="logo">
      <img src="@/assets/aiSpt.gif" alt="Logo" />
      <span>晓阳AI | 帮助中心</span>
    </div>
    <div class="search">
      <input
        type="text"
        placeholder="请输入关键字"
        v-model="searchQuery"
        @keyup.enter="performSearch"
      />
      <button @click="performSearch">搜索</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'TopHeader',
  data() {
    return {
      searchQuery: ''
    }
  },
  methods: {
    performSearch() {
      if (this.searchQuery.trim()) {
        this.$emit('search', this.searchQuery.trim())
      }
    }
  }
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 24px;
  height: 60px;
  border-bottom: 1px solid #eee;
  background: #fff;
}

.logo {
  display: flex;
  align-items: center;
}

.logo img {
  width: 40px;
  height: auto;
  margin-right: 12px;
  background: #0b2357;
  border-radius: 6px;
}

.logo span {
  font-size: 16px;
  font-weight: 600;
  color: #1f2937;
}

.search {
  display: flex;
  align-items: center;
  background: #f5f5f5;
  border-radius: 5px;
  padding: 6px 12px;
  width: 280px;
}

.search input {
  flex: 1;
  border: none;
  background: none;
  outline: none;
  font-size: 14px;
}

.search button {
  border: none;
  background: none;
  color: #2563eb;
  cursor: pointer;
  padding: 4px 8px;
  border-radius: 4px;
}
</style>
