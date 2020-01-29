<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="emitEvent">
      Click here
    </button>
    <br>    <br>
    <div>
      <button @click="eventPlus1">
        +
      </button>
      <button @click="eventMoins1">
        -
      </button>
      <p>valeur {{ but1 }}</p>

      <button @click="eventPlus2">
        +
      </button>
      <button @click="eventMoins2">
        -
      </button>
      <p>valeur {{ but2 }}</p>
      <button @click="eventPlus3">
        +
      </button>
      <button @click="eventMoins3">
        -
      </button>
      <p>valeur {{ but3 }}</p>
      <p>La moyenne de ces trois boutons est de : {{ moy }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    but1: {
      type: Number,
      required: true,
    },
    but2: {
      type: Number,
      required: true,
    },
    but3: {
      type: Number,
      required: true,
    },
    moy: {
      type: Number,
      required: true,
    },
    msg: {
      type: String,
      default: 'VueJS',
    },
  },
  methods: {
    emitEvent() {
      this.$emit('slt');
    },
    eventPlus1() {
      this.$emit('plus1');
    },
    eventPlus2() {
      this.$emit('plus2');
    },
    eventPlus3() {
      this.$emit('plus3');
    },
    eventMoins1() {
      this.$emit('moins1');
    },
    eventMoins2() {
      this.$emit('moins2');
    },
    eventMoins3() {
      this.$emit('moins3');
    },
    averageSum() {
      this.$emit('avg');
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
