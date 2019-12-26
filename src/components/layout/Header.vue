<!--  -->
<template>
  <div class="header">
    <h1>Todo List</h1>
    <div id="nav">
      <!-- 使用 router-link 组件来导航. -->
      <!-- 通过传入 `to` 属性指定链接. -->
      <!-- <router-link> 默认会被渲染成一个 `<a>` 标签 -->
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>
    </div>
    <!-- 路由出口 -->
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {};
  },

  components: {},

  computed: {},

  methods: {}
};
</script>
<style scoped>
.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
}
.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
}
</style>
