<script setup>
  defineProps({
    title: {
      type: String,
      required: true,
    },
  });
</script>

<template>
  <footer
    v-if="title || social"
    class="
      flex 
      w-full 
      absolute 
      bottom-0 
      left-0 
      px-4
      py-0.5 
      bg-barBottom
      text-xs
      text-gray-700 
      font-bold 
      z-50
    "
  >
    <div class="w-1/2 text-left">
      {{ title }}

      <slot name="flag">
        <twemoji-flag-brazil />
      </slot>
    </div>

    <div class="w-1/2 flex justify-end">
      <slot />
    </div>
  </footer>
</template>
