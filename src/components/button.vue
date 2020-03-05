<template>
  <button
    :type="type"
    @click="clickHandle"
    :class="{
      [`btn-${size}`]: size,
      [`btn-${loading}`]: loading
    }"
    :disabled="disabled || loading">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'btn',
  props:{
    disabled: Boolean,
    loading: Boolean,
    type: {
      type: String,
      default: 'button',
      validator(value){
        return (['button', 'submit', 'reset']).indexOf(value) > -1;
      }
    },
    size: {
      type: String,
      validator(value){
        return (['lg', 'sm']).indexOf(value) > -1;
      }
    }
  },
  beforeCreate(){
    console.log('child beforeCreate');
  },
  created(){
    console.log('child created');
  },
  beforeMount(){
    console.log('child beforeMount');
  },
  mounted(){
    console.log('child mounted');
  },
  beforeUpdate(){
    console.log('child beforeUpdate');
  },
  updated(){
    console.log('child updated');
  },
  beforeDestroy(){
    console.log('child beforeDestroy');
  },
  destroyed(){
    console.log('child destroyed');
  },
  methods: {
    clickHandle(event) {
      this.$emit('click', event);
    },
  },
}
</script>

<style>

</style>