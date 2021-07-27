<template>
  <div class="home">
    regionTest : {{regionTest}}
    <br>
    langTest : {{langTest}}
    <hr>
    <Youtube />
  </div>
</template>

<script>
// @ is an alias to /src
import Youtube from "@/views/Youtube";

export default {
  name: 'Home',
  components: {
    Youtube
  },
  inject: ['regionTest', 'langTest']
}
</script>
