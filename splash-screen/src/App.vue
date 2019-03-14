<template>
  <div id="app">
    <SplashScreen @hide="onLoaded" v-if="!isLaunched" />
    <div id="content" v-else>
      <div class="container">
        <div style="margin-bottom: 60px; text-align: center">
          <img
            src="https://elevenback.jp/_nuxt/img/5e1feb8.svg"
            width="80"
            alt
          />
        </div>
        <el-row>
          <el-col
            :span="7"
            v-for="(o, index) in 12"
            :key="o"
            :offset="index % 3 ? 1 : 0"
            :style="{ marginBottom: '42px' }"
          >
            <el-card :body-style="{ padding: '0px' }">
              <div style="height: 128px;padding: 32px 0; text-align: center">
                <img src="./assets/logo.png" width="64" class="image" />
              </div>
              <div style="padding: 16px 16px 32px;">
                <span>Item {{ o }}</span>
              </div>
            </el-card>
          </el-col>
        </el-row>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SplashScreen from './components/SplashScreen.vue'

export default Vue.extend({
  name: 'app',
  components: {
    SplashScreen
  },
  data() {
    return {
      isLaunched: false
    }
  },
  methods: {
    onLoaded() {
      this.isLaunched = true
    }
  }
})
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#content {
  margin: 60px 0 0;
  animation: slideIn 0.3s ease-out forwards;
}

.container {
  width: 1024px;
  margin: 0 auto;
}

@keyframes slideIn {
  0% {
    opacity: 0;
    transform: translateY(10px);
  }
  100% {
    opacity: 1;
    transform: translateY(0px);
  }
}
</style>
