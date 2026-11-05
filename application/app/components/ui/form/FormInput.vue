<script setup lang="ts">
const {
  modelValue,
  placeholder = "",
  type = "text",
  id,
  label,
  required = false,
  message,
} = defineProps<{
  modelValue: string;
  placeholder: string;
  type: string;
  id: string;
  label?: string;
  required?: boolean;
  message?: string;
}>();

const emit = defineEmits<{
  (e: "update:modelValue", value: string): void;
}>();
</script>
<template>
  <div class="flex flex-col gap-2">
    <label v-if="label" :for="id" class="font-mono uppercase cursor-pointer">{{ label }} <span v-if="required">*</span></label>
    <BaseInput
      :id="id"
      :required="required"
      :model-value="modelValue"
      :placeholder="placeholder"
      :type="type"
      @update:model-value="emit('update:modelValue', $event)"
    />
    <p v-if="message" class="text-muted text-sm font-medium">{{ message }}</p>
  </div>
</template>
