<script setup lang="ts">
const {
  modelValue,
  placeholder = "",
  type = "text",
  id,
  required = false,
} = defineProps<{
  modelValue: string;
  placeholder?: string;
  type?: string;
  id: string;
  required?: boolean;
}>();

const emit = defineEmits<{
  (e: "update:modelValue", value: string): void;
}>();

const updateModelValue = (event: Event) => {
  const target = event.target as HTMLInputElement;
  emit("update:modelValue", target.value);
};
</script>
<template>
  <input
    :id="id"
    :required="required"
    :value="modelValue"
    :placeholder="placeholder"
    :type="type"
    @input="updateModelValue"
    class="py-4 px-[18px] text-xl text-dark font-medium border-[3px] rounded-xl w-full max-w-[320px] focus:outline-none focus:bg-yellow focus:shadow-primary-shadow"
  />
</template>
