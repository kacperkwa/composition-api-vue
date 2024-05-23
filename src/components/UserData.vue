<template>
  <h2>{{ userName }}</h2>
  <h3>{{ props.age }}</h3>
</template>
<script setup>
import { computed, defineProps } from 'vue';
const props = defineProps(['firstName', 'lastName', 'age']);
const userName = computed(() => {
  return (props.firstName + ' ' + props.lastName).toUpperCase();
});
</script>
