<template>
  <div id="app">
    <button @click="load">Load Component right here.</button>
    <async-component
            v-if="loadComponent"
            :component="Example"
            example="Example Props"
            @listen="listen"/>
  </div>
</template>

<script>
import AsyncComponent from "./components/AsyncComponent";

const Example = () => import("./components/Example")

export default {
  name: 'App',
  components: {
    AsyncComponent
  },
  data() {
    return {
      Example,
      loadComponent: false
    }
  },
  methods: {
    load() {
      this.loadComponent = true
    },
    listen() {
      alert("hii guys")
    }
  }
}
</script>
