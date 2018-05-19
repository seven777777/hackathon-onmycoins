<template>
  <div class="home_wrap">
    <div class="navBar"></div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">
.home_wrap{
  width: 100%;
  .navBar{
    width: 100%;
    height: 60px;
    background: white;
    box-shadow: rgba(0,0,0,0.2) 0px 1px 12px;
  }
}
</style>
