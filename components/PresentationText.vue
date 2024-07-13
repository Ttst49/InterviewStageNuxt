<script setup lang="ts">
defineProps({
  content:{
    required: true
  }
})
</script>

<template>
  <div class="m-3.5 w-100 flex justify-center items-center typewriter">
    <h1
        class="h-full text-5xl"
    >
    {{content}}
  </h1>
  </div>
</template>

<style scoped>
.typewriter h1{
  overflow: hidden;
  white-space: nowrap;
  letter-spacing: .15em;
  animation:
      typing 2.5s steps(40, end) forwards;
}

@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}
</style>
