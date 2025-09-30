<template>
  <div class="page-header">
    <h1>插件支持</h1>
    <p class="page-description">
      脚本内置多个插件，您可以根据不同场景选择使用，以下是所有可用的插件列表：
    </p>
  </div>
  <div class="page-container">
    <div class="table-container">
      <div class="table-wrapper">
        <table class="plugin-table">
          <thead>
            <tr>
              <th class="col-name">插件名称</th>
              <th class="col-description">使用方法</th>
              <th class="col-screenshot">页面截图</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="plugin in plugins" :key="plugin.id">
              <td class="col-name">
                <div class="plugin-name">
                  <!-- <img src="../assets/plugings.svg" alt="" /> -->
                  {{ plugin.name }}
                </div>
              </td>
              <td class="col-description">
                <div class="plugin-description">{{ plugin.usage }}</div>
              </td>
              <td class="col-screenshot">
                <div class="screenshot-wrapper">
                  <div
                    class="screenshot-grid"
                    v-if="
                      Array.isArray(plugin.screenshots) &&
                      plugin.screenshots.length > 0
                    "
                  >
                    <div
                      v-for="(screenshot, index) in plugin.screenshots"
                      :key="index"
                      class="screenshot-item"
                    >
                      <img
                        :src="screenshot"
                        class="plugin-screenshot"
                        @click="toggleImageEnlarge(screenshot)"
                      />
                    </div>
                  </div>
                  <div v-else class="no-screenshots">暂无截图</div>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <!-- 图片放大遮罩层 -->
    <div
      v-if="isImageEnlarged"
      class="image-overlay"
      @click="
        () => {
          isImageEnlarged = false
          enlargedImage = null
        }
      "
    >
      <img :src="enlargedImage" class="enlarged-image" @click.stop />
    </div>
  </div>
</template>

<script>
export default {
  name: 'PluginTable',
  data() {
    return {
      plugins: [
        {
          id: 1,
          name: '✨ 截图工具',
          usage:
            ' 点击截图，选择区域坐标定点截图，同时还可将截图复制到剪贴板、保存到自定义的位置，选择区域坐标定点截图，同时还可将截图复',
          screenshots: [
            require('@/assets/capture1.png'),
            require('@/assets/capture1.png'),
            require('@/assets/capture1.png')
          ] // 多个本地图片地址
        },
        {
          id: 2,
          name: '✨ 键盘输入',
          usage: ' 增加文本输入的步骤，支持输入文本、选择文本、复制文本等操作',
          screenshots: [
            require('@/assets/capture4.png'),
            require('@/assets/capture4.png')
          ]
        },
        {
          id: 3,
          name: '✨ 鼠标点击',
          usage: ' 插入鼠标点击的操作，支持通过图像、坐标点击',
          screenshots: [require('@/assets/capture1.png')]
        },
        {
          id: 4,
          name: '✨ 启动应用程序',
          usage: ' 可以选择指定的应用程序或快捷方式，由脚本自动启动',
          screenshots: [
            require('@/assets/capture2.png'),
            require('@/assets/capture3.png')
          ]
        },
        {
          id: 5,
          name: '✨ 桌面显示/隐藏',
          usage: ' 选择隐藏后，不管桌面打开多少个页面，都会直接显示桌面',
          screenshots: [
            require('@/assets/capture2.png'),
            require('@/assets/capture4.png')
          ]
        },
        {
          id: 6,
          name: '✨ 窗口最大化/最小化',
          usage: ' 点击可选择最大化/最小化的应用',
          screenshots: [
            require('@/assets/capture4.png'),
            require('@/assets/capture3.png')
          ]
        },
        {
          id: 7,
          name: '✨ 获取窗口对象',
          usage:
            ' 可以通过窗口标题和类名获取窗口对象，以后在操作指定应用程序时用',
          screenshots: [
            require('@/assets/capture1.png'),
            require('@/assets/capture1.png'),
            require('@/assets/capture1.png')
          ]
        }
      ],
      enlargedImage: null, // 存储当前放大的图片URL
      isImageEnlarged: false // 控制图片是否放大的状态
    }
  },
  methods: {
    toggleImageEnlarge(screenshot) {
      if (this.enlargedImage === screenshot && this.isImageEnlarged) {
        // 如果点击的是已放大的图片，则关闭放大视图
        this.isImageEnlarged = false
        this.enlargedImage = null
      } else {
        // 否则放大新点击的图片
        this.enlargedImage = screenshot
        this.isImageEnlarged = true
      }
    }
  }
}
</script>

