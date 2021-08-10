<template>
  <div class="container">
    <Header title="Header title" />
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
export default {
  name: "App",
  components:{
    Header,
    Tasks
  },
  data(){
    return{
      tasks:[]
    }
  },
  methods:{
    deleteTask(id){
      if(confirm('Вы согласены удалить этот таск?')){
       this.tasks = this.tasks.filter((task)=> task.id != id )
      }
    },
    toggleReminder(id){
      this.tasks = this.tasks.map((task)=> task.id == id ? {...task , reminder : !task.reminder} : task )
    }
  },
  created(){
    this.tasks = [
     {
      id:1,
      text:'CF Real Madrid has created',
      day:'2nd of march 1899',
      reminder: true
     },
     {
      id:2,
      text:'FC Bayern has created',
      day:'22nd of march 1902',
      reminder: true
     },
     {
      id:3,
      text:'Manchester United has created',
      day:'6nd of march 1893',
      reminder: true
     },
     {
      id:4,
      text:'PSG has created',
      day:'25nd of june 1933',
      reminder: true
     }
    ]
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,600;0,700;1,400;1,500&display=swap');
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
