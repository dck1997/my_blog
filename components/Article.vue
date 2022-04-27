<template>
  <div class="article">
    <el-card shadow="hover">
      <div slot="header" class="clearfix">
        <span>文章列表</span>
      </div>
      <div v-for="article in articleList" :key="article.index" class="article_item">
        <div>
          <i class="el-icon-document"></i>
          <el-tooltip class="item" effect="light" :content="article.tips" placement="top">
            <el-link :href="article.href">{{ article.title }}</el-link>
          </el-tooltip>
        </div>
        <div>{{article.date}}</div>
      </div>
      <el-divider></el-divider>
      <pagination class="pagination"/>
    </el-card>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name:'NuxtArticle',
  data(){
    return {
      articleList:[
        {
          index:0,
          title:'Vue',
          href:'https://element.eleme.cn/#/zh-CN/component/link',
          date:'2022-4-25',
          tips:'vue'
        },
        {
          index:1,
          title:'React',
          date:'2022-4-25',
          tips:'ract'
        },
        {
          index:2,
          title:'JQuary',
          date:'2022-4-25'
        },
        {
          index:3,
          title:'React',
          date:'2022-4-25'
        },
        {
          index:4,
          title:'Vue',
          href:'https://element.eleme.cn/#/zh-CN/component/link',
          date:'2022-4-25'
        },
        {
          index:5,
          title:'React',
          date:'2022-4-25'
        },
        {
          index:6,
          title:'JQuary',
          date:'2022-4-25'
        },
        {
          index:7,
          title:'React',
          date:'2022-4-25'
        },
        {
          index:8,
          title:'React',
          date:'2022-4-25'
        },
        {
          index:9,
          title:'JQuary',
          date:'2022-4-25'
        },
        {
          index:10,
          title:'React',
          date:'2022-4-25'
        },
      ]
    }
  },
  mounted(){
    axios
      .get("http://localhost:3000/article?SkipCounts=0&MaxCounts=10")
      .then((res) => {
        console.log('res---',res.data)
        const { code, msg } = res.data
        if(code === 200) {
            this.articleList = res.data.data
            console.log(this.articleList)
        }else{
          this.$message.error(msg)
        }
      })
      .catch((err) => {
        console.log(err);
      });
  }
}
</script>

<style lang="scss" scoped>
.article{
  position: relative;
  left: 40%;
  top: -30%;
  width: 700px;
}
.article_item{
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
}
.pagination{
  margin-top: 20px;
  align-items: flex-end;
  display: flex;
  justify-content: flex-end;
}
</style>
