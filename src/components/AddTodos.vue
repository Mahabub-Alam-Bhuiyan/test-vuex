<template>
<div>
  <h3>Add Todos</h3>

  <div class="add">
    <form @submit.prevent="onsubmit">
      <input type="text" v-model="title" placeholder="Add Todo..">
      <input type="submit" value="Submit">
      </form>
  </div>

</div>
</template>

<script>
import {mapActions} from 'vuex'
export default {
  name: "AddTodos",
  data(){
    return{
  title: ''
    }
  },
  methods:{
  ...mapActions(["addTodo"]),
    onsubmit(e){
    e.preventDefault();
    this.addTodo(this.title)
    }

  },

}
</script>

<style scoped>
form{
  display: flex;
}
input[type="text"]{
  flex: 10;
  padding: 10px;
  border: 1px solid #41b883;
  outline: 0;
}
input[type="submit"]{
  flex: 2;
  color: white;
  background-color: #41b883;
  border: #41b883 solid;
  cursor: pointer;
}
</style>
