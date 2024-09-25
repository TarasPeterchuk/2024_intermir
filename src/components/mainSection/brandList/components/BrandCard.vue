<template>
  <div class="brand-card" v-if="props.image">
    <img
      class="brand-card__image"
      src="@/assets/images/Hermossa Logo Beyaz.png"
      alt="Hermossa Logo Beyaz"
    />
  </div>
</template>
<script setup>
const props = defineProps({
  image: {
    type: String,
  },
});
</script>

<style scoped lang="scss">
.brand-card {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 362px;
  height: 160px;
  background: #272626;
  border: 1px solid #525151;
}
.brand-card__image {
  width: 263px;
}
</style>
