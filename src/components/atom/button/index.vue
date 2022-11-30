<template>
  <ElButton
    :type="type"
    :plain="plain"
    :round="round"
    :icon="icon"
    :disabled="disabled"
    :loading="loading"
    :size="size"
  >
    {{ label }}
  </ElButton>
</template>

<script setup lang="ts">
  import { ElButton } from "element-plus"
  interface IButton {
    type: string
    label: string
    plain?: boolean
    round?: boolean
    icon?: string
    disabled?: boolean
    loading?: boolean
    size?: string
  }
  const { type, label, plain, round, icon, disabled, loading, size } =
    defineProps<IButton>()
  // import { defineComponent } from "vue"

  // export default defineComponent({
  //   name: "Button",
  //   props: {
  //     label: {
  //       type: String,
  //     },
  //     type: {
  //       type: String,
  //     },
  //     plain: {
  //       type: Boolean,
  //     },
  //     rounded: {
  //       type: Boolean,
  //     },
  //     icon: {
  //       type: String,
  //     },
  //     disabled: Boolean,
  //     loading: Boolean,
  //     size: {
  //       type: String,
  //     },
  //     rest: {
  //       type: null,
  //     },
  //   },
  //   components: {
  //     ElButton,
  //   },
  // })
</script>
