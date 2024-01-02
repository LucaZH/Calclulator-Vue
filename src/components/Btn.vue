<template>
    <button @click="handleClick" class="button">{{ label }}</button>
  </template>
  
  <script lang="ts">
  import { defineComponent, PropType } from 'vue';
  
  export default defineComponent({
    name: 'CalcButton',
    props: {
      label: {
        type: String, 
        required: true,
      },
    },
    setup(props) {
      const handleClick = () => {
        console.log(`Button "${props.label}" clicked!`);
      };
  
      return {
        handleClick,
      };
    },
  });
  </script>
<style scoped>
.button {
  width: 25%;
  background: #425062;
  color: #fff;
  padding: 20px;
  display: inline-block;
  font-size: 25px;
  text-align: center;
  vertical-align: middle;
  margin-right: -4px;
  border-right: solid 2px #3C4857;
  border-bottom: solid 2px #3C4857;
  transition: all 0.2s ease-in-out;
}
.button:hover {
  background: #E0B612;
  transform: rotate(1deg);
}
</style>