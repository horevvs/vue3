<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div :class="['dodo', { bobo: ara.length >= 4 }]">Counter</div>
    <div :class="ara.length > 5 ? 'one' : 'two'">{{ count }} </div>
    <div>{{ name }} </div>
    <button @click="inrease"> + </button>
    <button @click="decrease"> - </button>

    <!-- <input type="text" :placeholder="result" :value="inputvalue" @input="changeinput">
    <p>{{ inputvalue }}</p> -->
    <!-- директива  сразу записывает все в переменнут  inputvalue: '' -->
    <input type="text" :placeholder="result" v-model="inputvalue" v-on:keypress.enter="addNewnote">

    <p :class="{ one: true, three: ara.length >= 2 }">{{ inputvalue }}</p>
    <p>{{ inputvalue }}</p>
    <!-- // тут рендерим чере v-for как в реакте только в v-for пришем итем и его id, прописываем потмо по нему фильруем -->
    <button @:click="removeNote" class="btn">return</button>
    <div v-if="ara.length == 0">
      нету заметок
      <div>{{ calculateNotes }}</div>
    </div>

    <div v-else>
      <div v-for="(  item, index  ) in   ara  " v-bind:key="index">
        <div :class="{ one: true, three: ara.length > 2 }" @:click="getid(index)">{{ item }}</div>
        <button @:click="geleteNote(index)" class="btn">удалить</button>
      </div>
    </div>
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
      inputvalue: '',
      ara2: ['11', '22', '33', '44', '55'],
      ara: []
    }
  },
  methods: {

    addNewnote() {
      // читаем значение с инпута когда срабатывает функция
      this.ara.push(event.target.value)
      this.inputvalue = '2пусто'
    },


    inrease() {
      this.count++
    },
    decrease() {
      this.count--
    },
    changeinput() {
      this.inputvalue = event.target.value
    },

    getid(index) {
      console.log(index)
    },

    geleteNote(index) {
      this.ara.splice(index, 1)
    },

    removeNote() {
      console.log(this.ara)

      this.ara = ['11', '22', '33', '44', '55']
    },
  },

  // только по условию, например когда идет изменение dom
  computed: {
    calculateNotes() {
      return console.log('сработал computed', this.ara)
    }
  },

  // срабатывает в случае выполнения события, реагирует на переменну в дата
  watch: {
    inputvalue(value) {
      console.log('watch', value)
      if (value.length >= 5) {
        // this.name = 'vitya'
        this.name = 'витя'
        console.log('сработало')
      }
    }
  },



}
</script>

<style>
.one {
  background-color: brown;
}


.two {
  background-color: rgb(87, 165, 74);
}


.three {
  background-color: rgb(42, 61, 165);
}


.bobo {
  font-size: 45px;

}

.dodo {
  background-color: rgb(163, 165, 42);
}
</style>
