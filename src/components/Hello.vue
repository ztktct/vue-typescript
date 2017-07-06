<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Hello, VUE + Typescript</h2>
    <div>
      <h2>{{level}}-{{levels}}</h2>
      <button @click='add'>点我+1</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component, Prop, Watch } from 'vue-property-decorator';

@Component
export default class Hello extends Vue {
  // props
  @Prop() public name: string

  // initdata
  msg = 'Welcom to your vue.js app!'

  level = 2333

  // methods
  add () {
    this.level += 1
  }

  // computed
  get levels(): number{
    return this.level + 1
  }

  // watch
  @Watch('level')
  onLevelChange(val:number, oldVal:number){
    console.log('oh yeah! Level up!')
  }

  // lifecycle
  created(){
    console.log('components created!')
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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
