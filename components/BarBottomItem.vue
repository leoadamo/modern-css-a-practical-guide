<script setup>
defineProps({
  text: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="flex justify-center items-center ml-4">
    <span class="flex justify-center item-center">
      <slot />
    </span>

    <span class="ml-0.5">
      {{ text }}
    </span>
  </div>
</template>
