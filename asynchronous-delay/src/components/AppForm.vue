<template>
  <div v-loading="isLoading">
    <div v-if="!isSubmited" class="content">
      <p>
        <span>User ID</span><br />
        <el-input style="margin-top: 8px;" placeholder="@username" />
      </p>
      <p>
        <span>Password</span><br />
        <el-input style="margin-top: 8px;" placeholder="password" type="text" />
      </p>
      <el-button @click="handleClickSubmit">
        Save
      </el-button>
    </div>
    <div
      style="color: #1FA0FF;"
      :class="{
        slideIn: isAnimate
      }"
      class="text-center flex flex-col justify-center items-center content"
      v-else
    >
      <h1 style="margin-bottom: 8px;"><i class="el-icon-success"></i><br /></h1>
      <h2 style="margin-top: 0;">fetched</h2>
      <el-button
        @click="isSubmited = false"
        plain
        style="position: absolute; right: 16px; bottom: 16px;"
        >Back</el-button
      >
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { delay } from '../utils/delay'

export default Vue.extend({
  props: {
    isAnimate: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      isSubmited: false,
      isLoading: false
    }
  },
  methods: {
    async handleClickSubmit() {
      ;(document.activeElement! as HTMLElement).blur()
      this.isLoading = true
      await Promise.all([this.fetchAPI(160), delay(this.isAnimate ? 800 : 0)])
      this.isLoading = false
      this.isSubmited = true
    },
    async fetchAPI(ms: number) {
      await delay(ms)
      return
    }
  }
})
</script>

<style scoped>
.text-center {
  text-align: center;
}

.slideIn {
  animation: slideInLeft 0.3s ease-out forwards;
}

@keyframes slideInLeft {
  0% {
    transform: translateX(20px);
    opacity: 0;
  }
  100% {
    transform: translateX(00px);
    opacity: 1;
  }
}
</style>
