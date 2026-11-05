<script setup lang="ts">
const value = ref("123");
const pemis = ref("123");
const emit = defineEmits<{ (e: "submit-form"): void }>();
</script>
<template>
  <form @submit.prevent="emit('submit-form')">
    <FormInput v-model="value" id="user-email" placeholder="email" type="email" label="email" required />
    <PasswordInput />
  </form>
</template>
