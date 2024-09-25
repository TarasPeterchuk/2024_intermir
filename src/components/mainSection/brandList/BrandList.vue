<template>
  <div class="brand-list">
    <div class="brand-list__header">
      <h4 class="brand-list__header-label">Бренди</h4>
      <BaseButton color="secondary">Дивитися усі</BaseButton>
    </div>
    <div class="brand-list__items">
      <BrandCard
        v-for="index in 16"
        :key="index"
        image="Hermossa Logo Beyaz.png"
      />
    </div>
  </div>
</template>
<script setup>
import BaseButton from '@/components/kit/BaseButton.vue';
import BrandCard from '@/components/mainSection/brandList/components/BrandCard.vue';
</script>

<style scoped lang="scss">
.brand-list__header {
  display: flex;
  justify-content: space-between;
}
.brand-list__header-label {
  width: 50%;
  font-size: 48px;
  font-weight: 700;
  line-height: 56px;
  padding-bottom: 8px;
  color: #ffffff;
  border-bottom: 2px solid #ffffff;
}
.brand-list__items {
  display: grid;
  grid-template-columns: repeat(4, auto);
  justify-content: space-between;
  margin: 40px 0;
  gap: 24px;
}
</style>
