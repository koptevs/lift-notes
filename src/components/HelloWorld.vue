<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <h1 class="font-bold text-2xl text-indigo-700">{{ msg }}</h1>
</template>
