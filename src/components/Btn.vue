<template>
    <button @click="handleClick" class="button">{{ label }}</button>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'CalcButton',
    props: {
      label: {
        type: [String, Number],
        required: true,
      },
      modelValue: {
        type: String,
        default: '',
      },
    },
    emits: ['update:modelValue', 'calculate', 'clear', 'delete', 'toggleParenthesis'],
    setup(props, { emit }) {
      const handleClick = () => {
        if (props.label === '=') {
            emit('calculate');
        } 
        else if(props.label === 'AC'){
            emit('clear')
        }else if(props.label === 'D'){
            emit('delete')
        }else if(props.label === '( )'){
            emit('toggleParenthesis')
        }else {
            emit('update:modelValue', props.modelValue + props.label);
        }
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
  