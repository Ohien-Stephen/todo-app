<template>
  <div class="home">
    <form @submit.prevent="addTodo">
      <input v-model="title" type="text" placeholder="enter todo" required>
      <button>&plus;</button>
    </form>
    <div class="todo-container">
      <todos @check-todo="checkTodo" @del-todo="DeleteTodo" :todos="todos"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import todos from '@/components/todos.vue'

export default {
  name: 'Home',
  components: {
   todos,
  },
  data(){
    return{
      title:'',
      todos:[
        {id:1, title:"Cook Rice", completed:true},
        {id:2, title:"Create a todo app", completed:false},
        {id:3, title:"Write a Novel", completed:true},
        {id:4, title:"Make a Vuex Tutorals", completed:false},
        {id:4, title:"Go to the Mall", completed:false},
      ]
    }
  },
  methods:{
    addTodo(){
      const newTodo = {
        id:'6',
        title:this.title,
        completed:false
      };
      this.todos = [...this.todos, newTodo];
      this.title='';
    },
    checkTodo(id){
      alert("Check" + id)
    },
    DeleteTodo(id){
      this.todos = this.todos.filter(todo=> todo.id !== id);
    }
  }
}
</script>
<style scoped lang="scss">
$primary : rgb(111,2,225);
  form{
    width: 100%;
    display:flex;

      input{
        flex:1;
        padding:10px;
        outline: none;
        border: none;
        font-size: 1.3em;
        border-bottom:1px solid gray ;
      }
      button{      
        background-color: $primary;
        color: white;
        font-weight: bold;
        border: none;
        outline: none;
        font-size: 1.5em;
        padding:5px 15px;      
        cursor: pointer;

        &:hover{
          background-color: darken($primary, 5);
        }
    }
  }
</style>
