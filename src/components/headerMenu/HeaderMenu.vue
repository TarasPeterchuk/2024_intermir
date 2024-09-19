<template>
  <header class="header-menu">
    <img
      class="header-menu__logo"
      src="@/assets/images/logo_dark.png"
      alt="logo"
    />
    <HeaderMenuItems :items="props.menuData?.items" />
    <div class="header-menu__buttons">
      <SocialMediaButtons :items="props.menuData?.socialMedia" />
      <div class="header-menu__auth-buttons">
        <BaseButton>Зареєструватися</BaseButton>
        <BaseButton color="secondary">Увійти</BaseButton>
      </div>
    </div>
  </header>
</template>
<script setup>
import HeaderMenuItems from '@/components/headerMenu/components/headerMenuItems/HeaderMenuItems.vue';
import SocialMediaButtons from '@/components/headerMenu/components/socialMediaButtons/SocialMediaButtons.vue';
import BaseButton from '@/components/kit/BaseButton.vue';

const props = defineProps({
  menuData: {
    type: Object,
    default: () => ({}),
  },
});
</script>

<style scoped lang="scss">
.header-menu {
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
