<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" @sendMsg="handler"/>
    <h3>我的年龄：{{ myAge }}</h3>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { ref } from 'vue'
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  setup () {
    var myAge = ref(0)
    const count = ref(1)
    const handler = value => {
      console.log('子组件emit传值到父页面：', value)
      myAge.value = value + (count.value++)
    }
    debugger
    return { myAge, handler }
  }
}
</script>
