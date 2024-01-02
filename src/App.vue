<template>
  <div class="container">
    <div class="calc-body">
      <div class="calc-screen">
        <div class="calc-operation">{{ operationLabel }}</div>
        <div class="calc-typed">{{ typedLabel }}</div>
      </div>
      <div class="calc-button-row">
        <Btn class="c" label="AC" @clear="clear"/>
        <Btn class="l" label="( )"/>
        <Btn class="l" label="%" v-model="typedLabel"/>
        <Btn class="l" label="/" v-model="typedLabel"/>
      </div>
      <div class="calc-button-row">
        <Btn label="7" v-model="typedLabel"/>
        <Btn label="8" v-model="typedLabel"/>
        <Btn label="9" v-model="typedLabel"/>
        <Btn class="l" label="*" v-model="typedLabel"/>
      </div>
      <div class="calc-button-row">
        <Btn label="4" v-model="typedLabel"/>
        <Btn label="5" v-model="typedLabel"/>
        <Btn label="6" v-model="typedLabel"/>
        <Btn class="l" label="-" v-model="typedLabel"/>
      </div>
      <div class="calc-button-row">
        <Btn label="1" v-model="typedLabel"/>
        <Btn label="2" v-model="typedLabel"/>
        <Btn label="3" v-model="typedLabel"/>
        <Btn class="l" label="+" v-model="typedLabel"/>
      </div>
      <div class="calc-button-row">
        <Btn label="." v-model="typedLabel"/>
        <Btn label="0" v-model="typedLabel"/>
        <Btn label="D" @delete="del"/>
        <Btn class="l" label="=" @calculate="calculate"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Btn from './components/Btn.vue';

export default defineComponent({
  components: {
    Btn,
  },
  setup() {
    const operationLabel = ref('');
    const typedLabel = ref('');
    let operation = '';

    const calculate = () => {
      try {
        operation = typedLabel.value
        const result = eval(typedLabel.value);
        typedLabel.value = result.toString();
        operationLabel.value = `${operation}=${result}`;
      } catch (error) {
        console.error('Error evaluating expression:', error);
      }
    };

    const clear = () => {
      typedLabel.value = ''
    };

    const del = () =>{
      typedLabel.value = typedLabel.value.slice(0, -1);
    };
    return {
      operationLabel,
      typedLabel,
      calculate,
      clear,
      del,
    };
  },
});
</script>
