<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul>
      <li>
        <a href="https://forum.vuejs.org" target="_blank">Forums</a>
      </li>
      <li>
        <a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a>
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank">Twitter</a>
      </li>
      <br>
      <li>
        <a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a>
      </li>
    </ul>
    <h2>VUE + Typescript</h2>
    <div>
      <h2>{{level}}-{{levels}}</h2>
      <button @click='add'>点我+1</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component, Prop } from 'vue-property-decorator';

@Component({
  watch: {
    level(v1:number, v2:number) {
      console.log(v1, v2)
    }
  }
})
export default class Hello extends Vue {
  @Prop() public name: string

  msg = 'welcom to my vue.js app'

  level = 333

  add() {
    this.level += 1
  }

  get levels(): number {
    return this.level
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
