<template>
<div id="app" class="max-w-xl mx-auto my-0 bg-gradient-to-r from-slate-500 to-slate-100 p-3 mt-8 shadow-2xl">
<div class="text-5xl py-3">To Do List</div>
    <div class="flex mb-4" v-if="isEditing">
      <input type="text" placeholder="Adding" v-model="todo" class="pl-2 bg-gradient-to-r from-slate-500 to-slate-100 border-2 border-black rounded">
      <button type="submit" class="p-3 border-2 bg-gradient-to-l from-slate-300 border-l-0 border-black hover:bg-slate-400" @click="addTodo">Add</button>
    </div>
    <!-- <div v-else>
      <input type="text" v-model="todo" class="p-3 bg-gradient-to-r from-slate-500 to-slate-100 border-2 border-black rounded">
      <button type="submit" @click="updateTodo" class="p-3 border-2 bg-gradient-to-l from-slate-300 border-l-0 border-black hover:bg-slate-400">Update</button>
      </div>  -->
    <ul class="flex flex-col">
      <li class="flex justify-between text-lg" v-for="todo in todos" :key="todo.id">
          {{ todo }}
    <a>
      <button class="border-2 px-4 py-2 hover:bg-black hover:text-white" @click="editTodo(index,todo)">Edit</button>
      <button @click="deleTodo(index,todo)" class="p-2 hover:bg-black hover:text-red-800">Delete</button>
    </a>          
        </li>
    </ul>  
</div>
</template>
<style>  
</style>
<script > 
export default {
  name:'app',
  data(){
    return {
      isEditing:true,
      todo:'',
      todos:['ngu','hoc','choi','an','hat'],
      Index : null,
    }
  },
  methods: {
    addTodo(){
      this.todos.push(this.todo)
      this.todo = ''   
      return
    },
    editTodo(index,todo){
      this.todo = todo
      this.isEditing = true
      this.Index = index
      this.todos.splice(this.todo,1,this.todo)
    },
    // updateTodo(){
    //   this.todos.splice(this.todo,1,this.todo)
    //   this.isEditing= true
    // },
    deleTodo(index){
      this.todos.splice(index,1)
      console.log(this.todos)
    }   
  }
}
  </script>


































































































































































