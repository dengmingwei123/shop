<template>
  <div class='login'>
    <el-form
      ref="form"
      :model='form'
      :rules="rules"
      label-width="80px"
      status-icon
    >
      <img src="@/common/image/user.jpg">
      <el-form-item
        label='用户名'
        prop='username'
      >
        <el-input
          v-model='form.username'
          placeholder='请输入用户名'
        ></el-input>
      </el-form-item>
      <el-form-item
        label='密码'
        prop='password'
      >
        <el-input
          type='password'
          v-model='form.password'
          placeholder='请输入密码'
        ></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary">立即创建</el-button>
        <el-button>取消</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        username: '',
        password: ''
      },
      rules: {
        username: [
          {
            required: true,
            message: '请输入用户名',
            trigger: 'change'
          },
          {
            min: 3,
            max: 9,
            message: '长度在 3 到 9 个字符',
            trigger: 'change'
          }
        ],
        password: [
          {
            required: true,
            message: '请输入密码',
            trigger: 'change'
          },
          {
            min: 6,
            max: 12,
            message: '长度在 6 到 12 个字符',
            trigger: 'change'
          }
        ]
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~common/stylus/variable.styl';

.login {
  width: 100%;
  height: 100%;
  background-color: $color-background;
  overflow: hidden;

  .el-form {
    position: relative;
    width: 385px;
    height: 200px;
    background: #fff;
    margin: 200px auto;
    padding: 75px 40px 0 50px;
    border-radius: 20px;

    img {
      position: absolute;
      top: 0;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 120px;
      height: 120px;
      border-radius: 50%;
      border: 10px solid #fff;
    }
  }
}
</style>
