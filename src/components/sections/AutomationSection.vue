<template>
  <section class="automation-section">
    <div class="page-header">
      <h1 class="page-title">脚本自动化</h1>
      <p class="page-description">通过录制和执行脚本，实现重复性工作的自动化，提高工作效率</p>
    </div>

    <div class="automation-content">
      <div class="automation-sidebar">
        <div class="sidebar-menu">
          <h3>功能导航</h3>
          <ul>
            <li class="sidebar-item active" data-tab="recording">脚本录制</li>
            <li class="sidebar-item" data-tab="execution">脚本执行</li>
            <li class="sidebar-item" data-tab="management">脚本管理</li>
            <li class="sidebar-item" data-tab="variables">变量管理</li>
            <li class="sidebar-item" data-tab="plugins">插件管理</li>
          </ul>
        </div>

        <div class="quick-actions">
          <h3>快速操作</h3>
          <button class="action-btn new-script-btn"><i class="fas fa-plus"></i> 新建脚本</button>
          <button class="action-btn record-btn"><i class="fas fa-record-vinyl"></i> 开始录制</button>
          <button class="action-btn import-btn"><i class="fas fa-file-import"></i> 导入脚本</button>
        </div>
      </div>

      <div class="main-content">
        <div class="tab-content active" id="recording">
          <div class="tab-header">
            <h2>脚本录制</h2>
            <div class="tab-actions">
              <button class="btn btn-primary"><i class="fas fa-play"></i> 开始录制</button>
              <button class="btn btn-secondary"><i class="fas fa-cog"></i> 设置</button>
            </div>
          </div>

          <div class="recording-area">
            <div class="recording-controls">
              <button class="control-btn record"><i class="fas fa-record-vinyl"></i></button>
              <button class="control-btn pause"><i class="fas fa-pause"></i></button>
              <button class="control-btn stop"><i class="fas fa-stop"></i></button>
            </div>

            <div class="recording-status">
              <div class="status-indicator idle">就绪</div>
              <div class="status-info">点击"开始录制"按钮开始录制脚本</div>
            </div>
          </div>

          <div class="recording-options">
            <h3>录制选项</h3>
            <div class="options-grid">
              <div class="option-item">
                <label class="checkbox-label">
                  <input type="checkbox" checked>
                  <span>记录鼠标操作</span>
                </label>
              </div>
              <div class="option-item">
                <label class="checkbox-label">
                  <input type="checkbox" checked>
                  <span>记录键盘输入</span>
                </label>
              </div>
              <div class="option-item">
                <label class="checkbox-label">
                  <input type="checkbox">
                  <span>智能识别变量</span>
                </label>
              </div>
              <div class="option-item">
                <label class="checkbox-label">
                  <input type="checkbox" checked>
                  <span>等待页面加载</span>
                </label>
              </div>
            </div>
          </div>
        </div>

        <div class="tab-content" id="execution">
          <div class="tab-header">
            <h2>脚本执行</h2>
            <div class="tab-actions">
              <button class="btn btn-primary"><i class="fas fa-play"></i> 执行脚本</button>
              <button class="btn btn-secondary"><i class="fas fa-cog"></i> 执行设置</button>
            </div>
          </div>

          <div class="execution-area">
            <div class="script-list">
              <h3>脚本列表</h3>
              <div class="script-items">
                <div class="script-item selected">
                  <div class="script-info">
                    <h4>登录流程自动化</h4>
                    <p>最后修改: 2024-01-15</p>
                  </div>
                  <div class="script-actions">
                    <button class="btn-icon"><i class="fas fa-play"></i></button>
                    <button class="btn-icon"><i class="fas fa-edit"></i></button>
                    <button class="btn-icon"><i class="fas fa-trash"></i></button>
                  </div>
                </div>
                <div class="script-item">
                  <div class="script-info">
                    <h4>数据报表生成</h4>
                    <p>最后修改: 2024-01-10</p>
                  </div>
                  <div class="script-actions">
                    <button class="btn-icon"><i class="fas fa-play"></i></button>
                    <button class="btn-icon"><i class="fas fa-edit"></i></button>
                    <button class="btn-icon"><i class="fas fa-trash"></i></button>
                  </div>
                </div>
              </div>
            </div>

            <div class="execution-details">
              <h3>执行详情</h3>
              <div class="execution-log">
                <div class="log-entry">
                  <span class="log-time">10:30:25</span>
                  <span class="log-message">脚本开始执行</span>
                </div>
                <div class="log-entry">
                  <span class="log-time">10:30:26</span>
                  <span class="log-message">打开网页: https://example.com/login</span>
                </div>
                <div class="log-entry">
                  <span class="log-time">10:30:28</span>
                  <span class="log-message">输入用户名: admin</span>
                </div>
                <div class="log-entry">
                  <span class="log-time">10:30:29</span>
                  <span class="log-message">输入密码: ********</span>
                </div>
                <div class="log-entry">
                  <span class="log-time">10:30:30</span>
                  <span class="log-message">点击登录按钮</span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="tab-content" id="management">
          <div class="tab-header">
            <h2>脚本管理</h2>
            <div class="tab-actions">
              <button class="btn btn-primary"><i class="fas fa-plus"></i> 新建脚本</button>
              <button class="btn btn-secondary"><i class="fas fa-folder"></i> 新建文件夹</button>
            </div>
          </div>

          <div class="script-management">
            <div class="file-tree">
              <h3>脚本库</h3>
              <div class="tree-container">
                <div class="tree-folder">
                  <div class="folder-header">
                    <i class="fas fa-chevron-down"></i>
                    <i class="fas fa-folder"></i>
                    <span>工作流脚本</span>
                  </div>
                  <div class="folder-contents">
                    <div class="tree-file">
                      <i class="fas fa-file-code"></i>
                      <span>登录流程自动化.js</span>
                    </div>
                    <div class="tree-file">
                      <i class="fas fa-file-code"></i>
                      <span>数据报表生成.js</span>
                    </div>
                    <div class="tree-folder">
                      <div class="folder-header">
                        <i class="fas fa-chevron-right"></i>
                        <i class="fas fa-folder"></i>
                        <span>数据处理</span>
                      </div>
                      <div class="folder-contents">
                        <div class="tree-file">
                          <i class="fas fa-file-code"></i>
                          <span>Excel数据导入.js</span>
                        </div>
                        <div class="tree-file">
                          <i class="fas fa-file-code"></i>
                          <span>CSV文件处理.js</span>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="tree-folder">
                  <div class="folder-header">
                    <i class="fas fa-chevron-down"></i>
                    <i class="fas fa-folder"></i>
                    <span>自动化测试</span>
                  </div>
                  <div class="folder-contents">
                    <div class="tree-file">
                      <i class="fas fa-file-code"></i>
                      <span>网页自动化测试.js</span>
                    </div>
                    <div class="tree-file">
                      <i class="fas fa-file-code"></i>
                      <span>API接口测试.js</span>
                    </div>
                  </div>
                </div>
                <div class="tree-file">
                  <i class="fas fa-file-code"></i>
                  <span>定时任务.js</span>
                </div>
              </div>
            </div>

            <div class="script-editor">
              <div class="editor-header">
                <div class="editor-tabs">
                  <div class="editor-tab active">登录流程自动化.js</div>
                  <div class="editor-tab">变量</div>
                  <div class="editor-tab">日志</div>
                </div>
                <div class="editor-actions">
                  <button class="btn btn-secondary"><i class="fas fa-save"></i> 保存</button>
                  <button class="btn btn-secondary"><i class="fas fa-play"></i> 运行</button>
                  <button class="btn btn-secondary"><i class="fas fa-cog"></i> 设置</button>
                </div>
              </div>
              <div class="editor-content">
                <div class="editor-code active">
                  <pre><code>// 登录流程自动化脚本

