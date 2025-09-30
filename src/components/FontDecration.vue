<template>
  <div class="tab-header">
    <h2><slot>脚本录制</slot></h2>
    <!-- <div class="tab-actions">
      <button class="btn btn-primary">
        <i class="fas fa-play"></i> 操作步骤
      </button>
    </div> -->
  </div>
</template>

<script>
export default {}
</script>

<style>
.tab-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
  padding-bottom: 16px;
  border-bottom: 1px solid #e5e7eb;
}

.tab-header h2 {
  font-size: 20px;
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
</style>
