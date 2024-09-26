<template>
  <header class="page-header">
    <img
      class="page-header__logo"
      src="@/assets/images/logo_dark.png"
      alt="logo"
    />
    <PageMenu :items="props.data?.menuItems" :uppercase="true" />
    <div class="page-header__buttons">
      <SocialMediaButtons :items="props.data?.socialMedia" />
      <div class="page-header__auth-buttons">
        <BaseButton>Зареєструватися</BaseButton>
        <BaseButton color="secondary">Увійти</BaseButton>
      </div>
    </div>
  </header>
</template>
<script setup>
import PageMenu from '@/components/pageMenu/PageMenu.vue';
import SocialMediaButtons from '@/components/SocialMediaButtons.vue';
import BaseButton from '@/components/kit/BaseButton.vue';

const props = defineProps({
  data: {
    type: Object,
    default: () => ({}),
  },
});
</script>

<style scoped lang="scss">
.page-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1520px;
  margin: 24px 0;
  &__logo {
    width: 178px;
  }
  &__buttons {
    display: flex;
    align-items: center;
    gap: 40px;
  }
  &__auth-buttons {
    display: flex;
    gap: 16px;
  }
}
</style>
