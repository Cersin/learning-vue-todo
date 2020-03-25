<template>
 <div id="container">
  <h1>Todo app</h1>
<todo-app></todo-app>
 </div>

</template>

<script>
 import Todo from './components/TodoApp.vue'
 export default {
  components:{
   TodoApp: Todo
  }
 }
</script>
<style>
#container{
 text-align: center;
}
</style>
