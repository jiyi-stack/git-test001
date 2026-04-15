<template>
  <section class="updatesSection">
    <div class="sectionHeader">
      <h3>最近更新功能</h3>
      <button
        class="checkUpdateBtn"
        @click="checkForUpdates"
        :class="{ loading: isLoading }"
      >
        <i class="fas fa-sync-alt"></i>
        检查版本
      </button>
    </div>

    <div class="updatesCard">
      <div class="updateList">
        <div v-for="update in updates" :key="update.id" class="updateItem">
          <div class="updateBullet" :id="update.id"></div>
          <div class="updateContent">
            <h4 style="margin-bottom: 8px">{{ update.title }}</h4>
            <p style="font-size: 16px">{{ update.description }}</p>
            <p class="updateDate">{{ update.date }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'UpdatesSection',
  data() {
    return {
      isLoading: false,
      currentVersion: 'v1.1.9',
      latestVersion: 'v2.1.0',
      updates: [
        {
          id: 'item-1',
          title: '外包考勤系统新增考勤信息下载表格功能',
          description:
            '下载考勤信息，包含每日打卡数据，每月工时汇总/加班/调休工时等信息',
          date: '2024-01-15'
        },
        {
          id: 'item-2',
          title: '脚本录制功能升级',
          description: '新增智能操作识别，提高识别速度，减少在录制卡顿的现象',
          date: '2024-01-10'
        },
        {
          id: 'item-3',
          title: '新增脚本插件',
          description: '新增脚本插件Pdf处理工具插件，支持合并，压缩pdf文件',
          date: '2024-01-05'
        },
        {
          id: 'item-4',
          title: '脚本录制跳转交互优化',
          description: '跳转逻辑发生变化，点击录制后直接开启全屏记录',
          date: '2024-01-02'
        },
        {
          id: 'item-5',
          title: '脚本录制功能升级',
          description: '新增智能变量识别，提高识别速度，减少在录制卡顿的现象',
          date: '2024-01-01'
        },
        {
          id: 'item-6',
          title: '脚本编辑',
          description: '新增脚本编辑功能，用户可以直接在脚本中编辑和调试代码',
          date: '2024-01-08'
        }
      ]
    }
  },
  computed: {
    isLatestVersion() {
      return this.currentVersion === this.latestVersion
    }
  },
  methods: {
    getVersionText() {
      return this.isLatestVersion
        ? '当前已是最新版本'
        : `您当前的版本是${this.currentVersion}，请更新`
    },
    checkForUpdates() {
      this.isLoading = true
      setTimeout(() => {
        this.isLoading = false
        const modal = document.createElement('div')
        modal.className = 'update-modal'

        const iconClass = this.isLatestVersion
          ? 'fas fa-check-circle'
          : 'fas fa-exclamation-triangle'
        const iconColor = this.isLatestVersion ? '#10b981' : '#f59e0b'
        const statusText = this.getVersionText()

        modal.innerHTML = `
          <div class="modal-content">
            <div class="modal-header">
              <h3>检查更新</h3>
              <span class="close-btn">&times;</span>
            </div>
            <div class="modal-body">
              <div class="update-status">
                <i class="${iconClass}" style="color: ${iconColor};"></i>
                <p>${statusText}</p>
              </div>
              <div class="download-options">
                <h4>下载最新版本</h4>
                <div class="download-links">
                  <a href="/downloads/app-latest.exe" class="download-link">
                    <i class="fas fa-download"></i>
                    晓阳AI助手 (${this.latestVersion})
                  </a>
                </div>
              </div>
            </div>
          </div>
        `

        const style = document.createElement('style')
        style.textContent = `
          .update-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            animation: fadeIn 0.3s ease-out;
          }

          @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
          }

          .modal-content {
            background: white;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            animation: slideUp 0.1s ease-out;
          }

          @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
          }

          .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 16px 20px;
            border-bottom: 1px solid #f3f4f6;
          }

          .modal-header h3 {
            margin: 0;
            font-size: 16px;
            font-weight: 600;
            color: #1f2937;
          }

          .close-btn {
            font-size: 22px;
            color: #9ca3af;
            cursor: pointer;
          }

          .close-btn:hover {
            color: #4b5563;
          }

          .modal-body {
            padding: 20px;
          }

          .update-status {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 20px;
          }

          .update-status i {
            font-size: 22px;
          }

          .update-status p {
            margin: 0;
            color: #1f2937;
            font-size: 14px;
          }

          .download-options h4 {
            margin: 0 0 12px 0;
            font-size: 14px;
            font-weight: 600;
            color: #1f2937;
          }

          .download-links {
            display: flex;
            flex-direction: column;
            gap: 10px;
          }

          .download-link {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px 16px;
            background: #f9fafb;
            border-radius: 6px;
            text-decoration: none;
            color: #1f2937;
          }

          .download-link:hover {
            background: #f3f4f6;
          }

          .download-link i {
            color: #2563eb;
          }
        `
        document.head.appendChild(style)
        document.body.appendChild(modal)

        const closeBtn = modal.querySelector('.close-btn')
        closeBtn.addEventListener('click', function () {
          modal.style.animation = 'fadeOut 0.3s ease-out'
          setTimeout(() => {
            document.body.removeChild(modal)
          }, 300)
        })

        modal.addEventListener('click', function (e) {
          if (e.target === modal) {
            closeBtn.click()
          }
        })
      }, 1500)
    }
  }
}
</script>

<style scoped>
/* 更新列表 */
.updatesSection {
  display: flex;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
  margin-top: 16px;
}

/* 章节头部样式 */
.sectionHeader {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 16px;
}

.sectionHeader h2 {
  margin: 0;
}

.checkUpdateBtn {
  background: white;
  color: #4b5563;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  padding: 8px 16px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 6px;
  transition: all 0.2s;
}

.checkUpdateBtn:hover {
  background: #2563eb;
  color: white;
  border-color: #2563eb;
  transform: translateY(-1px);
}

.checkUpdateBtn.loading i {
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/* 卡片样式 */
.updatesCard {
  background: white;
  border-radius: 8px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  flex: 1;
  height: 200px;
  position: relative;
}

.updateList {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.updateItem {
  display: flex;
  position: relative;
}

.updateBullet {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #9ca3af;
  margin-top: 8px;
  flex-shrink: 0;
}

.updateItem:first-child .updateBullet {
  width: 10px;
  height: 10px;
  background: #2563eb;
  outline: 5px solid #b7ceff;
  animation: bulletPulse 2s infinite ease-in-out;
  z-index: 10;
}

@keyframes bulletPulse {
  0% {
    outline-width: 0px;
    box-shadow: 0 0 0 rgba(37, 99, 235, 0.4);
  }
  50% {
    outline-width: 3px;
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
  }
  100% {
    outline-width: 0px;
    box-shadow: 0 0 0 0 rgba(37, 99, 235, 0);
  }
}

/* 时间轴连接线 */
.updateItem:not(:last-child)::after {
  content: '';
  position: absolute;
  left: 3px;
  top: 16px;
  bottom: -30px;
  width: 2px;
  background: #e5e7eb;
}

.updateContent {
  margin-left: 12px;
}

.updateContent h3 {
  font-weight: 600;
  margin-bottom: 8px;
  color: #1f2937;
}

.updateContent p {
  color: #4b5563;
  margin-bottom: 2px;
}

.updateDate {
  color: #9ca3af;
  font-size: 14px;
}
</style>
