<template>
  <div class="hello">
    <error-msg :msg="msg" ref="msg"></error-msg>
    <div class="landing">
      <div class="title">登录</div>
      <div class="login">
        <div class="item">
          <label>用户名</label>
          <i-input :form="form" :deleteBoolArr="deleteBoolArr" str="user" place="请输入用户名"></i-input>
        </div>
        <div class="item">
          <label>密码</label>
          <i-input :form="form" inputType="password" :deleteBoolArr="deleteBoolArr" str="pwd" place="请输入密码"></i-input>
        </div>
      </div>
      <div class="main-btn" @click="login">登录</div>
    </div>
    <div class="links">
      <router-link :to="{ name: 'register'}">
        新用户注册
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      form: {
        user: '',
        pwd: ''
      },
      msg: '',
      msgDisplay: false,
      rule: {
        user: [
          { required: true, message: '用户名不得为空' }
        ],
        pwd: [
          { required: true, message: '密码不得为空' }
        ]
      },
      deleteBoolArr: {
        user: false,
        pwd: false
      }
    }
  },
  methods: {
    login () {
      let _this = this
      if (!this.validate()) return
      this.validate()
      // 登陆，是否需要加密信息
      this.$XHRpost('user/login', {
        username: this.form.user,
        password: this.form.pwd
      }, function (data) {
        _this.errorMsg(data.message)
        if (data.success) {
          // 跳转
          if (data.success) {
            // 储存用户名和密码
            _this.errorMsg('登录成功')
            // 跳转
          } else {
            _this.errorMsg(data.message)
          }
        } else {
          _this.errorMsg('登录失败，请稍后再试')
        }
      })
    }
  }
}
</script>
