<template>
  <div>
    <div class="w-100 d-flex flex-row">
      <BentoSquare
          @open-bento="openBento"
          class="col-3"
          title="coucou"
          size="sm"
      />
      <BentoSquare
          @open-bento="openBento"
          class="col-3"
          title="coucou"
          size="sm"
      />
      <BentoSquare
          @open-bento="openBento"
          class="col-3"
          title="coucou"
          size="sm"
      />
    </div>
    <BentoSquare
        @open-bento="openBento"
        title="salut"
        size="lg"
    />
    <BentoSquare
        @open-bento="openBento"
        title="hey hay"
        size="md"
    />
  </div>
</template>
<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps({
  visible: {
    default: false,
    type: Boolean
  }
});

const emit = defineEmits(['update:visible']);


const openBento = () => {
};
</script>
