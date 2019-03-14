<template>
  <div id="app">
    <div class="container">
      <AppForm :isAnimate="false" class="col" />
      <AppForm :isAnimate="true" class="col" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AppForm from './components/AppForm.vue'

export default Vue.extend({
  name: 'app',
  components: {
    AppForm
  }
})
</script>

<style>
html,
body,
#app {
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  background: #2b2b2b;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.flex {
  display: flex;
}

.flex-col {
  flex-direction: column;
}

.items-center {
  align-items: center;
}

.justify-center {
  justify-content: center;
}

* {
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  width: 1280px;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
}

.col {
  width: 600px;
  height: 400px;
  background: #fff;
  position: relative;
}

.content {
  width: 100%;
  height: 100%;
  padding: 16px;
}
</style>
