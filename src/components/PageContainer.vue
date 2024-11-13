<template>
  <el-card class="page-container">
    <template #header>
      <div class="header">
        <!-- 文章管理 -->
        <span>{{ title }}</span>
        <div class="extra">
          <!-- 添加文章按钮也不要写死，用具名插槽 -->
          <slot name="extra"></slot>
        </div>
      </div>
    </template>
    <!-- 默认插槽定制内容 -->
    <slot></slot>
  </el-card>
</template>

<style lang="scss" scoped>
.page-container {
  min-height: 100%;
  box-sizing: border-box;
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
<script setup>
// 父传子 title文章管理
defineProps({
  title: {
    required: true,
    type: String
  }
})
</script>
