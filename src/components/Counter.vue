<template>
  <div>
    <button @click="increment">
      PLUCE
    </button>
    <button @click="decrement">
      MOUINS
    </button>
    <p>{{ value }}</p>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    value: {
      type: Number,
      required: true,
    },
  },
  methods: {
    increment() {
      this.$emit('input', this.value + 1);
    },
    decrement() {
      this.$emit('input', this.value - 1);
    },
  },
};
</script>

<style scoped>

</style>
