<script setup lang="ts">
const {
  to,
  variant = "primary",
  size = "md",
} = defineProps<{
  to?: string;
  variant?: "primary";
  size?: "md";
}>();

const rendereElement = computed(() => (to ? "NUXT_LINK" : "button"));
</script>
<template>
  <component :is="rendereElement" v-bind="{ variant }">
    <slot />
  </component>
</template>
