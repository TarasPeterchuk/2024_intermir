<template>
  <div class="header-menu__social-media">
    <ButtonIconLink v-for="item in props.items" :key="item?.id" :item="item" />
  </div>
</template>

<script setup>
import ButtonIconLink from '@/components/kit/ButtonIconLink.vue';

const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped lang="scss">
.header-menu__social-media {
  display: flex;
  gap: 16px;
}
</style>
