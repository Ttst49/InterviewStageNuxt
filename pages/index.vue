<template>
  <div>
    <Bento
        @open-bento="openBento"
        class="col-3"
        title="coucou"
        size="sm"
        :is-rectangle="false"
    />
    <Bento
        @open-bento="openBento"
        class="col-3"
        title="coucou"
        size="sm"
        :is-rectangle="true"
    />
    <Bento
        @open-bento="openBento"
        class="col-3"
        title="coucou"
        size="md"
        :is-rectangle="false"
    />
    <Bento
        @open-bento="openBento"
        class="col-3"
        title="coucou"
        size="md"
        :is-rectangle="true"
    />
    <Bento
        @open-bento="openBento"
        class="col-3"
        title="coucou"
        size="lg"
        :is-rectangle="false"
    />
    <Bento
        @open-bento="openBento"
        class="col-3"
        title="coucou"
        size="lg"
        :is-rectangle="true"
    />
  </div>
</template>
<script setup lang="ts">
import { defineProps } from 'vue';
import Bento from "~/components/Bento.vue";

const props = defineProps({
  visible: {
    default: false,
    type: Boolean
  }
});

defineEmits(['update:visible']);


const openBento = () => {
};
</script>
