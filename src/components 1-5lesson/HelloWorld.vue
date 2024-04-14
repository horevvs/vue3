<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="">Counter</div>
    <div>{{ count }} </div>
    <div>{{ name }} </div>
    <button @click="inrease"> + </button>
    <button @click="decrease"> - </button>

    <!-- <input type="text" :placeholder="result" :value="inputvalue" @input="changeinput">
    <p>{{ inputvalue }}</p> -->
   <!-- директива  сразу записывает все в переменнут  inputvalue: '' -->
    <input type="text" :placeholder="result" v-model="inputvalue">
    //
    <p>{{ inputvalue }}</p>
    <p>{{ inputvalue }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0,
      name: 'Vova',
      result: 'епта текст',
      inputvalue: ''
    }
  },
  methods: {
    inrease() {
      this.count++
    },
    decrease() {
      this.count--
    },
    changeinput() {
      this.inputvalue= event.target.value
    }

  }

}
</script>
