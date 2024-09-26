<template>
  <footer class="page-footer">
    <div class="page-footer__body">
      <div class="page-footer__redirects">
        <img
          class="page-footer__logo"
          src="@/assets/images/logo_dark.png"
          alt="logo"
        />
        <PageMenu :items="props.data?.menuItems" :vertical="true" />
      </div>
      <div class="page-footer__subscribe-social">
        <SubscribeForm />
        <SocialMediaButtons :items="props.data?.socialMedia" />
      </div>
    </div>
    <span class="page-footer__copyright">© 2024 All right reserved</span>
  </footer>
</template>
<script setup>
import PageMenu from '@/components/pageMenu/PageMenu.vue';
import SubscribeForm from '@/components/SubscribeForm.vue';
import SocialMediaButtons from '@/components/SocialMediaButtons.vue';

const props = defineProps({
  data: {
    type: Object,
    default: () => ({}),
  },
});
</script>

<style scoped lang="scss">
.page-footer {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  background: #323131;

  &__body {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin: 64px 0;
  }
  &__redirects {
    display: flex;
    gap: 80px;
  }
  &__logo {
    width: 178px;
    height: max-content;
  }

  &__subscribe-social {
    display: flex;
    flex-direction: column;
    gap: 40px;
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
