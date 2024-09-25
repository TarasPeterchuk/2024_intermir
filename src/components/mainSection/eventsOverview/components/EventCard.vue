<template>
  <div class="event-card">
    <img
      class="event-card__image"
      src="@/assets/images/unsplash_aEnH4hJ_Mrs.png"
      alt="unsplash_aEnH4hJ_Mrs"
    />
    <div class="event-card__detail">
      <IconCalendar />
      <span>{{ formattedDate(props.item?.date) }}</span>
    </div>
    <div class="event-card__detail">
      <IconLocation />
      <span>{{ props.item?.location }}</span>
    </div>
    <h4 class="event-card__subject">{{ props.item?.subject }}</h4>
    <p class="event-card__description">{{ props.item?.description }}</p>
  </div>
</template>
<script setup>
import IconCalendar from '@/components/icons/IconCalendar.vue';
import IconLocation from '@/components/icons/IconLocation.vue';
const props = defineProps({
  item: {
    type: Object,
    default: () => ({}),
  },
});

const options = { year: 'numeric', month: 'long', day: '2-digit' };
const formattedDate = (date) =>
  new Date(date).toLocaleDateString('en-US', options);
</script>

<style scoped lang="scss">
.event-card {
  display: flex;
  min-width: 491px;
  height: 540px;
  padding: 16px 16px 24px 16px;
  flex-direction: column;
  gap: 10px;
  background: #323131;
  box-shadow: 0px 10px 20px 0px #1c1c1c40;

  &__detail {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 16px;
    font-weight: 600;
    line-height: 24px;
    color: #adadad;
  }

  &__subject {
    margin-top: 16px;
    font-size: 24px;
    font-weight: 700;
    line-height: 32px;
  }
  &__description {
    font-size: 16px;
    line-height: 24px;
  }
}
</style>