// 定义变量
const username = 'admin';
const password = 'password123';
const loginUrl = 'https://example.com/login';

// 打开登录页面
openPage(loginUrl);

// 等待页面加载
waitForPageLoad();

// 输入用户名
inputText('#username', username);

// 输入密码
inputText('#password', password);

// 点击登录按钮
clickElement('#login-button');

// 等待登录完成
waitForPageLoad();

// 验证登录是否成功
if (getCurrentUrl().includes('dashboard')) {
    log('登录成功');
} else {
    log('登录失败', 'error');
}</code></pre>
                </div>
                <div class="editor-variables">
                  <h3>脚本变量</h3>
                  <div class="variables-list">
                    <div class="variable-item">
                      <div class="variable-name">username</div>
                      <div class="variable-value">'admin'</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                      </div>
                    </div>
                    <div class="variable-item">
                      <div class="variable-name">password</div>
                      <div class="variable-value">'password123'</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                      </div>
                    </div>
                    <div class="variable-item">
                      <div class="variable-name">loginUrl</div>
                      <div class="variable-value">'https://example.com/login'</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                      </div>
                    </div>
                  </div>
                  <button class="btn btn-primary"><i class="fas fa-plus"></i> 添加变量</button>
                </div>
                <div class="editor-log">
                  <h3>执行日志</h3>
                  <div class="log-container">
                    <div class="log-entry info">
                      <span class="log-time">10:30:25</span>
                      <span class="log-message">脚本开始执行</span>
                    </div>
                    <div class="log-entry success">
                      <span class="log-time">10:30:26</span>
                      <span class="log-message">打开页面: https://example.com/login</span>
                    </div>
                    <div class="log-entry info">
                      <span class="log-time">10:30:28</span>
                      <span class="log-message">输入用户名: admin</span>
                    </div>
                    <div class="log-entry info">
                      <span class="log-time">10:30:29</span>
                      <span class="log-message">输入密码: ********</span>
                    </div>
                    <div class="log-entry info">
                      <span class="log-time">10:30:30</span>
                      <span class="log-message">点击登录按钮</span>
                    </div>
                    <div class="log-entry success">
                      <span class="log-time">10:30:31</span>
                      <span class="log-message">登录成功，跳转到仪表板</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="tab-content" id="variables">
          <div class="tab-header">
            <h2>变量管理</h2>
            <div class="tab-actions">
              <button class="btn btn-primary"><i class="fas fa-plus"></i> 新建变量</button>
              <button class="btn btn-secondary"><i class="fas fa-upload"></i> 导入变量</button>
              <button class="btn btn-secondary"><i class="fas fa-download"></i> 导出变量</button>
            </div>
          </div>

          <div class="variables-management">
            <div class="variables-overview">
              <div class="stats-cards">
                <div class="stat-card">
                  <div class="stat-icon">
                    <i class="fas fa-database"></i>
                  </div>
                  <div class="stat-info">
                    <div class="stat-value">24</div>
                    <div class="stat-label">变量总数</div>
                  </div>
                </div>
                <div class="stat-card">
                  <div class="stat-icon">
                    <i class="fas fa-folder"></i>
                  </div>
                  <div class="stat-info">
                    <div class="stat-value">5</div>
                    <div class="stat-label">变量组数</div>
                  </div>
                </div>
                <div class="stat-card">
                  <div class="stat-icon">
                    <i class="fas fa-clock"></i>
                  </div>
                  <div class="stat-info">
                    <div class="stat-value">2</div>
                    <div class="stat-label">最近更新</div>
                  </div>
                </div>
              </div>
            </div>

            <div class="variables-list-container">
              <div class="variables-filters">
                <div class="search-box">
                  <i class="fas fa-search"></i>
                  <input type="text" placeholder="搜索变量名称或值">
                </div>
                <div class="filter-options">
                  <select class="filter-select">
                    <option>所有类型</option>
                    <option>字符串</option>
                    <option>数字</option>
                    <option>布尔值</option>
                    <option>数组</option>
                    <option>对象</option>
                  </select>
                  <select class="filter-select">
                    <option>所有组</option>
                    <option>登录信息</option>
                    <option>API配置</option>
                    <option>测试数据</option>
                  </select>
                </div>
              </div>

              <div class="variables-list">
                <div class="variable-group">
                  <div class="group-header">
                    <i class="fas fa-chevron-down"></i>
                    <i class="fas fa-folder"></i>
                    <span>登录信息</span>
                    <span class="group-count">(3)</span>
                  </div>
                  <div class="group-variables">
                    <div class="variable-row">
                      <div class="variable-name">username</div>
                      <div class="variable-value">"admin"</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-usage">5个脚本</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                        <button class="btn-icon"><i class="fas fa-copy"></i></button>
                      </div>
                    </div>
                    <div class="variable-row">
                      <div class="variable-name">password</div>
                      <div class="variable-value">"********"</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-usage">3个脚本</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                        <button class="btn-icon"><i class="fas fa-copy"></i></button>
                      </div>
                    </div>
                    <div class="variable-row">
                      <div class="variable-name">loginUrl</div>
                      <div class="variable-value">"https://example.com/login"</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-usage">2个脚本</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                        <button class="btn-icon"><i class="fas fa-copy"></i></button>
                      </div>
                    </div>
                  </div>
                </div>

                <div class="variable-group">
                  <div class="group-header">
                    <i class="fas fa-chevron-right"></i>
                    <i class="fas fa-folder"></i>
                    <span>API配置</span>
                    <span class="group-count">(2)</span>
                  </div>
                  <div class="group-variables">
                    <div class="variable-row">
                      <div class="variable-name">apiEndpoint</div>
                      <div class="variable-value">"https://api.example.com"</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-usage">4个脚本</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                        <button class="btn-icon"><i class="fas fa-copy"></i></button>
                      </div>
                    </div>
                    <div class="variable-row">
                      <div class="variable-name">apiKey</div>
                      <div class="variable-value">"sk-1234567890"</div>
                      <div class="variable-type">字符串</div>
                      <div class="variable-usage">4个脚本</div>
                      <div class="variable-actions">
                        <button class="btn-icon"><i class="fas fa-edit"></i></button>
                        <button class="btn-icon"><i class="fas fa-trash"></i></button>
                        <button class="btn-icon"><i class="fas fa-copy"></i></button>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="tab-content" id="plugins">
          <div class="tab-header">
            <h2>插件管理</h2>
            <div class="tab-actions">
              <button class="btn btn-primary"><i class="fas fa-plus"></i> 安装插件</button>
              <button class="btn btn-secondary"><i class="fas fa-upload"></i> 上传插件</button>
            </div>
          </div>

          <div class="plugins-management">
            <div class="plugins-categories">
              <div class="category-tab active" data-category="all">全部</div>
              <div class="category-tab" data-category="installed">已安装</div>
              <div class="category-tab" data-category="recommended">推荐</div>
              <div class="category-tab" data-category="development">开发中</div>
            </div>

            <div class="plugins-list">
              <div class="plugin-card">
                <div class="plugin-header">
                  <div class="plugin-icon">
                    <i class="fas fa-file-pdf"></i>
                  </div>
                  <div class="plugin-info">
                    <h3 class="plugin-name">PDF处理工具</h3>
                    <div class="plugin-meta">
                      <span class="plugin-version">v1.2.0</span>
                      <span class="plugin-category">文档处理</span>
                    </div>
                  </div>
                  <div class="plugin-status">
                    <span class="status-badge installed">已安装</span>
                  </div>
                </div>
                <div class="plugin-description">
                  支持PDF文件的合并、拆分、压缩、加密等功能，提供批量处理能力，提升办公效率。
                </div>
                <div class="plugin-actions">
                  <button class="btn btn-secondary"><i class="fas fa-cog"></i> 配置</button>
                  <button class="btn btn-secondary"><i class="fas fa-info-circle"></i> 详情</button>
                </div>
              </div>

              <div class="plugin-card">
                <div class="plugin-header">
                  <div class="plugin-icon">
                    <i class="fas fa-file-excel"></i>
                  </div>
                  <div class="plugin-info">
                    <h3 class="plugin-name">Excel数据处理</h3>
                    <div class="plugin-meta">
                      <span class="plugin-version">v2.0.1</span>
                      <span class="plugin-category">数据处理</span>
                    </div>
                  </div>
                  <div class="plugin-status">
                    <span class="status-badge installed">已安装</span>
                  </div>
                </div>
                <div class="plugin-description">
                  支持Excel文件的读取、编辑、导出，提供数据透视表、图表生成等高级功能。
                </div>
                <div class="plugin-actions">
                  <button class="btn btn-secondary"><i class="fas fa-cog"></i> 配置</button>
                  <button class="btn btn-secondary"><i class="fas fa-info-circle"></i> 详情</button>
                </div>
              </div>

              <div class="plugin-card">
                <div class="plugin-header">
                  <div class="plugin-icon">
                    <i class="fas fa-envelope"></i>
                  </div>
                  <div class="plugin-info">
                    <h3 class="plugin-name">邮件自动化</h3>
                    <div class="plugin-meta">
                      <span class="plugin-version">v1.5.3</span>
                      <span class="plugin-category">通讯工具</span>
                    </div>
                  </div>
                  <div class="plugin-status">
                    <span class="status-badge recommended">推荐</span>
                  </div>
                </div>
                <div class="plugin-description">
                  支持邮件的自动发送、接收、分类处理，可设置定时任务和规则引擎，实现邮件自动化管理。
                </div>
                <div class="plugin-actions">
                  <button class="btn btn-primary"><i class="fas fa-download"></i> 安装</button>
                  <button class="btn btn-secondary"><i class="fas fa-info-circle"></i> 详情</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AutomationSection'
}
</script>

