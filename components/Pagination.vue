<template>
  <div>
    <el-pagination
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page.sync="currentPage1"
      :page-size="100"
      layout="prev, pager, next,total"
      :total="1000">
    </el-pagination>
  </div>
</template>

<script>
export default {
  name:'NuxtPagination',
  data(){
    return {
      currentPage1:1
    }
  },
  methods:{
    handleSizeChange(){

    },
    handleCurrentChange(){

    },
  }
}
</script>

<style>

</style>
