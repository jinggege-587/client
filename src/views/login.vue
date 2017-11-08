<template>
  <div id="login">
    <div class="page-wrap">
      <div class="page-title">
        <a @click="$router.go(-1)">
          <i class="icon-back"></i>
        </a>
        <span>登录</span>
      </div>
      <div class="page-content">
        <mt-field 
          style="margin-top: 10px;border-top: 1px solid #ccc" 
          label="账户" 
          placeholder="请输入账户" 
          :attr="{
            maxLength: 11
          }"
          :state="fieldState.identifier" 
          v-model="loginForm.identifier" 
          @blur.native.capture="check('identifier')"
          >
        </mt-field>
        <mt-field 
          label="密码"
          style="border-bottom: 1px solid #ccc"
          placeholder="请输入登录密码"
          :attr="{
            maxLength: 20
          }"
          type="password" 
          :state="fieldState.password" 
          v-model="loginForm.password">
        </mt-field>
        <div style="margin: 10px 0;text-align: center; font-size: 12px;">
          <div style="">
            <input style="margin: 1px 0;width: 15px;height:15px;" type="checkbox" v-model="loginForm.validate">
            <span style="vertical-align: top;color: #888;">注册或使用网站账号登录即视为您已同意</span>
          </div>
          <div style="font-size: 14px;">
            <router-link tag="span" :to="{path: '/agreement'}">《用户使用协议》</router-link>
          </div>
        </div>
        <div style="padding: 0px 10px;">
          <mt-button style="width:100%;margin: 20px 0 10px 0;background-color:#FE4D45;color:#ffffff;" @click="sumbit('loginForm')">登录</mt-button>
          <a href="javascript: void(0);" style="color:#aaa;font-size: 14px;" @click="$router.replace({name: 'smsLogin'})">→使用短信验证码登录</a>
          <mt-button style="width:100%;margin-top: 20px;border-bottom-color:#FE4D45;color:#FE4D45;" plain @click="$router.push({name: 'register'})">手机号快速注册</mt-button>
        </div>
      </div>
    </div>
	<div class="login-weixin">
		<div class="describe">
			<span class="f_"></span>
			<span style="padding: 0 0.8rem;">其他方式登录</span>
			<span class="f_"></span>
		</div>
		<p style="text-align:center;" @click="weixin()"><img src="../../static/img/wechat_session.png" alt=""></p>
	</div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      loginForm: {
        identifier: '',
        password: '',
        validate: true
      },
      fieldState: {
        identifier: '',
        password: ''
      },
      toastClient: ''
    }
  },
  created () {
  },
  activated () {
  },
  methods: {
    check (fieldName) {
      if (!this.loginForm[fieldName]) {
        this.fieldState[fieldName] = 'error'
      } else {
        this.fieldState[fieldName] = 'success'
      }
    },
    validateField (field, scope) {
      let valid = true
      switch (field) {
        case 'identifier':
          if (!scope.identifier.trim()) {
            this.toast('请输入账号')
            valid = false
          }
          break
        case 'password':
          if (!scope.password.trim()) {
            this.toast('请输入密码')
            valid = false
          }
          break
        case 'validate':
          if (!scope.validate) {
            this.toast('请勾选同意')
            valid = false
          }
          break
        default:
          break
      }
      this.check(field)
      return valid
    },
    sumbit (formName) {
      let valid = true
      if (formName === 'loginForm') {
        for (let k in this.loginForm) {
          valid = this.validateField(k, this.loginForm)
          if (!valid) {
            return
          }
        }
        if (valid) {
          this.$api.login(this.loginForm, data => {
            window.localStorage.setItem('expirationTime', data.resource.expirationTime)
            window.localStorage.setItem('token', data.resource.token)
            window.localStorage.setItem('identifier', this.loginForm.identifier)
            this.toast('登录成功')
            this.$router.replace({name: 'userCenter'})
          }, e => {
            this.toast(`登录失败,${e.message}`)
          })
        }
      }
    },
    toast (message) {
      if (this.toastClient) {
        this.toastClient.close()
      }
      this.toastClient = this.$toast({
        message: message,
        position: 'middle',
        duration: 2000
      })
    },
	weixin (code){
		window.android.weiLogin();
	},
	push (code){
		$.ajax({
			url: "/client//wechatLogin",
			type: "post",
			data: {
				"code": code
			},
			success: function(result) {
				var code = result.responseCode;
				if (code == "200") {
					var data = result.message;
					window.localStorage.setItem("token", data);
					window.location.href = '/ppapp/#/userCenter';
				} else {
					alert("error");
				}
			}
		})
	}
  }
}
</script>

<style>
	.login-weixin{
		height: 3rem;
	}
	.login-weixin .describe{
		height: 2rem;
		padding: 0 3rem;
	}
	.login-weixin .describe span{float: left;display: inline-block;}
	.login-weixin .describe span.f_{
		width: 6rem;
		background: #eaeaea;
		height: 1px;
		margin-top: .6rem;
	}

</style>
