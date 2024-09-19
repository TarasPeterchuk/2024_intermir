<template>
  <a
    :href="props.item?.href"
    @click.prevent="() => {}"
    class="header-item__element"
  >
    {{ props.item.name }}
  </a>
</template>

<script setup>
const props = defineProps({
  item: {
    type: Object,
    default: () => ({}),
  },
});
</script>

<style scoped lang="scss">
.header-item__element {
  padding: 12px 24px;
  color: #ffffff;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px;
}
</style>
