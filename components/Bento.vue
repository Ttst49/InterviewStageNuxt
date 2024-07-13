<template>
  <Card
      @click="$emit('open-bento', miniContent)"
      :class="[
          getSize,
      'm-3 bento cursor-pointer',
      { 'focused': isFocus }
      ]"
      @focus="isFocus = true"
      @blur="isFocus = false"
      tabindex="0"
  >
    <template #title>{{ title }}</template>
    <template #content>
      <transition name="fade">
      <p class="m-0.5">{{ isFocus ? fullContent : miniContent }} </p>
      </transition>
    </template>
  </Card>
</template>

<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  miniContent: {
    type: String,
    default: "Rien par ici",
    required: false,
  },
  fullContent:{
    type:String,
    default:"Rien par ici"
  },
  size: {
    default: "sm",
    type: String,
  },
  isRectangle: {
    default: false,
    type: Boolean,
  },
});

const getSize = computed(() => {
  if (props.isRectangle) {
    switch (props.size) {
      case "sm":
        return "h-40 w-64";
      case "md":
        return "h-48 w-80";
      case "lg":
        return "h-64 w-96";
      default:
        return "";
    }
  }
  switch (props.size) {
    case "sm":
      return "h-48 w-48";
    case "md":
      return "h-64 w-64";
    case "lg":
      return "h-80 w-80";
    default:
      return "";
  }
});

defineEmits({
  "open-bento": (value) => value,
});

const isFocus = ref(false);
</script>

<style scoped>
.bento {
  transition: 0.5s ease-out transform, 0.5s ease-out width;
}
.bento:focus{
  transform: translate(-5px, -5px);
  border: 1px groove whitesmoke;
  height: 100%;
  width: 98%;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
</style>
