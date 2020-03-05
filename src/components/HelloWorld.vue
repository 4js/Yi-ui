<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <Button :size="size" @click="handleClick">按钮</Button>
  </div>
</template>

<script>
import Button from './button'
export default {
  name: 'HelloWorld',
  data(){
    return {
      size: 'lg'
    }
  },
  props: {
    msg: String
  },
  components: {
    Button
  },
  beforeCreate(){
    console.log('parent beforeCreate');
  },
  created(){
    console.log('parent created');
  },
  beforeMount(){
    console.log('parent beforeMount');
  },
  mounted(){
    console.log('parent mounted');
  },
  beforeUpdate(){
    console.log('parent beforeUpdate');
  },
  updated(){
    console.log('parent updated');
  },
  beforeDestroy(){
    console.log('parent beforeDestroy');
  },
  destroyed(){
    console.log('parent destroyed');
  },
  methods: {
    handleClick() {
      this.size = 'sm';
      console.log(this.size);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
