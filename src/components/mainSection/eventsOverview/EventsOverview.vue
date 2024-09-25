<template>
  <div class="events-overview">
    <div class="events-overview__header">
      <h4 class="events-overview__header-label">Заходи</h4>
      <BaseButton color="secondary">Дивитися усі</BaseButton>
    </div>
    <div class="events-overview__items">
      <EventCard v-for="item in props.items" :key="item" :item="item" />
    </div>
  </div>
</template>
<script setup>
import BaseButton from '@/components/kit/BaseButton.vue';
import EventCard from '@/components/mainSection/eventsOverview/components/EventCard.vue';
const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});
</script>

<style scoped lang="scss">
.events-overview__header {
  display: flex;
  justify-content: space-between;
}
.events-overview__header-label {
  width: 50%;
  font-size: 48px;
  font-weight: 700;
  line-height: 56px;
  padding-bottom: 8px;
  color: #ffffff;
  border-bottom: 2px solid #ffffff;
}
.events-overview__items {
  display: grid;
  grid-template-columns: repeat(3, auto);
  justify-content: space-between;
  margin: 40px 0;
  gap: 24px;
}
</style>
