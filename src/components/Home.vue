<template>
  <aside class="sidebar">
    <nav class="nav-menu">
      <ul>
        <li
          v-for="item in menuItems"
          :key="item.page"
          :class="[
            'menu-item',
            { active: activePage === item.page, 'has-submenu': item.submenu }
          ]"
          :data-page="item.page"
          @click="handleMenuItemClick(item)"
        >
          <i :class="item.icon"></i>
          <span>{{ item.title }}</span>
          <i
            v-if="item.submenu"
            :class="[
              'fas',
              'fa-chevron-down',
              'chevron',
              { rotated: isSubmenuOpen(item.page) }
            ]"
          ></i>
        </li>

        <!-- 子菜单 -->
        <template v-for="item in menuItems" :key="`${item.page}-submenu`">
          <li v-if="item.submenu && isSubmenuOpen(item.page)" class="submenu">
            <ul>
              <li
                v-for="subItem in item.submenu"
                :key="subItem.page"
                :class="[
                  'submenu-item',
                  { active: activePage === subItem.page }
                ]"
                :data-page="subItem.page"
                @click="handleSubmenuItemClick(subItem)"
              >
                {{ subItem.title }}
              </li>
            </ul>
          </li>
        </template>
      </ul>
    </nav>
  </aside>
</template>

<script>
export default {
  name: 'SidebarMenu',
  data() {
    return {
      activePage: 'home',
      openSubmenus: [],
      menuItems: [
        {
          page: 'home',
          icon: 'fas fa-home',
          title: '前言'
        },
        {
          page: 'automation',
          icon: 'fas fa-code',
          title: '脚本自动化'
        },
        {
          page: 'ai-modules',
          icon: 'fas fa-robot',
          title: 'AI 模块',
          submenu: [
            { page: 'rules', title: '规则系统' },
            { page: 'attendance', title: '外包考勤系统' },
            { page: 'sunshine', title: '阳光灵思图' }
          ]
        },
        {
          page: 'plugins',
          icon: 'fas fa-puzzle-piece',
          title: '展示插件'
        }
      ]
    }
  },
  methods: {
    handleMenuItemClick(item) {
      if (item.submenu) {
        this.toggleSubmenu(item.page)
      } else {
        this.activePage = item.page
        this.$emit('page-change', item.page)
      }
    },
    handleSubmenuItemClick(subItem) {
      this.activePage = subItem.page
      this.$emit('page-change', subItem.page)
    },
    toggleSubmenu(page) {
      const index = this.openSubmenus.indexOf(page)
      if (index > -1) {
        this.openSubmenus.splice(index, 1)
      } else {
        this.openSubmenus.push(page)
      }
    },
    isSubmenuOpen(page) {
      return this.openSubmenus.includes(page)
    }
  }
}
</script>

<style scoped>
.sidebar {
  width: 250px;
  background-color: #f8f9fa;
  height: 100vh;
  overflow-y: auto;
  transition: all 0.3s;
}

.nav-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu-item {
  display: flex;
  align-items: center;
  padding: 15px 20px;
  cursor: pointer;
  transition: background-color 0.3s;
  position: relative;
}

.menu-item:hover {
  background-color: #e9ecef;
}

.menu-item.active {
  background-color: #dee2e6;
  font-weight: bold;
}

.menu-item i {
  margin-right: 10px;
  width: 20px;
  text-align: center;
}

.menu-item span {
  flex-grow: 1;
}

.has-submenu {
  justify-content: space-between;
}

.chevron {
  transition: transform 0.3s;
}

.chevron.rotated {
  transform: rotate(180deg);
}

.submenu {
  background-color: #e9ecef;
}

.submenu ul {
  list-style: none;
  padding: 0;
}

.submenu-item {
  padding: 10px 20px 10px 50px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.submenu-item:hover {
  background-color: #dee2e6;
}

.submenu-item.active {
  background-color: #ced4da;
  font-weight: bold;
}
</style>
