<template>
  <aside class="sidebar">
    <!-- 导航菜单 -->
    <nav class="nav-menu">
      <ul>
        <li
          class="menu-item"
          :class="{ active: currentPage === 'home' }"
          data-page="home"
          @click="handleItemClick('home')"
        >
          <i class="fas fa-home"></i>
          <span>前言</span>
        </li>

        <li
          class="menu-item"
          :class="{ active: currentPage === 'automation' }"
          data-page="automation"
          @click="handleItemClick('automation')"
        >
          <i class="fas fa-code"></i>
          <span>脚本自动化</span>
        </li>

        <li
          class="menu-item has-submenu"
          :class="{ active: currentPage === 'ai-modules' }"
          data-page="ai-modules"
          @click="handleItemClick('ai-modules')"
        >
          <i class="fas fa-robot"></i>
          <span>AI 模块</span>
          <i
            class="fas fa-chevron-down chevron"
            :class="{ rotate: isSubmenuOpen('ai-modules') }"
          ></i>
        </li>

        <!-- AI模块的子菜单 -->
        <li class="submenu" :class="{ show: isSubmenuOpen('ai-modules') }">
          <ul>
            <li
              class="submenu-item"
              :class="{ active: currentPage === 'rules' }"
              data-page="rules"
              @click.stop="handleSubItemClick('rules')"
            >
              规则系统
            </li>
            <li
              class="submenu-item"
              :class="{ active: currentPage === 'attendance' }"
              data-page="attendance"
              @click.stop="handleSubItemClick('attendance')"
            >
              外包考勤系统
            </li>
            <li
              class="submenu-item"
              :class="{ active: currentPage === 'sunshine' }"
              data-page="sunshine"
              @click.stop="handleSubItemClick('sunshine')"
            >
              阳光灵思图
            </li>
          </ul>
        </li>

        <li
          class="menu-item"
          :class="{ active: currentPage === 'plugins' }"
          data-page="plugins"
          @click="handleItemClick('plugins')"
        >
          <i class="fas fa-puzzle-piece"></i>
          <span>展示插件</span>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<script>
export default {
  name: 'SidebarMenu',
  props: {
    currentPage: {
      type: String,
      default: 'home'
    }
  },
  data() {
    return {
      submenuOpenState: {
        'ai-modules': false
      }
    }
  },
  methods: {
    handleItemClick(page) {
      // 移除所有菜单项的active类
      document
        .querySelectorAll('.menu-item')
        .forEach((i) => i.classList.remove('active'))

      // 为当前点击的菜单项添加active类
      event.currentTarget.classList.add('active')

      // 如果有子菜单，切换显示状态
      if (event.currentTarget.classList.contains('has-submenu')) {
        const chevron = event.currentTarget.querySelector('.chevron')
        const submenu = event.currentTarget.nextElementSibling

        if (chevron) {
          chevron.classList.toggle('rotate')
        }

        if (submenu && submenu.classList.contains('submenu')) {
          submenu.classList.toggle('show')
        }
      }

      // 处理页面切换
      this.$emit('page-change', page)
    },

    handleSubItemClick(page) {
      // 移除所有菜单项的active类
      document
        .querySelectorAll('.menu-item')
        .forEach((i) => i.classList.remove('active'))

      // 找到父级菜单项并添加active类
      const parentMenuItem = document.querySelector('[data-page="ai-modules"]')
      if (parentMenuItem) {
        parentMenuItem.classList.add('active')
      }

      // 处理页面切换
      this.$emit('page-change', page)
    },

    toggleSubmenu(menuId) {
      this.submenuOpenState[menuId] = !this.submenuOpenState[menuId]
    },

    isSubmenuOpen(menuId) {
      return this.submenuOpenState[menuId] || false
    }
  }
}
</script>

<style scoped>
/* 左侧菜单 */
.sidebar {
  width: 256px;
  background-color: #fff;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  position: fixed;
  height: 100%;
  overflow-y: auto;
}

.logo-container {
  padding: 24px;
  display: flex;
  justify-content: center;
}

.logo-container img {
  max-width: 100%;
  height: auto;
}

/* 导航菜单 */
.nav-menu {
  margin-top: 24px;
}

.menu-item {
  padding: 16px 24px;
  display: flex;
  align-items: center;
  cursor: pointer;
  transition: all 0.2s;
  border-left: 3px solid transparent;
}

.menu-item:hover {
  background-color: rgba(0, 0, 0, 0.03);
}

.menu-item.active {
  background-color: rgba(37, 99, 235, 0.1);
  border-left-color: #2563eb;
}

.menu-item i {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #4b5563;
}

.menu-item span {
  margin-left: 12px;
  color: #1f2937;
}

.menu-item .chevron {
  margin-left: auto;
  transition: transform 0.2s;
}

.menu-item.active .chevron.rotate {
  transform: rotate(180deg);
}

/* 子菜单 */
.submenu {
  background-color: #f3f4f6;
  display: none;
}

.submenu.show {
  display: block;
}

.submenu-item {
  padding: 12px 48px;
  cursor: pointer;
  transition: all 0.2s;
}

.submenu-item:hover {
  background-color: #e5e7eb;
}

.submenu-item.active {
  background-color: rgba(37, 99, 235, 0.1);
  border-left: 3px solid #2563eb;
  padding-left: 45px;
}
</style>
