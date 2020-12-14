<template>
  <div class="container">
    <button v-on:click="decrement()" class="decrement">Decrement</button>
    <div class="count">{{ count }}</div>
    <button v-on:click="increment()" class="increment">Increment</button>
  </div>
</template>

<script>
export default {
  name: "counter",
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    increment() {
      if (this.count < 9) {
        this.count++;
      }
    },
    decrement() {
      if (this.count > 1) {
        this.count--;
      }
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: space-around;
  height: 50px;
  width: 330px;
  padding: 10px;
  border: 2px solid gray;
  border-radius: 8px;
}
button {
  padding: 5px 10px;
  border-radius: 5px;
  outline: none;
  cursor: pointer;
  font-family: "Roboto";
  font-size: 16px;
  background: rgb(3, 199, 140);
}
.count {
  padding: 5px;
  font-size: 20;
  padding: 10px;
  border-radius: 5px;
  background: #000;
  color: aliceblue;
  font-weight: bold;
}
</style>
