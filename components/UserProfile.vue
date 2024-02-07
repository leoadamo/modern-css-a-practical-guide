<script setup>
  defineProps({
    user: {
      type: Object,
      required: true,
    },
  });
</script>

<template>
  <div class="flex items-center gap-4">
    <img 
      :src="user.thumbnail" 
      :alt="`${user.name} profile picture`"
      class="w-10 h-10 rounded-full" 
    >

    <div class="font-medium">
      <h2 class="!text-white !text-sm !mb-none">
        {{ user.name }}
      </h2>

      <a 
        :href="user.twitter"
        target="_blank"
        class="text-xs text-gray-500"
      >
        {{user.nickname}}
      </a>
    </div>
  </div>
</template>