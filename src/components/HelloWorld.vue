<template>
  <div class="hello">
    <h1>{{ $store.state.showFooter }}</h1>
    <h1>{{ $store.state.changableNum }}</h1>
    <h2 @click="show()">显示</h2>
    <h2 @click="hide()">隐藏</h2>
    <h2>{{isShow}}</h2>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: this.$store.state.showFooter,
      first: 2
    }
  },
  computed: {
    isShow () {
      return this.$store.getters.isShow
    }
  },
  methods: {
    show () {
      // this.$store.commit('show')
      // this.$store.commit('newNum', 6)
      this.$store.dispatch('hideFooter')
      this.$store.dispatch('getNewNum', 6)
    },
    hide () {
      // this.$store.commit('hide')
      // this.$store.commit('newNum', 6)
      this.$store.dispatch('showFooter')
      this.$store.dispatch('getNewNum', 6)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
