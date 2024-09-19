<template>
  <div class="brand-story__wrapper">
    <p class="brand-story__text">
      Подорож Hermossa почалася в 2014 році як модний бренд у Туреччині,
      унікальний у гармонії європейського сучасного дизайну з турецькою
      культурою.
    </p>
    <BaseButton color="secondary">Дізнатися більше</BaseButton>
  </div>
</template>
<script setup>
import BaseButton from '@/components/kit/BaseButton.vue';
</script>

<style scoped lang="scss">
.brand-story__wrapper {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding: 0 200px;
}
.brand-story__text {
  font-size: 24px;
  line-height: 32px;
  text-align: left;
  color: #ffffff;
  max-width: 40%;
}
</style>
