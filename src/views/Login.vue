<template>
  <div class="login_container">
    <!--登录区域  -->
    <div class="login_box">
      <!-- 头像     -->
      <div class="avatar_box">
        <img src="../assets/img/avatar.jpg">
      </div>

      <!-- 登录表单     -->
      <el-form ref="loginForm" :rules="loginRules" :model="loginForm" label-width="0px" class="login_form">
        <!-- 用户名       -->
        <el-form-item  prop="username">
          <el-input v-model="loginForm.username" prefix-icon="el-icon-user-solid"></el-input>
        </el-form-item>
        <!--  密码      -->
        <el-form-item  prop="password">
          <el-input v-model="loginForm.password" prefix-icon="el-icon-lock"></el-input>
        </el-form-item>
        <!--  验证码      -->
        <el-form-item  prop="verifyCode">
          <div class="verifyCode_box">
            <el-input v-model="loginForm.verifyCode" prefix-icon="el-icon-mobile-phone" class="verify_code"></el-input>
            <img src="../assets/img/msFwut.png" class="verify_img" alt="验证码加载失败">
          </div>
        </el-form-item>
        <!--登录按钮-->
        <el-form-item class="login_btn">
          <el-button type="primary" @click="submitForm('loginForm')">登录</el-button>
          <el-button @click="resetForm('loginForm')">重置</el-button>
        </el-form-item>
      </el-form>


    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      loginForm: {
        username: '',
        password: '',
        verifyCode: '',
      },
      loginRules:{
        username:[
          { required: true,message: "请输入用户名称", trigger: 'blur'},
          { min: 3, max: 16, message: "长度在3到16个字符" , trigger: 'blur'},
        ],
        password:[
          { required: true,message: "请输入登录密码", trigger: 'blur'},
          { min: 3, max: 16, message: "长度在3到16个字符" , trigger: 'blur'},
        ],

        verifyCode:[
          { required: true,message: "请输入验证码", trigger: 'blur'},

        ],

      }
    };
  },
  methods: {
    //注意，这里的函数名称一定要和按钮的名称对应，否则按钮会失效
    submitForm(formName){
      this.$refs[formName].validate((valid) => {
        if(valid){
          this.$router.push("/home");
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    },
    resetForm(formName){
      this.$refs[formName].resetFields();
    }
  }

}
</script>

<style lang="less" scoped>

.login_container{
  height: 100%;
  background-color: aquamarine;
}
.login_box{
  width: 450px;
  height: 380px;
  background-color: #FFFFFF;
  border-radius: 3px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%);


  .avatar_box{
    width: 130px;
    height: 130px;
    border: 1px solid #eeeeee;
    border-radius: 50%;
    padding: 10px;
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
    margin: -65px auto;
    background-color: #FFFFFF;

    img{
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background-color: #eeeeee;
    }

  }

  .login_form{
    position: absolute;
    bottom: 0px;
    width: 100%;
    padding: 0px 30px;
    box-sizing: border-box;


    .login_btn{
      display: flex;
      //将按钮向右边滑动放置，为验证码挪出空格
      justify-content: flex-end;
    }

    .verify_code{
      width: 60%;
    }

    .verifyCode_box{
      display: flex;
      .verify_code{
        width: 70%;
        justify-content: left;
      }
    }

    .verify_img{
      width: 30%;
      height: 45px;
      justify-content: flex-end;
    }

  }
}

</style>