<style scoped>
/* 标题样式 */
.page-header {
  margin-bottom: 32px;
}

.page-header h1 {
  font-size: 28px;
  margin-bottom: 8px;
  color: #1f2937;
}

/* 表格样式 */
.page-description {
  color: #6b7280;
  font-size: 18px;
  line-height: 1.6;
}

.table-container {
  width: 100%;
  overflow-x: auto;
  max-height: 90vh;
  display: flex;
  flex-direction: column;
}

.table-wrapper {
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  overflow: hidden;
}

.plugin-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 16px;
  table-layout: fixed;
}

.plugin-table thead {
  background: linear-gradient(135deg, #f5f7fa 0%, #e4e8f0 100%);
  border-bottom: 2px solid #d1d9e6;
  position: sticky;
  top: 0;
  z-index: 10;
  display: table;
  width: 100%;
  table-layout: fixed;
}

.plugin-table th {
  padding: 20px 24px;
  text-align: left;
  font-weight: 700;
  color: #374151;
  font-size: 16px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  position: relative;
}

.plugin-table td {
  padding: 16px 32px;
  border-bottom: 1px solid #f3f4f6;
  vertical-align: middle;
}

.plugin-table tbody {
  display: block;
  max-height: calc(80vh - 60px); /* 减去表头高度 */
  overflow-y: auto;
  width: 100%;
  background-color: #ffffff;
}

.plugin-table tbody tr:hover {
  background-color: #fafbfe;
  transition: background-color 0.2s ease;
}

.plugin-table tbody tr {
  display: table;
  width: 100%;
  table-layout: fixed;
}

.plugin-table th,
.plugin-table td {
  display: table-cell;
}

.plugin-table tbody tr:last-child td {
  border-bottom: none;
}

.col-name {
  width: 15%;
  max-width: 160px;
}

.col-description {
  width: 60%;
  min-width: 400px;
  padding-right: 24px;
}

.col-screenshot {
  width: 30%;
  min-width: 300px;
}

.plugin-name {
  font-weight: 600;
  color: #1f2937;
  font-size: 16px;
  /* padding-left: 24px; */
}

.plugin-description {
  line-height: 1.6;
  color: #4b5563;
}

.screenshot-wrapper {
  display: flex;
  justify-content: left;
  align-items: center;
  padding: 10px;
  border-radius: 8px;
  /* border: 1px solid #e5e7eb; */
}

.plugin-screenshot {
  max-width: 100%;
  height: auto;
  max-height: 100px; /* 限制最大高度 */
  border-radius: 2px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease;
  object-fit: contain; /* 确保图片保持比例 */
  cursor: pointer;
}

.plugin-screenshot:hover {
  transform: scale(1.03);
}

.screenshot-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  width: 100%;
}

.no-screenshots {
  padding: 20px;
  color: #9ca3af;
  text-align: center;
  font-style: italic;
}

/* 图片放大样式 */
.image-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
  cursor: pointer;
}

.enlarged-image {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain;
  cursor: default;
  border-radius: 4px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
}

/* 响应式调整 */
@media (max-width: 1200px) {
  .page-container {
    padding: 24px;
  }

  .plugin-table th,
  .plugin-table td {
    padding: 16px 20px;
  }

  .col-name {
    min-width: 180px;
  }

  .col-description {
    min-width: 300px;
  }

  .col-screenshot {
    min-width: 250px;
  }
}

@media (max-width: 768px) {
  .page-container {
    padding: 16px;
  }

  .page-header h1 {
    font-size: 24px;
  }

  .plugin-table th,
  .plugin-table td {
    padding: 12px 16px;
  }

  .plugin-name {
    font-size: 16px;
  }

  .plugin-description {
    font-size: 14px;
  }

  .col-name {
    min-width: 140px;
  }

  .col-description {
    min-width: 200px;
  }

  .col-screenshot {
    min-width: 150px;
  }
}
</style>
