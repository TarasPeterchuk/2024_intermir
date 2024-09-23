<template>
  <div class="base-carousel">
    <div
      class="base-carousel__inner"
      :style="{ transform: `translateX(${-currentIndex * 100}%)` }"
    >
      <div
        class="base-carousel__slide"
        v-for="(image, index) in props.items"
        :key="index"
      >
        <img :src="images[image]" :alt="image" class="base-carousel__image" />
      </div>
    </div>

    <BaseButton
      color="secondary"
      rounded
      :size="56"
      class="base-carousel__prev-button"
      @click="prevImage"
      ><ArrowLeft
    /></BaseButton>

    <BaseButton
      color="secondary"
      rounded
      :size="56"
      class="base-carousel__next-button"
      @click="nextImage"
      ><ArrowRight
    /></BaseButton>
    <div class="carousel-indicators">
      <div
        v-for="(image, index) in props.items"
        :key="index"
        :class="['indicator', { active: currentIndex === index }]"
      ></div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import BaseButton from '@/components/kit/BaseButton.vue';
import ArrowLeft from '@/components/icons/ArrowLeft.vue';
import ArrowRight from '@/components/icons/ArrowRight.vue';

const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});

const currentIndex = ref(0);

const imageModules = import.meta.glob('@/assets/images/*.png', { eager: true });
const images = Object.fromEntries(
  Object.entries(imageModules).map(([path, module]) => [
    path.split('/').pop(),
    module.default,
  ])
);

const prevImage = () => {
  if (currentIndex.value === 0) {
    currentIndex.value = props.items.length - 1;
  } else {
    currentIndex.value -= 1;
  }
};

const nextImage = () => {
  if (currentIndex.value === props.items.length - 1) {
    currentIndex.value = 0;
  } else {
    currentIndex.value += 1;
  }
};
</script>

<style scoped lang="scss">
.base-carousel {
  position: relative;
  // width: 100%;
  overflow: hidden;

  &__inner {
    display: flex;
    transition: transform 0.5s ease;
    width: 100%;
  }

  &__slide {
    min-width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  &__image {
    min-width: 100%;
    max-width: 100%;
    max-height: 100%;
    object-fit: cover;
  }

  &__prev-button,
  &__next-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    z-index: 1;
  }

  &__prev-button {
    left: 40px;
  }

  &__next-button {
    right: 40px;
  }
  .carousel-indicators {
    display: flex;
    justify-content: center;
    margin-top: 50px;
    gap: 6px;

    .indicator {
      width: 12px;
      height: 12px;
      background-color: #323131;
      border-radius: 6px;
      transition: background-color 0.3s, width 0.3s;

      &.active {
        width: 64px;
        height: 12px;
        background-color: #ffffff;
      }
    }
  }
}
</style>
