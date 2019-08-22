<template>
  <div class="hello" @click="$parent.$emit('mua')">
    <h1 @click="$emit('add','bar')">{{ msg }}</h1>
    <h2> {{foo}}--{{ai}}</h2>
    <!--匿名插槽-->
    <slot></slot>
    <!--具名插槽-->
    <slot name="content"></slot>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  inject:['ai'],
  props: {
    msg: String
  },
  data(){
    return{
      foo:'foo'
    }
  },
  created(){
    this.$parent.$on('mua',()=>{
      console.log('mua');
    })
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
