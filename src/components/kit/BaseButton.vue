<template>
  <button
    class="base-button"
    @click="handleClick"
    :class="[color, { rounded: props.rounded }]"
  >
    <div v-if="$slots.default" class="base-button__label">
      <slot></slot>
    </div>
  </button>
</template>

<script setup>
import { computed } from 'vue';
const props = defineProps({
  label: String,
  size: {
    type: [String, Number],
    default: 48,
  },
  color: {
    type: String,
    default: 'primary',
    validator: (prop) => ['primary', 'secondary'].includes(prop),
  },
  rounded: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(['click']);

const handleClick = (event) => {
  emit('click', event);
};

const buttonHeigth = computed(
  () => parseInt(props.size) && parseInt(props.size) + 'px'
);
</script>

<style scoped lang="scss">
.base-button {
  display: flex;
  align-items: center;
  justify-content: center;
  height: v-bind(buttonHeigth);
  min-height: v-bind(buttonHeigth);
  max-height: v-bind(buttonHeigth);
  min-width: v-bind(buttonHeigth);
  cursor: pointer;
  font-size: 16px;
  padding: 0 12px;
  border: 1px solid #ffffff;

  &.primary {
    background-color: #ffffff;
    color: #27348b;
  }
  &.secondary {
    background-color: transparent;
    color: #ffffff;
  }

  &.rounded {
    padding: 0;
    border-radius: 999px;
    border-color: #323131;
    background: #323131;
  }
}
</style>
