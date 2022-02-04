<template>
  <div id="app">
    <h1>Math Quiz App</h1>
    <operatorQuiz
      @onBack="clearOperator"
      v-if="operator"
      :operator="operator"
    />
    <operatorSelector v-if="!operator" @changeOperator="changeOperator" />
  </div>
</template>

<script>
import operatorSelector from "./components/OperatorSelector.vue";
import operatorQuiz from "./components/OperatorQuiz.vue";
export default {
  name: "App",
  data() {
    return {
      operator: null,
    };
  },
  methods: {
    changeOperator(operator) {
      this.operator = operator;
    },
    clearOperator() {
      this.operator = null;
    },
  },
  components: {
    operatorSelector,
    operatorQuiz,
  },
};
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
button {
  padding: 10px;
  width: 160px;
  height: 80px;
  vertical-align: top;
  margin-right: 10px;
  margin-top: 10px;
  background: #10aeb2;
  color: #fff;
  font-size: 24px;
  cursor: pointer;
}
</style>
