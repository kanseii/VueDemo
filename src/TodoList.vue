<template>
  <div>
    <div>
      <input v-model="inputValue">
      <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item
        v-for="(item,index) of list"
        :key="index"
        :content="item"
        :index="index"
        @delete="handleDelete"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem' // 在Javascript中引入组件
export default {
  components: {
    'todo-item': TodoItem
  },

  data: function() {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit() {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete(index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
