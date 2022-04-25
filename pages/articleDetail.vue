<template>
  <div>
    <TopNav/>
    <div class="content">
      <articleDetail/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ArticleDetailPage',
}
</script>

<style lang="scss" scoped>
.content{
  width: 80%;
  height: 100%;
  margin-left: 10%;
  margin-top: 5%;
  padding: 20px;
  background: darkgrey;
  position: absolute;
  border-radius: 10px;
}
</style>
