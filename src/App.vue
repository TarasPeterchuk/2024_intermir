<template>
  <HeaderMenu :menuData="pageData?.menu" />
  <main>
    <IntroSlide />
    <BrandStory :style="{ marginTop: '160px' }" />
    <BaseCaroucel
      :items="pageData?.caroucelImages"
      :style="{ margin: '0 200px', marginTop: '80px' }"
    />
  </main>
  <footer></footer>
</template>
<script setup>
import HeaderMenu from '@/components/headerMenu/HeaderMenu.vue';
import IntroSlide from '@/components/mainSection/IntroSlide.vue';
import BrandStory from '@/components/mainSection/BrandStory.vue';
import BaseCaroucel from '@/components/kit/BaseCaroucel.vue';

import { pageData } from './pageData.js';
</script>
<style scoped>
.page-header {
  display: flex;

  align-items: center;
}
</style>
