<template>
      <div :class="{divCompleted:todo.completed}">
          <p :class="{isCompleted:todo.completed}">{{todo.title}}</p>
          <button type="button" @click="checkTodo" class="check">&check;</button>
          <button type="button" @click="$emit('del-todo' , todo.id)" class="trash">&times;</button>
      </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'todo',
  components: {
    //HelloWorld
  },
  props:['todo'],
  methods:{
      checkTodo(){
          this.todo.completed = !this.todo.completed;
      }
  }
}
</script>
<style scoped lang="scss">

div{
    background-color: rgb(241, 241, 241);
    border-radius:0 0 15px 0 ;
    display: flex;
    margin-top: 0.5em;
    transition: 0.5s;

    p{
        flex: 1;
        font-size: 1.1em;
        align-self: center;
        padding: 5px 15px;

    }
    button{
        font-size: 1.5em;
        border: none;
        padding: 5px 15px;
        color: white;
        cursor: pointer;
        outline: none;
    }
    .check{
        background-color:rgb(0, 206, 34);
    }
    .trash{
        background-color:rgb(255, 111, 71);
        border-radius:0 0 15px 0 ;
    }
    .isCompleted{
        text-decoration: line-through;
    }
    .divCompleted{
        opacity: 0.3;
    }
}

</style>
