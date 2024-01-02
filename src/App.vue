<template>
  <div class="container">
    <div class="calc-body">
      <div class="calc-screen">
        <div class="calc-operation">2536 + 419 + </div>
        <div class="calc-typed">{{ typedLabel }}</div>
      </div>
      <div class="calc-button-row">
        <Btn class="c" label="1" v-model="typedLabel"/>
        <Btn class="l" label="≠" v-model="typedLabel"/>
        <Btn class="l" label="%" v-model="typedLabel"/>
        <Btn class="l" label="/" v-model="typedLabel"/>
      </div>
      <div class="calc-button-row">
        <Btn label="7" v-model="typedLabel"/>
        <Btn label="8" v-model="typedLabel"/>
        <Btn label="9" v-model="typedLabel"/>
        <Btn class="l" label="x" v-model="typedLabel"/>
      </div>
      <div class="calc-button-row">
        <Btn label="4" v-model="typedLabel"/>
        <Btn label="5" v-model="typedLabel"/>
        <Btn label="6" v-model="typedLabel"/>
        <Btn class="l" label="−" v-model="typedLabel"/>
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
        <Btn class="l" label="="/>
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
  setup(){
    const typedLabel = ref('');
    
    return { typedLabel, }
  }
});
</script>

