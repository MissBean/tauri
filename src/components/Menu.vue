<template>
  <div class="menu">
    <ul class="menu-list">
      <li v-for="item in menuItems" :key="item.name">
        <router-link :to="item.path">{{ item.name }}</router-link></li>
    </ul>
  </div>
</template>
<script setup>
import { ref } from "vue";
const menuItems = ref([
  { name: "上传区", path: "/upload" },
  { name: "相册", path: "/piclist" },
  { name: "图床设置", path: "/setting" },
]);
</script>
<style scoped>
  .menu {
    width: 150px;
    height: 100vh;
    background: #d4d4d470;
    text-align: left;
  }
  .menu-list {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  .menu-list li {
    padding: 10px 15px;
  }
  .menu-list li a {
    display: block;
    text-decoration: none;
    color: #333;
  }
</style>


