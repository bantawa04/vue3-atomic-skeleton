<template>
  <BaseInput :label="`Title`" v-model="title" />
  <BaseInput2 :label="`Title`" v-model="title2" />
  {{ title }}
  {{ title2 }}
</template>
<script setup lang="ts">
  import { ref } from "vue"
  // import Button from "./atom/button/index.vue"
  import BaseInput2 from "./atom/input/index2.vue"
  import BaseInput from "./atom/input/index.vue"

  // interface Book {
  //   title?: string
  //   price?: number
  // }
  // const book: Book = reactive({})
  const title = ref<string>("")
  const title2 = ref<string>("")
  const price = ref<string | number>("")
  const buttonClick = (type: string): void => {
    console.log(`${type} type button pressed`)
  }
</script>
