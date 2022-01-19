<!--  -->
<template>
  <div>
    {{ msg }}<br />
    长度:{{ mainStore.nameLength }}
  </div>
  <button @click="updateName">修改store中的name</button>
  <div>{{ mainStore.name }}</div>
</template>

<script setup lang="ts">
import { useMainStore } from '@/store/main'
import { ref } from 'vue'
console.log(import.meta.env.VITE_APP_WEB_URL)
const msg = ref('this is login page')
const mainStore = useMainStore()
const updateName = () => {
  mainStore.$patch({
    name: '名称被修改了,nameLength也随之改变了'
  })
}
</script>
<style lang="scss" scoped></style>
