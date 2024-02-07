<script setup>
  defineProps({
    text: {
      type: String,
      required: true,
    },

    url: {
      type: String,
      required: true
    }
  });
</script>

<template>
  <a 
    :href="url" 
    :title="text"
    target="_blank" 
    rel="noopener noreferrer"
    class="
      flex 
      justify-center 
      items-center 
      gap-0.5 
      ml-4
      transition-colors
      !text-gray-700
      !hover:text-white
    "
  >
    <span class="flex justify-center item-center">
      <slot />
    </span>
  
    <span class="ml-0.5">
      {{ text }}
    </span>
  </a>
</template>
