<template>
  <h2>{{ customTitle }} {{ start }}</h2>
  <p>{{ counter }}<sup>2</sup> = {{ squareCounter }}</p>
  <div>
    <button @click="decrement">-1</button>
    <button @click="increment">+1</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  props: {
    title: {
      type: String,
      required: false,
    },
    start: {
      type: Number,
      default: 100,
    },
  },
  data() {
    return {
      counter: this.start,
    };
  },
  methods: {
    increment() {
      this.counter++;
    },
    decrement() {
      this.counter--;
    },
  },
  computed: {
    squareCounter() {
      return this.counter * this.counter;
    },
    customTitle() {
      return this.title || "Counter";
    },
  },
};
</script>

<style>
button {
  background-color: #64bb87;
  border-radius: 5px;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}

button:hover {
  background-color: #5aa67b;
  transition: 0.3s ease-in-out;
}
</style>