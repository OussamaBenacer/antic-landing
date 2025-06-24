<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
defineProps({
  href: {
    type: String,
    default: "#",
  },
});
</script>

<template>
  <a
    :href="href"
    class="flex items-center gap-1 font-bold font-karla text-terracotta"
  >
    <slot /> <IconsChevronDown width="12" class-name="-rotate-90" />
  </a>
</template>
