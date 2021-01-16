<template>
  <div>
    <div>
      <input v-model="inputValue"/>
      <button @click="handleSubmit">提交</button>
    </div>

    <ul>
      <todo-item v-for="(item,index) of list"
                 :key="index"
                 :content="item"
                 :index="index"
                 @delete="handleDelete">

      </todo-item>

    </ul>
  </div>
</template>

<script>
import todoItem from './components/todoItem'
export default {
  components: {
    'todo-item': todoItem
  },
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit: function () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete: function (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>

</style>
