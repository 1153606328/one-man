<template>
  <div class="index">
    <mt-header  title="OneMan"></mt-header>
    <p class="title">My2019</p>
    <div class=""></div>
    <v-navigation></v-navigation>
  </div>
</template>

<script>
import navigation from "../components/Navigation.vue"
export default {
  name: 'HelloWorld',
  components: {//注册组件
    'v-navigation': navigation
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.index{
    .title{
      padding: 10px;
      font-weight: 600;
    }
}
</style>
