<template>
  <div class="home">
    regionTest : {{regionTest}}
    <br>
    langTest : {{langTest}}
    <hr>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  inject: ['regionTest', 'langTest']
}
</script>
