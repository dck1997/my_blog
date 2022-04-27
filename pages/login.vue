<template>
  <div>
    <div class="content">
      <el-form class="form">
        <el-form-item class="flex center" label="账号：">
          <el-input v-model="UserName" placeholder="请输入账号" size="medium" label="用户名"></el-input>
        </el-form-item>
        <el-form-item class="flex center" label="密码：">
          <el-input v-model="PassWord" placeholder="请输入密码" size="medium" type="password"></el-input>
        </el-form-item>
        <el-form-item class="button">
          <el-button type="primary" @click="onSubmit" size="medium">登录</el-button>
          <el-button size="medium">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return {
      UserName:'admin',
      PassWord:'123456'
    }
  },
  // created() {
  //   axios
  //     .get("http://localhost:3000/test")
  //     .then((res) => {
  //       this.msg = res.data;
  //     })
  //     .catch((err) => {
  //       console.log(err);
  //     });
  // },
  methods:{
    onSubmit(){
      axios
      .post("http://localhost:3000/login",{
        UserName:this.UserName,
        PassWord:this.PassWord
      })
      .then((res) => {
        console.log('res---',res.data)
        const { code, msg } = res.data
        if(code === 200) {
          this.$router.push({
            path: `/`
          })
        }else{
          this.$message.error(msg)
        }
      })
      .catch((err) => {
        console.log(err);
      });
    }
  },
  asyncData(){

    return {
    }
  }
}
</script>

<style lang="scss" scoped>
.form{
  position: relative;
  display: flex;
  flex-direction: column;
  width: 50%;
  padding: 50px 30px 10px 30px;
  font-size: 24px;border-radius: 12px;
  background-color: rgba(255,255,255,.2);
  overflow: hidden;
  backdrop-filter: blur(15px);
  box-shadow: 0 0 10px #333;
}
::v-deep .el-form-item__content{
  width: 80%;
}
.flex{
  display: flex;
}
.center{
  text-align: center;
}
.content{
  //background: linear-gradient(white, black);
  margin: 10% auto;
  height: 350px;
  width: 650px;
  padding: 30px;
  background-image: url("~/static/login.webp");
  background-repeat: no-repeat;
  border-radius: 25px;
  background-size: cover;
  background-position: center center;
  backdrop-filter: blur(30px);
  border: 2px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 0 80px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;

}
.button{
  text-align: center;
}
</style>
