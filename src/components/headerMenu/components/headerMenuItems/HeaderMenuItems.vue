<template>
  <div class="header-menu__navigation">
    <HeaderMenuItem v-for="item in $props.items" :key="item?.id" :item="item" />
  </div>
</template>

<script setup>
import HeaderMenuItem from '@/components/headerMenu/components/headerMenuItems/components/HeaderMenuItem.vue';

defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped lang="scss"></style>
