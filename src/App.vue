<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"
    ref="hm" @add="onadd($event)"/>
    <HelloWorld>
      <template v-slot:default>aaaaa</template>
        <template v-slot:content>具名插槽</template>
    </HelloWorld>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  provide:{ai:'ai'},
  components: {
    HelloWorld
  },
  mounted(){
    this.$refs.hm.foo='bar';
    this.$children[0].foo='dong'
  },
  methods:{
    onadd(e){
      console.log("onadd");
      console.log(e)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
