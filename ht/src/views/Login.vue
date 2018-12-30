<template>
  <div class="login">
    <el-form ref="form" :model="form" :rules="rules" class="container">
      <el-form-item>
        <div class="avatar">
           <img src="../assets/avatar.jpg" alt="">
        </div>
      </el-form-item>
      <el-form-item prop="username">
        <el-input v-model="form.username" placeholder="账户" prefix-icon="myicon myicon-user"></el-input>
      </el-form-item>
      <el-form-item prop="password"> <el-input v-model="form.password" placeholder="密码" prefix-icon="myicon myicon-key"></el-input></el-form-item>
      <el-form-item>
         <el-button type="primary" class="login-btn">登陆</el-button>
      </el-form-item> 
    </el-form>
  </div>
</template>

<script>
export default {

  data () {
    return {
      form:{
        username:'',
        password:'',
      },
      rules:{
        username:[
          { required: true, message: '请输入用户名', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
         password:[
          { required: true, message: '请输入用密码', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个数字或者字符', trigger: 'blur' }
        ]
      }
    }
  },

  methods: {},

  created () {
  }
}
</script>

<style lang="scss" scoped>
  .login{
    display: fixed;
    width: 100%;
    height: 100%;
    background-color: #2f4050;
    .container {
      position: relative;
      border: 2px solid #ccc;
      width: 600px;
      left: 50%;
      top: 40%;
      transform: translateX(-50%);
      background-color: white;
      padding: 60px 30px 10px 30px;
      border-radius: 5px;
      .login-btn {
        width: 100%;
      }
    .avatar {
      position: absolute;
      left: 50%;
      transform: translate(-50%,-105%);
      height: 110px;
      width: 110px;
      border: 7px solid white;
      box-shadow: 0px 1px 25px 1px;
      border-radius: 50%;
      overflow: hidden;
      z-index: 1;
    }
    }
  }
</style>
