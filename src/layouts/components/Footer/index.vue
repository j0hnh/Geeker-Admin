<template>
  <div class="footer flx-center">
    <a>{{ year }} © </a>
    <a style="font-size: 12px; color: var(--el-text-color-secondary)" class="ml10">
      (版本号:{{ version }} 发布时间:{{ lastBuildTime }})
    </a>
  </div>
</template>

<script setup lang="ts">
const { pkg, lastBuildTime } = __APP_INFO__;
const { version } = pkg;

const year = new Date().getFullYear();
</script>

<style scoped lang="scss">
@import "./index.scss";
</style>
