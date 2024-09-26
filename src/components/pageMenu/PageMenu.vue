<template>
  <div class="header-menu__navigation" :class="[{ vertical: props.vertical }]">
    <MenuItem
      v-for="item in $props.items"
      :key="item?.id"
      :item="item"
      :uppercase="props.uppercase"
    />
  </div>
</template>

<script setup>
import MenuItem from '@/components/pageMenu/components/MenuItem.vue';

const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
  vertical: {
    type: Boolean,
    default: false,
  },
  uppercase: {
    type: Boolean,
    default: false,
  },
});
</script>

<style scoped lang="scss">
.header-menu__navigation {
  display: flex;
}
.vertical {
  flex-direction: column;
}
</style>
