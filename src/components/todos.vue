<template>
  <div class="todo-list">
      <todo 
      :key="todo.id" 
      v-for="todo in todos" 
      :todo="todo" @check-todo="$emit('check-todo', todo.id)"
      @del-todo="$emit('del-todo', todo.id)"/>
  </div>
</template>

<script>
// @ is an alias to /src
import todo from '@/components/todo-item.vue'

export default {
  name: 'todos',
  components: {
    todo,
  },
  props:['todos'],
}
</script>
<style scoped lang="scss">
$primary : rgb(111,2,225);
.todo-list{
    width: 100%;  
    margin-top: 2em;
}
</style>
