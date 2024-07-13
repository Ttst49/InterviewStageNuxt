<script setup lang="ts">
const props = defineProps({
  title:{
    type: String,
    required:true,
  },
  content:{
    type: String,
    default:'nothing to show',
    required: false
  }
})
</script>

<template>
  <Card class="w-1/3 h-1/3 m-2.5">
    <template #title>{{ title }}</template>
    <template #content>
      <p class="m-0.5">
        {{ content }}
      </p>
    </template>
  </Card>
</template>

<style scoped>

</style>
