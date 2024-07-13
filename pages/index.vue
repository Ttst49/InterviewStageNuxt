<template>
  <PresentationText content="Interview du stage chez Kairios"/>
  <div v-for="(item, idx) in data" :key="item.index">
    <Bento
        v-if="currentIndex >= idx"
        :class="item.index"
        :title="item.title"
        :mini-content="item.miniContent"
        :full-content="item.fullContent"
        @click="showNext(idx)"
    />
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue"
import data from 'assets/json/data.json'
import PresentationText from "~/components/PresentationText.vue";
const currentIndex = ref(0);
const showNext = (idx: number) => {
  if (idx === currentIndex.value) {
    currentIndex.value++;
  }
};

</script>
