<template>
  <HeaderMenu :menuData="pageData?.menu" />
  <main>
    <IntroSlide />
    <BrandStory :style="{ margin: '160px 200px 0 200px' }" />
    <BaseCaroucel
      :items="pageData?.caroucelImagesWoman"
      :style="{ margin: '80px 200px 0 200px' }"
    />
    <BrandList :style="{ margin: '80px 200px 0 200px' }" />
    <BaseCaroucel
      :items="pageData?.caroucelImagesMen"
      :style="{ margin: '80px 200px 0 200px' }"
      ><img
        src="@/assets/images/AZZARO blanc fond transparent 1.png"
        alt="AZZARO blanc fond transparent"
    /></BaseCaroucel>
    <EventsOverview
      :items="pageData?.events"
      :style="{ margin: '160px 200px 0 200px' }"
    />
    <ClientsMap :style="{ margin: '160px 200px 0 200px' }" />
  </main>
  <PageFooter :style="{ margin: '0 200px' }" />
</template>
<script setup>
import HeaderMenu from '@/components/headerMenu/HeaderMenu.vue';
import PageFooter from '@/components/pageFooter/PageFooter.vue';
import IntroSlide from '@/components/mainSection/IntroSlide.vue';
import BrandStory from '@/components/mainSection/BrandStory.vue';
import BaseCaroucel from '@/components/kit/BaseCaroucel.vue';
import BrandList from '@/components/mainSection/brandList/BrandList.vue';
import EventsOverview from '@/components/mainSection/eventsOverview/EventsOverview.vue';
import ClientsMap from '@/components/mainSection/ClientsMap.vue';
import { useTheme } from '@/utils/useTheme';
import { pageData } from './pageData.js';
useTheme();
</script>
<style scoped></style>
