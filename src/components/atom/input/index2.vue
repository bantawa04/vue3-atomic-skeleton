<template>
  <label for="">{{ label }}</label>
  <input
    :value="modelValue"
    @input="$emit('update:modelValue', handleInputChange($event))"
  />
</template>
<script setup lang="ts">
  interface IInput {
    label: string
    modelValue: any
  }
  const { label, modelValue } = defineProps<IInput>()
  const handleInputChange = (event: Event) => {
    console.log(typeof modelValue)
    // console.log((event.target as HTMLInputElement).value)
    return (event.target as HTMLInputElement).value
  }
</script>
