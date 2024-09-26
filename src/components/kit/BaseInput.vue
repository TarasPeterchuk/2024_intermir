<template>
  <div class="base-input">
    <label v-if="props.label" class="base-input__label">{{ label }}</label>
    <input
      :type="type"
      :placeholder="placeholder"
      :value="modelValue"
      @input="emit('update:modelValue', $event.target.value)"
      class="base-input__field"
    />
  </div>
</template>

<script setup>
const props = defineProps({
  modelValue: {
    type: String,
    default: '',
  },
  label: {
    type: String,
    default: '',
  },
  placeholder: {
    type: String,
    default: '',
  },
  type: {
    type: String,
    default: 'text',
  },
});

const emit = defineEmits(['update:modelValue']);
</script>

<style scoped lang="scss">
.base-input {
  display: flex;
  flex-direction: column;
  gap: 8px;
  color: #ffffff;

  &__label {
    font-size: 16px;
    font-weight: 600;
    line-height: 24px;
  }

  &__field {
    padding: 10px 16px;
    border: 1px solid #525151;
    background-color: transparent;
    outline: none;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    color: #ffffff;

    &:hover {
      border-color: #a9a8a8;
    }
    &:focus {
      border-color: #a9a8a8;
    }
    &::placeholder {
      font-size: 16px;
      font-weight: 400;
      line-height: 24px;
      color: #adadad;
    }
  }
}
</style>
