<template>
  <a :href="props.item?.href" @click.prevent="() => {}" class="button-link">
    <component :is="getComponentType(props.item?.icon)" />
  </a>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';

const IconFacebook = defineAsyncComponent(() =>
  import('@/components/icons/IconFacebook.vue')
);
const IconTelegram = defineAsyncComponent(() =>
  import('@/components/icons/IconTelegram.vue')
);
const IconWhatsapp = defineAsyncComponent(() =>
  import('@/components/icons/IconWhatsapp.vue')
);
const IconInstagram = defineAsyncComponent(() =>
  import('@/components/icons/IconInstagram.vue')
);
const IconFacebookDark = defineAsyncComponent(() =>
  import('@/components/icons/IconFacebookDark.vue')
);
const IconLinkedin = defineAsyncComponent(() =>
  import('@/components/icons/IconLinkedin.vue')
);
const IconTelegramDark = defineAsyncComponent(() =>
  import('@/components/icons/IconTelegramDark.vue')
);

const props = defineProps({
  item: {
    type: Object,
    default: () => ({}),
  },
});

function getComponentType(type) {
  const typeToComponent = {
    facebook: IconFacebook,
    telegram: IconTelegram,
    whatsapp: IconWhatsapp,
    instagram: IconInstagram,
    facebookDark: IconFacebookDark,
    linkedin: IconLinkedin,
    telegramDark: IconTelegramDark,
  };

  return typeToComponent[type] || '';
}
</script>

<style scoped lang="scss">
.header-item__element {
  padding: 12px 24px;
  color: #ffffff;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px;
  &:hover {
    font-weight: 600;
  }
}
</style>
