<template>
  <div class="clients-map">
    <div class="clients-map__header">
      <h4 class="clients-map__header-label">Наші клієнти</h4>
    </div>
    <p class="clients-map__subtitle">Більше 500 клієнтів по всій Україні</p>
    <img
      class="clients-map__map"
      src="@/assets/images/Ukraine Map.png"
      alt="Ukraine Map"
    />
  </div>
</template>

<script setup></script>

<style scoped lang="scss">
.clients-map {
  &__header-label {
    width: 50%;
    font-size: 48px;
    font-weight: 700;
    line-height: 56px;
    padding-bottom: 8px;
    color: #ffffff;
    border-bottom: 2px solid #ffffff;
  }
  &__items {
    display: grid;
    grid-template-columns: repeat(3, auto);
    justify-content: space-between;
    margin: 40px 0;
    gap: 24px;
  }
  &__subtitle {
    margin-top: 40px;
    font-size: 24px;
    font-weight: 700;
    line-height: 32px;
  }
  &__map {
    margin-top: 40px;
  }
}
</style>
