<template>
  <section class="updates-section">
    <div class="section-header">
      <h2 class="page-title">最近更新功能</h2>
      <button
        class="check-update-btn"
        @click="checkForUpdates"
        :class="{ loading: isLoading }"
      >
        <i class="fas fa-sync-alt"></i>
        检查版本
      </button>
    </div>
    <div class="updates-card">
      <div class="update-list">
        <div class="update-item">
          <div class="update-bullet" id="item-1"></div>
          <div class="update-content">
            <h3 class="update-title">外包考勤系统新增考勤信息下载表格功能</h3>
            <p class="update-description">
              下载考勤信息，包含每日打卡数据，每月工时汇总/加班/调休工时等信息
            </p>
            <p class="update-date">2024-01-15</p>
          </div>
        </div>

        <div class="update-item">
          <div class="update-bullet" id="item-2"></div>
          <div class="update-content">
            <h3 class="update-title">脚本录制功能升级</h3>
            <p class="update-description">
              新增智能操作识别，提高识别速度，减少在录制卡顿的现象
            </p>
            <p class="update-date">2024-01-10</p>
          </div>
        </div>

        <div class="update-item">
          <div class="update-bullet" id="item-3"></div>
          <div class="update-content">
            <h3 class="update-title">新增脚本插件</h3>
            <p class="update-description">
              新增脚本插件Pdf处理工具插件，支持合并，压缩pdf文件
            </p>
            <p class="update-date">2024-01-05</p>
          </div>
        </div>

        <div class="update-item">
          <div class="update-bullet" id="item-4"></div>
          <div class="update-content">
            <h3 class="update-title">脚本录制跳转交互优化</h3>
            <p class="update-description">
              跳转逻辑发生变化，点击录制后直接开启全屏记录
            </p>
            <p class="update-date">2024-01-02</p>
          </div>
        </div>

        <div class="update-item">
          <div class="update-bullet" id="item-5"></div>
          <div class="update-content">
            <h3 class="update-title">脚本录制功能升级</h3>
            <p class="update-description">
              新增智能变量识别，提高时别速度，减少在录制卡顿的现象
            </p>
            <p class="update-date">2024-01-01</p>
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
      currentVersion: 'v1.1.9', // 当前版本
      latestVersion: 'v2.1.0' // 最新版本
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
      // 添加加载状态
      this.isLoading = true

      // 模拟检查更新过程
      setTimeout(() => {
        // 移除加载状态
        this.isLoading = false

        // 创建更新提示模态框
        const updateModal = document.createElement('div')
        updateModal.className = 'update-modal'

        // 根据版本状态确定图标和文本
        const iconClass = this.isLatestVersion
          ? 'fas fa-check-circle'
          : 'fas fa-exclamation-triangle'
        const iconColor = this.isLatestVersion ? '#10b981' : '#f59e0b'
        const statusText = this.getVersionText()

        // 使用字符串模板直接插入值，而不是Vue插值
        updateModal.innerHTML = `
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

        // 添加模态框样式
        const style = document.createElement('style')
        style.textContent = `
          .update-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
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
            background-color: white;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            animation: slideUp 0.1s ease-out;
          }

          @keyframes slideUp {
            from {
              transform: translateY(50px);
              opacity: 0;
            }
            to {
              transform: translateY(0);
              opacity: 1;
            }
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
            font-size: 18px;
            font-weight: 600;
            color: #1f2937;
          }

          .close-btn {
            font-size: 24px;
            color: #9ca3af;
            cursor: pointer;
            transition: color 0.2s;
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
            color: #10b981;
            font-size: 24px;
          }

          .update-status p {
            margin: 0;
            color: #1f2937;
            font-size: 16px;
          }

          .download-options h4 {
            margin: 0 0 12px 0;
            font-size: 16px;
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
            background-color: #f9fafb;
            border-radius: 6px;
            text-decoration: none;
            color: #1f2937;
            transition: background-color 0.2s;
          }

          .download-link:hover {
            background-color: #f3f4f6;
          }

          .download-link i {
            color: #2563eb;
          }
        `
        document.head.appendChild(style)

        document.body.appendChild(updateModal)

        // 添加关闭按钮功能
        const closeBtn = updateModal.querySelector('.close-btn')
        closeBtn.addEventListener('click', function () {
          updateModal.style.animation = 'fadeOut 0.3s ease-out'
          setTimeout(() => {
            document.body.removeChild(updateModal)
          }, 300)
        })

        // 点击模态框外部关闭
        updateModal.addEventListener('click', function (e) {
          if (e.target === updateModal) {
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
.updates-section {
  display: flex;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
  margin-top: 32px;
  margin-bottom: 8px;
}

.updates-card {
  background-color: #fff;
  border-radius: 8px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  flex: 1;
  /* overflow-y: auto; */
  position: relative;
  /* 自定义滚动条样式 */
  scrollbar-width: thin;
  scrollbar-color: #cbd5e1 #f1f5f9;
  height: 200px;
}

.update-list {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.update-item {
  display: flex;
  position: relative;
}

.update-bullet {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background-color: #9ca3af;
  margin-top: 8px;
  flex-shrink: 0;
}

.update-item:first-child .update-bullet {
  width: 10px;
  height: 10px;
  background-color: #2563eb;
  outline: 5px solid #b7ceff;
  animation: bulletPulse 2s infinite ease-in-out;
  z-index: 10;
}

@keyframes bulletPulse {
  0% {
    outline-width: 0px;
    box-shadow: 0 0 0 0 rgba(37, 99, 235, 0.4);
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
.update-item:not(:last-child)::after {
  content: '';
  position: absolute;
  left: 3px;
  top: 16px;
  bottom: -30px;
  width: 2px;
  background-color: #e5e7eb;
}

.update-content {
  margin-left: 12px;
}

.update-title {
  font-weight: 600;
  margin-bottom: 8px;
  color: #1f2937;
}

.update-description {
  color: #4b5563;
  margin-bottom: 8px;
}

.update-date {
  color: #9ca3af;
  font-size: 14px;
}

/* 章节头部样式 */
.section-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 16px;
}

.page-title {
  margin-bottom: 0;
}

.check-update-btn {
  background-color: white;
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
  overflow: hidden;
  position: relative;
  transition: color 0.3s;
}

.check-update-btn:hover {
  background-color: #2563eb;
  color: white;
  border-color: #2563eb;
  transform: translateY(-1px);
}

.check-update-btn:active {
  background-color: #1d4ed8;
  transform: translateY(0);
}

.check-update-btn i {
  transition: transform 0.3s;
}

.check-update-btn.loading i {
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
</style>
