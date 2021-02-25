<template>
  <div id="app">
    <!-- 路由就是根据网址不同返回不同的内容 -->
    <!-- 显示的是当前路由地址所对应的内容 -->
    <!-- keep-alive: 路由中的内容加载时放在内存中，避免每次加载 -->
    <keep-alive>
      <router-view />
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
