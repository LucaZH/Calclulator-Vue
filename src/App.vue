<template>
  <div class="container">
    <div class="calc-body">
      <div class="calc-screen">
        <div class="calc-operation">2536 + 419 + </div>
        <div class="calc-typed">2955</div>
      </div>
      <div class="calc-button-row">
        <Btn class="c" label="1" />
        <Btn class="l" label="≠" />
        <Btn class="l" label="%" />
        <Btn class="l" label="/" />
      </div>
      <div class="calc-button-row">
        <Btn label="7" />
        <Btn label="8" />
        <Btn label="9" />
        <Btn class="l" label="x" />
      </div>
      <div class="calc-button-row">
        <Btn label="4" />
        <Btn label="5" />
        <Btn label="6" />
        <Btn class="l" label="−" />
      </div>
      <div class="calc-button-row">
        <Btn label="1" />
        <Btn label="2" />
        <Btn label="3" />
        <Btn class="l" label="+" />
      </div>
      <div class="calc-button-row">
        <Btn label="." />
        <Btn label="0" />
        <Btn class="l" label="=" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Btn from './components/Btn.vue';

export default defineComponent({
  components: {
    Btn,
  },
});
</script>
<style scoped>
* {
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}

body {
  background: #EAEBEC;
}

.container {
  width: 400px;
  margin: auto;
}

.calc-body {
  width: 275px;
  margin: auto;
  min-height: 400px;
  border: solid 1px #3A4655;
  box-shadow: 0 8px 50px -7px black;
}

.calc-screen {
  background: #3A4655;
  width: 100%;
  height: 150px;
  padding: 20px;
}

.calc-operation {
  text-align: right;
  color: #727B86;
  font-size: 21px;
  padding-bottom: 10px;
  border-bottom: dotted 1px;
}

.calc-typed {
  margin-top: 20px;
  font-size: 45px;
  text-align: right;
  color: #fff;
}

.calc-button-row {
  width: 100%;
  background: #3C4857;
}
</style>
