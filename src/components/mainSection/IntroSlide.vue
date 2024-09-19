<template>
  <div class="intro-slide__wrapper">
    <img
      class="intro-slide__image"
      src="@/assets/images/02_AZZARO SUN_EDIT_16_9 (1) 1@2x.png"
      alt="intro-image"
    />
    <h1 class="intro-slide__label">ЛОРЕМ ІПСУМ<br />ДОЛОР СІТ АМЕТ</h1>
  </div>
</template>
<script setup></script>

<style scoped lang="scss">
.intro-slide__wrapper {
  position: relative;
  max-width: 100vw;
  overflow-x: hidden;
  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, rgba(39, 38, 38, 0) 0%, #272626 100%);
  }
}
.intro-slide__image {
  width: 100%;
  height: auto;
}
.intro-slide__label {
  position: absolute;
  bottom: 200px;
  left: 200px;
  right: 200px;
  font-size: 80px;
  font-weight: 700;
  line-height: 88px;
  text-align: left;
  color: #ffffff;
  border-bottom: 2px solid #ffffff;
}
</style>
