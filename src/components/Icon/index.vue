<template>
  <el-icon>
    <SvgIcon v-if="isSvgIcon" :name="icon.substring(5)" :icon-style="{ width: 'inherit', height: 'inherit' }" />
    <component v-else-if="props.icon" :is="props.icon"></component>
  </el-icon>
</template>

<script setup lang="ts">
import { computed } from "vue";
import SvgIcon from "@/components/SvgIcon/index.vue";

const props = defineProps({
  icon: {
    type: [String, Object],
    required: true
  }
});

const isSvgIcon = computed(() => {
  return typeof props.icon === "string" && props.icon.startsWith("icon-");
});
</script>
