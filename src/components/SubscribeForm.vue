<template>
  <form class="subscribe-form" @submit.prevent="submitForm">
    <span class="subscribe-form__label">Підпишіться на розсилку</span>
    <BaseInput placeholder="Ім'я" v-model="name" />
    <BaseButton type="submit">Підписатися</BaseButton>
  </form>
</template>

<script setup>
import BaseButton from '@/components/kit/BaseButton.vue';
import BaseInput from '@/components/kit/BaseInput.vue';

import { ref } from 'vue';

const name = ref('');

const submitForm = () => {
  if (name.value) {
    name.value = '';
  }
};
</script>

<style scoped lang="scss">
.subscribe-form {
  display: flex;
  flex-direction: column;
  width: 362px;
  gap: 8px;

  &__label {
    font-size: 24px;
    font-weight: 700;
    line-height: 32px;
  }
}
</style>
