<template>
  <div id="app">
    <img
      alt="Vue logo"
      src="./assets/logo.png"
    >
    <h3 v-if="avg === 3">
      OUAIP C'EST 3 GROOOOS
    </h3>
    <h3 v-else>
      PRESQUE !!!!!
    </h3>
    <counter
      :value="btn1"
      @input="btn1=$event"
    />
    <counter
      :value="btn2"
      @input="btn2=$event"
    />
    <counter v-model="btn3" />
    <p>Moyenne : {{ avg }}</p>
  </div>
</template>

<script>
import counter from './components/Counter.vue';

const createCounters = () => ({
  btn1: 0,
  btn2: 0,
  btn3: 0,
});

export default {
  name: 'App',
  components: {
    counter,
  },
  data() {
    return {
      btn1: 0,
      btn2: 0,
      btn3: 0,
    };
  },
  computed: {
    avg() {
      return (this.btn1 + this.btn2 + this.btn3) / 3;
    },
  },
  methods: {
    yeyItWorks() {
      alert('it works');
    },
    resetCounters() {
      this.counter = createCounters();
    },
  },
};
</script>

<style lang="scss">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  </style>
