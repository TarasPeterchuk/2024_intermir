<template>
  <footer class="page-footer">
    <div class="page-footer__body">
      <img
        class="page-footer__logo"
        src="@/assets/images/logo_dark.png"
        alt="logo"
      />
      <BaseButton>Підписатися</BaseButton>
    </div>
    <span class="page-footer__copyright">© 2024 All right reserved</span>
  </footer>
</template>
<script setup>
import BaseButton from '@/components/kit/BaseButton.vue';
</script>

<style scoped lang="scss">
.page-footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  &__body {
    display: flex;
    margin: 64px 0;
  }

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
  &__copyright {
    margin: 24px 0;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    color: #adadad;
  }
}
</style>
