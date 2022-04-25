<template>
  <div>
    <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b">
      <el-menu-item index="1">首页</el-menu-item>
      <el-submenu index="2">
        <template slot="title">文章</template>
        <el-submenu index="2-1">
          <template slot="title">前端</template>
          <el-menu-item index="2-1-1">Vue</el-menu-item>
          <el-menu-item index="2-1-2">React</el-menu-item>
          <el-menu-item index="2-1-3">JQuary</el-menu-item>
        </el-submenu>
        <el-submenu index="2-2">
          <template slot="title">后端</template>
          <el-menu-item index="2-2-1">Java</el-menu-item>
          <el-menu-item index="2-2-2">Node</el-menu-item>
          <el-menu-item index="2-2-3">Python</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="4">视频</el-menu-item>
      <el-menu-item index="3">消息中心</el-menu-item>
<!--      <el-menu-item index="4"><a href="https://www.ele.me" target="_blank">订单管理</a></el-menu-item>-->
    </el-menu>
  </div>
</template>

<script>
export default {
  data(){
    return {
      activeIndex:"1"
    }
  },
  methods:{
    handleSelect(){

    }
  },
  asyncData(){

    return {

    }
  },
  name:'NuxtTopNav'
}
</script>

<style lang="scss" scoped>
.el-menu{
  width: 50%;
  text-align: center;
  left: 25%;
  display: flex;
  justify-content: space-between;
}
</style>
