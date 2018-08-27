<template>
  <div id="app">
    <!-- 显示当前路由地址所对应的的内容： exclude中是不需要缓存的组件，mouted每次都会重新执行 -->
    <keep-alive exclude="Detail">
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
