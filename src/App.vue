<script setup>
import { useRoute, useRouter } from 'vue-router'
import { useUserStore, useCountStore } from '@/stores'
const router = useRouter()
const route = useRoute()
const userStore = useUserStore()
const countStore = useCountStore()

const goList = () => {
  console.log(router, route)
  router.push('/list')
}
</script>

<template>
  <div>
    <hr />
    <router-view></router-view>
    <hr />
    <hr />
    <hr />
    Hello Vue!
    <el-button @click="$router.push('/home')">跳首页</el-button>
    <el-button @click="goList">跳列表页</el-button>
    <el-button type="primary">Primary</el-button>

    <p>{{ userStore.token }}</p>
    <el-button @click="userStore.setToken('Bearer dfadfdasfsad')">登录</el-button>
    <el-button @click="userStore.removeToken()">退出</el-button>
    <hr />
    {{ countStore.count }}
    <el-button @click="countStore.add(2)">加法</el-button>
  </div>
</template>

<style scoped>
h1 {
  color: red;
}
</style>
