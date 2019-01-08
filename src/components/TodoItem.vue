<template>
    <li @click="handleDelete">{{content}}</li>
</template>

<script>
export default {
  props: ['content', 'index'],   // 声明使用 引用来自父组件的值
  methods: {
    handleDelete () {
      this.$emit('delete', this.index)
    }
  }
}

</script>

<style>

</style>
