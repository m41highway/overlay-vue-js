<template>
  <div class="hello">
    <div>
      <h1>{{ msg }}</h1>
      <h2>Essential Links</h2>
      <ul>
        <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
        <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
        <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
        <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
        <br>
        <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
      </ul>
      <h2>Ecosystem</h2>
      <ul>
        <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
        <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
        <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
        <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
      </ul>
    </div>
    <div id="overlay" v-bind:class="{ 'close-overlay': hasClosedByUser }">
      <div id="text">Overlay Text ...</div>
      <input type="button" value="X" class="close-ad-button"  v-on:click="closeOverlay"></input>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',

  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      hasClosedByUser: false,
    }
  },

  methods: {
    closeOverlay() {
      console.log('closing');

      this.hasClosedByUser = true;
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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

#overlay {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0,0,0,0.5);
  z-index: 2;
  cursor: pointer;
}

#text{
  position: absolute;
  top: 50%;
  left: 50%;
  font-size: 50px;
  color: white;
  transform: translate(-50%,-50%);
  -ms-transform: translate(-50%,-50%);
}

.close-ad-button {
  position: absolute;
  top: 50%;
  left: 50%;
  font-size: 50px;
  color: blue;
  transform: translate(150px,125px);
  -ms-transform: translate(150px,125px);
}

.close-overlay {
  display: none;
}
</style>
