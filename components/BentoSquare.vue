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
  },
  size:{
    default: "sm",
    type:String
  }
})

const getSize = computed(() => {
  switch (props.size) {
    case "sm":
      return "h-48 w-48 bg-sky-500 m-1 bentoSquare";
    case "md":
      return "h-64 w-64 bg-sky-700 m-1 bentoSquare";
    case "lg":
      return "h-80 w-80 bg-sky-900 m-1 bentoSquare";
    default:
      return "";
  }
});


defineEmits({
  "open-bento": value => value
})

</script>

<template>
  <Card
      @click="$emit('open-bento',content)"
      :class="getSize"
  >
    <template #title>{{ title }}</template>
    <template #content>
      <p
          class="m-0.5">
        {{ content }}
      </p>
      {{size}}
    </template>
  </Card>
</template>

<style scoped>
.bentoSquare:hover{
  translate: -5px -5px 0;
  border: whitesmoke 1px groove;
  transition: .5s ease-out translate;
}
</style>
