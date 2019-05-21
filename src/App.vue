<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">{{$t('documentation.documentation')}}</router-link> |
      <router-link to="/about">{{$t('documentation.github')}}</router-link>
    </div>
    <input v-for="item in dataEn" :key="item.value" type="button" @click="changeEn(item.lang)" :value="item.value">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      dataEn: [
        {
          value: '日语',
          lang: 'ja'
        },
        {
          value: '中文',
          lang: 'zh'
        }
      ]
    }
  },
  methods: {
    changeEn (lang) {
      // window.localStorage.setItem('language', lang)
      // location.reload()
      this.$i18n.locale = lang
      // this.$i18n.mergeLocaleMessage(lang, local[lang])
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
