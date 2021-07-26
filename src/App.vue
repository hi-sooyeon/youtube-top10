<template>
  <div class="d-flex flex-column">
    <Header />
    <div class="container-fluid">
      <div class="row d-flex flex-row justify-content-between g-5 w-100 vh-100">
        <Sidebar class="col-sm-2 py-4" ref="Sidebar"/>
        <router-view class="col-sm-10 py-4" />
      </div>
    </div>
    <Footer />
  </div>
</template>
<script>
import Header from "@/layouts/Header";
import Footer from "@/layouts/Footer";
import Sidebar from "@/layouts/Sidebar";

export default {
  components: {
    Header, Footer, Sidebar
  },
  data() {
    return {
      tempRegion: 'JP',
      tempLang: 'ja'
    }
  },
  computed: {
    regionTest() {
      //this.$refs.Sidebar.
      let defRegion = this.$store.getters.getRegion === '' || this.$store.getters.getRegion === undefined;
      return defRegion ? this.$store.dispatch('defaultRegion') : this.$store.getters.getRegion;
    },
    langTest() {
      let defLang = this.$store.getters.getLang === '' || this.$store.getters.getLang === undefined;
      return defLang ? this.$store.dispatch('defaultLang') : this.$store.getters.getLang;
    }
  },
  provide() {
    return {
      regionTest: this.regionTest,
      langTest: this.langTest
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
