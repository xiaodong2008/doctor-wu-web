<script setup lang="ts">
defineProps<{
  avatarUrl: string
  name: string
  link?: string
}>()
</script>

<template>
  <a
    class="base !border-none !no-underline !text-[var(--fg-light)] inline-flex rounded-4 !h-6 pr-2 py-[0px] vertical-mid box-content relative mb-[2px] bg-[#8883]"
    hover="bg-[#8884] !bg-op40 !text-[var(--fg)]" flex="items-center justify-start"
    :href="link ?? 'javascript: void 0;'" target="_blank" font-condensed
  >
    <img class="inline !rounded-4 h-5 !w-5 ml-[2px]" :src="avatarUrl" alt="Avatar">
    <span class="ml-1 text-sm">{{ name }}</span>
  </a>
</template>

<style scoped>
.base {
  overflow: hidden;
}

.base::before {
  content: '';
  position: absolute;
  left: -110%;
  top: 0;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(
    90deg,
    rgba(255, 255, 255, 0),
    rgba(255, 255, 255, 0.5),
    rgba(255, 255, 255, 0)
  );
}

.base:hover {
  &::before {
    left: 110%;
    transition: all 0.8s;
  }
}
</style>
