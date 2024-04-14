<template>
  <My_component />
  <New_Notes v-for="note in notes"
   v-bind:key="note"
    v-bind:oneNote="note.task" 
    v-bind:id="note.id"
    v-bind:result="note.result"
     />
</template>

<script>
import My_component from './components/My_component.vue'
import New_Notes from './components/New_Notes.vue'
export default {
  data() {
    return {
      notes: [{
        task: 'задача 1', id: 1,
        result: 'сделано1'
      },
      { task: 'задача 2', id: 2, c: 'сделано2' },
      { task: 'задача 3', id: 3, result: 'сделано3' },]
    }
  },
  // name: 'App',
  components: {
    My_component,
    New_Notes
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