<style scoped>
/* 页面标题 */
.page-header {
  margin-bottom: 32px;
}

.page-header h1 {
  font-size: 28px;
  margin-bottom: 8px;
  color: #1f2937;
}

.page-description {
  color: #6b7280;
  font-size: 16px;
}

/* 脚本自动化页面样式 */
.automation-section {
  display: flex;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
}

.automation-content {
  display: flex;
  flex: 1;
  gap: 24px;
  overflow: hidden;
}

.automation-sidebar {
  width: 240px;
  flex-shrink: 0;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.sidebar-menu h3,
.quick-actions h3 {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 12px;
  color: #374151;
}

.sidebar-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.sidebar-item {
  padding: 10px 16px;
  margin-bottom: 4px;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.sidebar-item:hover {
  background-color: #f3f4f6;
}

.sidebar-item.active {
  background-color: #eff6ff;
  color: #2563eb;
  font-weight: 500;
}

.action-btn {
  width: 100%;
  padding: 10px 16px;
  margin-bottom: 8px;
  border: none;
  border-radius: 6px;
  background-color: #f9fafb;
  color: #374151;
  font-size: 14px;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 8px;
  transition: background-color 0.2s;
}

.action-btn:hover {
  background-color: #f3f4f6;
}

.action-btn i {
  font-size: 16px;
}

.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.tab-content {
  display: none;
  flex-direction: column;
  flex: 1;
}

.tab-content.active {
  display: flex;
}

.tab-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
  padding-bottom: 16px;
  border-bottom: 1px solid #e5e7eb;
}

.tab-header h2 {
  font-size: 22px;
  font-weight: 600;
  color: #1f2937;
}

.tab-actions {
  display: flex;
  gap: 12px;
}

.btn {
  padding: 8px 16px;
  border: none;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 6px;
  transition: background-color 0.2s;
}

.btn-primary {
  background-color: #2563eb;
  color: white;
}

.btn-primary:hover {
  background-color: #1d4ed8;
}

.btn-secondary {
  background-color: #f3f4f6;
  color: #374151;
}

.btn-secondary:hover {
  background-color: #e5e7eb;
}

.btn-icon {
  width: 32px;
  height: 32px;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
}

.btn-icon:hover {
  background-color: #f3f4f6;
}

/* 录制区域样式 */
.recording-area {
  background-color: #f9fafb;
  border-radius: 8px;
  padding: 24px;
  margin-bottom: 24px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.recording-controls {
  display: flex;
  gap: 16px;
  justify-content: center;
}

.control-btn {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: transform 0.1s;
}

.control-btn:hover {
  transform: scale(1.05);
}

.control-btn.record {
  background-color: #ef4444;
  color: white;
}

.control-btn.pause {
  background-color: #f59e0b;
  color: white;
}

.control-btn.stop {
  background-color: #6b7280;
  color: white;
}

.recording-status {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

.status-indicator {
  padding: 6px 12px;
  border-radius: 4px;
  font-weight: 500;
  font-size: 14px;
}

.status-indicator.idle {
  background-color: #e5e7eb;
  color: #6b7280;
}

.status-indicator.recording {
  background-color: #fee2e2;
  color: #dc2626;
}

.status-indicator.paused {
  background-color: #fef3c7;
  color: #d97706;
}

.status-info {
  color: #6b7280;
  font-size: 14px;
}

.recording-options {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.recording-options h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.options-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.option-item {
  display: flex;
  align-items: center;
}

.checkbox-label {
  display: flex;
  align-items: center;
  cursor: pointer;
  font-size: 14px;
  color: #374151;
}

.checkbox-label input[type="checkbox"] {
  margin-right: 8px;
}

/* 执行区域样式 */
.execution-area {
  display: flex;
  flex: 1;
  gap: 24px;
}

.script-list,
.execution-details {
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.script-list {
  width: 300px;
  flex-shrink: 0;
}

.execution-details {
  flex: 1;
  display: flex;
  flex-direction: column;
}

.script-list h3,
.execution-details h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.script-items {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.script-item {
  padding: 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  transition: border-color 0.2s;
}

.script-item:hover {
  border-color: #d1d5db;
}

.script-item.selected {
  border-color: #2563eb;
  background-color: #eff6ff;
}

.script-info h4 {
  font-size: 16px;
  font-weight: 500;
  margin-bottom: 4px;
  color: #1f2937;
}

.script-info p {
  font-size: 14px;
  color: #6b7280;
}

.script-actions {
  display: flex;
  gap: 4px;
}

.execution-log {
  flex: 1;
  overflow-y: auto;
  background-color: #1f2937;
  color: #f9fafb;
  border-radius: 6px;
  padding: 16px;
  font-family: monospace;
  font-size: 14px;
}

.log-entry {
  margin-bottom: 4px;
  display: flex;
  gap: 8px;
}

.log-time {
  color: #9ca3af;
}

.log-message {
  color: #f9fafb;
}

/* 脚本管理样式 */
.script-management {
  display: flex;
  flex: 1;
  gap: 24px;
}

.file-tree {
  width: 300px;
  flex-shrink: 0;
  background-color: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.script-editor {
  flex: 1;
  display: flex;
  flex-direction: column;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.file-tree h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.tree-container {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.tree-folder {
  margin-bottom: 8px;
}

.folder-header {
  display: flex;
  align-items: center;
  padding: 6px 8px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.folder-header:hover {
  background-color: #f3f4f6;
}

.folder-header i {
  margin-right: 8px;
  color: #6b7280;
}

.folder-header i:first-child {
  font-size: 12px;
}

.folder-header i:nth-child(2) {
  margin-right: 8px;
}

.folder-header span {
  font-size: 14px;
  color: #374151;
}

.folder-contents {
  margin-left: 24px;
  display: none;
}

.folder-contents.show {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.tree-file {
  display: flex;
  align-items: center;
  padding: 6px 8px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.tree-file:hover {
  background-color: #f3f4f6;
}

.tree-file i {
  margin-right: 8px;
  color: #6b7280;
}

.tree-file span {
  font-size: 14px;
  color: #374151;
}

.editor-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #e5e7eb;
}

.editor-tabs {
  display: flex;
  gap: 16px;
}

.editor-tab {
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  color: #6b7280;
  cursor: pointer;
  transition: background-color 0.2s;
}

.editor-tab:hover {
  background-color: #f3f4f6;
}

.editor-tab.active {
  background-color: #eff6ff;
  color: #2563eb;
}

.editor-actions {
  display: flex;
  gap: 12px;
}

.editor-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.editor-code,
.editor-variables,
.editor-log {
  display: none;
  flex-direction: column;
  flex: 1;
  overflow: hidden;
}

.editor-code.active,
.editor-variables.active,
.editor-log.active {
  display: flex;
}

.editor-variables h3,
.editor-log h3 {
  font-size: 18px;
  margin-bottom: 16px;
  color: #1f2937;
}

.editor-code pre {
  flex: 1;
  overflow: auto;
  background-color: #1f2937;
  color: #f9fafb;
  border-radius: 6px;
  padding: 16px;
  font-family: monospace;
  font-size: 14px;
  margin: 0;
}

.editor-code code {
  font-family: monospace;
}

.variables-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
  overflow-y: auto;
  flex: 1;
  padding-right: 8px;
}

.variable-item {
  display: flex;
  align-items: center;
  padding: 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  background-color: #f9fafb;
}

.variable-name {
  width: 120px;
  font-weight: 500;
  color: #1f2937;
}

.variable-value {
  flex: 1;
  font-family: monospace;
  color: #4b5563;
}

.variable-type {
  width: 80px;
  color: #6b7280;
  font-size: 14px;
}

.variable-usage {
  width: 100px;
  color: #6b7280;
  font-size: 14px;
}

.variable-actions {
  display: flex;
  gap: 4px;
}

.log-container {
  flex: 1;
  overflow-y: auto;
  background-color: #1f2937;
  border-radius: 6px;
  padding: 16px;
  font-family: monospace;
  font-size: 14px;
}

.log-entry {
  margin-bottom: 4px;
  display: flex;
  gap: 8px;
}

.log-entry.info .log-time {
  color: #9ca3af;
}

.log-entry.info .log-message {
  color: #f9fafb;
}

.log-entry.success .log-time {
  color: #9ca3af;
}

.log-entry.success .log-message {
  color: #10b981;
}

/* 变量管理样式 */
.variables-management {
  display: flex;
  flex-direction: column;
  gap: 24px;
  flex: 1;
}

.variables-overview {
  display: flex;
  gap: 24px;
}

.stats-cards {
  display: flex;
  gap: 24px;
  width: 100%;
}

.stat-card {
  flex: 1;
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 16px;
  border-radius: 8px;
  background-color: #f9fafb;
  border: 1px solid #e5e7eb;
}

.stat-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  background-color: #eff6ff;
}

.stat-icon i {
  font-size: 24px;
  color: #2563eb;
}

.stat-info {
  display: flex;
  flex-direction: column;
}

.stat-value {
  font-size: 24px;
  font-weight: 600;
  color: #1f2937;
}

.stat-label {
  font-size: 14px;
  color: #6b7280;
}

.variables-list-container {
  display: flex;
  flex-direction: column;
  flex: 1;
  gap: 16px;
}

.variables-filters {
  display: flex;
  gap: 16px;
  align-items: center;
}

.search-box {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  background-color: #fff;
  flex: 1;
}

.search-box i {
  color: #9ca3af;
}

.search-box input {
  border: none;
  background: none;
  outline: none;
  width: 100%;
  font-size: 14px;
  color: #1f2937;
}

.filter-options {
  display: flex;
  gap: 12px;
}

.filter-select {
  padding: 8px 12px;
  border-radius: 6px;
  border: 1px solid #e5e7eb;
  background-color: #fff;
  font-size: 14px;
  color: #1f2937;
  cursor: pointer;
}

.variables-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  flex: 1;
  overflow-y: auto;
}

.variable-group {
  border-radius: 8px;
  border: 1px solid #e5e7eb;
  overflow: hidden;
}

.group-header {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  background-color: #f9fafb;
  cursor: pointer;
  transition: background-color 0.2s;
}

.group-header:hover {
  background-color: #f3f4f6;
}

.group-header i {
  margin-right: 8px;
  color: #6b7280;
}

.group-header i:first-child {
  font-size: 12px;
}

.group-header i:nth-child(2) {
  margin-right: 12px;
}

.group-header span {
  font-size: 16px;
  font-weight: 500;
  color: #1f2937;
}

.group-count {
  margin-left: auto;
  font-size: 14px;
  color: #6b7280;
}

.group-variables {
  display: flex;
  flex-direction: column;
}

.variable-row {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  border-top: 1px solid #e5e7eb;
}

.variable-name {
  width: 120px;
  font-weight: 500;
  color: #1f2937;
}

.variable-value {
  flex: 1;
  font-family: monospace;
  color: #4b5563;
}

.variable-type {
  width: 80px;
  color: #6b7280;
  font-size: 14px;
}

.variable-usage {
  width: 100px;
  color: #6b7280;
  font-size: 14px;
}

.variable-actions {
  display: flex;
  gap: 4px;
}

/* 插件管理样式 */
.plugins-management {
  display: flex;
  flex-direction: column;
  gap: 24px;
  flex: 1;
}

.plugins-categories {
  display: flex;
  gap: 12px;
  border-bottom: 1px solid #e5e7eb;
  padding-bottom: 12px;
}

.category-tab {
  padding: 8px 16px;
  border-radius: 6px 6px 0 0;
  font-size: 14px;
  font-weight: 500;
  color: #6b7280;
  cursor: pointer;
  transition: background-color 0.2s;
}

.category-tab:hover {
  color: #1f2937;
}

.category-tab.active {
  color: #2563eb;
  background-color: #eff6ff;
}

.plugins-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  flex: 1;
}

.plugin-card {
  background-color: #fff;
  border-radius: 8px;
  border: 1px solid #e5e7eb;
  padding: 20px;
  transition: box-shadow 0.2s;
}

.plugin-card:hover {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.plugin-header {
  display: flex;
  align-items: center;
  margin-bottom: 12px;
}

.plugin-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  margin-right: 16px;
  background-color: #f3f4f6;
}

.plugin-icon i {
  font-size: 24px;
  color: #6b7280;
}

.plugin-info {
  flex: 1;
}

.plugin-name {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 4px;
  color: #1f2937;
}

.plugin-meta {
  display: flex;
  gap: 12px;
}

.plugin-version {
  font-size: 14px;
  color: #6b7280;
}

.plugin-category {
  font-size: 14px;
  color: #6b7280;
}

.plugin-status {
  margin-left: 16px;
}

.status-badge {
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 12px;
  font-weight: 500;
}

.status-badge.installed {
  background-color: #d1fae5;
  color: #065f46;
}

.status-badge.recommended {
  background-color: #dbeafe;
  color: #1e40af;
}

.plugin-description {
  color: #4b5563;
  line-height: 1.5;
  margin-bottom: 16px;
}

.plugin-actions {
  display: flex;
  gap: 12px;
}

/* 自定义滚动条 */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f5f9;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: #cbd5e1;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #94a3b8;
}
</style>
