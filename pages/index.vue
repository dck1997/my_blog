<template>
  <div>
    <TopNav/>
    <div class="content">
      <card/>
      <Article/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
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
