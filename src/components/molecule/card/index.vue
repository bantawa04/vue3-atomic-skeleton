<template>
  <el-card class="box-card">
    <template v-if="title" #header>
      <div class="card-header">
        <span>Card name</span>
        <Button :label="`Action`" type="`warning`" />
      </div>
    </template>
    <div v-for="o in 4" :key="o" class="text item">{{ "List item " + o }}</div>
  </el-card>
</template>
<script lang="ts">
  import { defineComponent } from "vue"
  import { ElCard } from "element-plus"
  import Button from "../../atom/button/index.vue"
  export default defineComponent({
    props: {
      title: String,
      content: Array || Object,
      buttonAction: Function,
    },
    components: {
      Button,
      ElCard,
    },
  })
</script>
<style>
  .card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .text {
    font-size: 14px;
  }

  .item {
    margin-bottom: 18px;
  }

  .box-card {
    width: 480px;
  }
</style>
