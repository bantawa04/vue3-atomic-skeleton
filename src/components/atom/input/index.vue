<template>
  <el-form-item :label="label">
    <ElInput
      :autofocus="true"
      :type="type"
      :placeholder="placeholder"
      :show-word-limit="showWordLimit"
      :clearable="clearable"
      :show-password="showPassword"
      :suffix-icon="suffixIcon"
      :prefix-icon="prefixIcon"
      :size="size"
      :max-length="maxLength"
      v-model="val"
    >
      <template v-if="prepend" #prepend>Http://</template>
      <template v-if="append" #append>.com</template>
    </ElInput>
  </el-form-item>
</template>
<script setup lang="ts">
  import { computed, toRefs } from "vue"
  import { ElInput, ElFormItem } from "element-plus"
  interface IInput {
    label: string
    type?: string
    placeholder?: string
    maxLength?: number
    showWordLimit?: boolean
    clearable?: boolean
    showPassword?: boolean
    suffixIcon?: any
    prefixIcon?: any
    size?: string
    prepend?: any
    append?: any
    modelValue: any
  }

  const props = defineProps<IInput>()
  const {
    label,
    type,
    placeholder,
    maxLength,
    showWordLimit,
    clearable,
    showPassword,
    suffixIcon,
    prefixIcon,
    size,
    prepend,
    append,
    modelValue,
  } = toRefs(props)

  const emit = defineEmits(["update:modelValue"])

  const val = computed({
    get() {
      return modelValue.value
    },
    set(val) {
      emit("update:modelValue", val)
    },
  })
</script>
