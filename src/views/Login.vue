<template>
  <div class="login">
    <div class="w">
      <div id="logo">
        <a href="//www.jd.com/" clstag="pageclick|keycount|20150112ABD|45">
          <img
            src="//misc.360buyimg.com/lib/img/e/logo-201305-b.png"
            alt="京东"
            width="170"
            height="60"
          >
        </a>
        <b></b>
      </div>
      <a
        href="//surveys.jd.com/index.php?r=survey/index/sid/568245/lang/zh-Hans"
        target="_blank"
        class="q-link"
      >
        <b></b>登录页面，调查问卷
      </a>
    </div>
    <div id="content">
      <div class="tips-wrapper">
        <div class="tips-inner">
          <div class="cont-wrapper">
            <i class="icon-tips"></i>
            <p>
              依据《网络安全法》，为保障您的账户安全和正常使用，请尽快完成手机号验证！ 新版
              <a
                href="https://about.jd.com/privacy/"
                class="black"
                target="_blank"
              >《京东隐私政策》</a>已上线，将更有利于保护您的个人隐私。
            </p>
          </div>
        </div>
      </div>
      <div class="login_wrap">
        <div class="login_content">
          <form action class="login_form">
            <div class="tips-wrapper">
              <div class="tips-inner">
                <div class="cont-wrapper">
                  <i class="icon-tips"></i>
                  <p>京东不会以任何理由要求您转账汇款，谨防诈骗。</p>
                </div>
              </div>
            </div>
            <div class="login-tab login-tab-l">
              <span
                clstag="pageclick|keycount|login_pc_201804112|9"
                class="checked"
              >账号登录</span>
            </div>
            <div class="qrcode-login">
              <div class="center">
                <div class="item-phone-wrap">
                  <div class="form-item form-item-phone">
                    <div style="overflow:hidden">
                      <div class="select_country">
                        中国 0086
                        <span class="iconfont icon--xiangxiajiantou"></span>
                      </div>
                      <div class="item-input-wrap">
                        <p class="biaodan">
                          <input type="text" maxlength="11" class="feild" placeholder="建议使用常用手机号" v-model="username">
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="item-phone-wrap">
                  <div class="form-item form-item-phone">
                    <div style="overflow:hidden">
                      <div class="select_country">密码</div>
                      <div class="item-input-wrap">
                        <p class="biaodan">
                          <input type="text" class="feild" placeholder="请输入密码" v-model="userpassword">
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="btn-register" @click="login">登录</div>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
    <div class="footer">
      <div class="links">
        <a rel="nofollow" target="_blank" href="//www.jd.com/intro/about.aspx">关于我们</a>|
        <a rel="nofollow" target="_blank" href="//www.jd.com/contact/">联系我们</a>|
        <a rel="nofollow" target="_blank" href="//zhaopin.jd.com/">人才招聘</a>|
        <a rel="nofollow" target="_blank" href="//www.jd.com/contact/joinin.aspx">商家入驻</a>|
        <a rel="no follow" target="_blank" href="//www.jd.com/intro/service.aspx">广告服务</a>|
        <a rel="nofollow" target="_blank" href="//app.jd.com/">手机京东</a>|
        <a target="_blank" href="//club.jd.com/links.aspx">友情链接</a>|
        <a target="_blank" href="//media.jd.com">销售联盟</a>|
        <a href="//club.jd.com/" target="_blank">京东社区</a>|
        <a href="//gongyi.jd.com" target="_blank">京东公益</a>|
        <a
          target="_blank"
          href="//en.jd.com/"
          clstag="pageclick|keycount|20150112ABD|9"
        >English Site</a>
      </div>
      <div class="copyright">Copyright©2004-2020&nbsp;&nbsp;京东JD.com&nbsp;版权所有</div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      username: '',
      userpassword: ''
    }
  },
  methods: {
    login() {
      let _this = this;
      axios
        .post("http://118.24.239.63:3000/users/login", {
          userName: this.username,
          userPwd: this.userpassword
        })
        .then(function(response) {
          if (response.data.status !== '0') {
            alert(response.data.msg);
          } else {
            localStorage.setItem('username', response.data.result.userName);
            localStorage.setItem('userId', response.data.result.userId);
            _this.$router.push('/');
          }
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
};
</script>

<style lang="scss" scoped>
.w {
  width: 990px;
  margin: 0 auto;
  #logo {
    position: relative;
    width: 300px;
    margin: 10px 0;
    height: 60px;
    float: left;
  }
  a {
    color: #666;
    text-decoration: none;
    a img {
      border: 0;
      vertical-align: middle;
    }
  }
  b {
    display: block;
    width: 110px;
    height: 40px;
    position: absolute;
    right: 0;
    bottom: 0;
    background: url(//misc.360buyimg.com/user/passport/1.0.0/css/i/l-icon.png)
      no-repeat;
  }
  .q-link {
    position: relative;
    color: #999;
    float: right;
    top: 52px;
    b {
      display: inline-block;
      height: 14px;
      margin: -1px 20px;
      background: url(//misc.360buyimg.com/user/passport/1.0.0/css/i/q-icon.png)
        no-repeat;
      overflow: hidden;
      vertical-align: middle;
    }
  }
}
#content {
  clear: both;
  .tips-wrapper {
    background: #fff8f0;
    width: 100%;
    padding-top: 10px;
    padding-bottom: 10px;
    text-align: center;
    .cont-wrapper {
      display: inline-block;
      width: 90%;
    }
    .icon-tips {
      background: url(//misc.360buyimg.com/user/passport/1.0.0/widget/login-form-2018-0827/i/icon-tips.png);
      display: inline-block;
      width: 16px;
      height: 16px;
      vertical-align: middle;
      margin-right: 5px;
    }
    p {
      vertical-align: middle;
      color: #999;
      font-size: 12px;
      display: inline-block;
    }
  }
  .login_wrap {
    position: relative;
    height: 475px;
    margin: 0 0 20px;
    z-index: 5;
    background: url(../assets/images/banner.png) no-repeat center center;
    background-color: #e93854;
    .login_content {
      width: 990px;
      margin: 0 auto;
      .login_form {
        float: right;
        top: 10px;
        position: relative;
        z-index: 4;
        background: #fff;
        overflow: visible;
        width: 346px;
        height: 430px;
        .tips-wrapper {
          background: #fff8f0;
          width: 100%;
          padding-top: 10px;
          padding-bottom: 10px;
          text-align: center;
          .icon-tips {
            background: url(//misc.360buyimg.com/user/passport/1.0.0/widget/login-form-2018-0827/i/icon-tips.png);
            display: inline-block;
            width: 16px;
            height: 16px;
            vertical-align: middle;
            margin-right: 5px;
          }
          p {
            vertical-align: middle;
            color: #999;
            font-size: 12px;
            display: inline-block;
          }
        }
        .login-tab-l {
          width: 100%;
        }
        .login-tab {
          height: 54px;
          font-size: 18px;
          text-align: center;
          border-bottom: 1px solid #f4f4f4;
          // position: absolute;
          background: #fff;
          display: block;
          .checked {
            font-weight: 700;
            color: #e4393c;
          }
          span {
            width: 99%;
            height: 18px;
            // position: absolute;
            line-height: 54px;
            left: 0;
            top: 18px;
            border-right: 1px solid #f4f4f4;
          }
        }
      }
    }
  }
  .qrcode-login {
    width: 306px;
    height: 324px;
    margin-left: 20px;
    .center {
      width: 306px;
      .item-phone-wrap {
        width: 100%;
        height: 86px;
        position: relative;
        z-index: 2;
        .form-item {
          position: relative;
          width: 306px;
          height: 52px;
          z-index: 0;
          .select_country {
            width: 108px;
            line-height: 52px;
            font-size: 14px;
            color: #666;
            padding-left: 20px;
            float: left;
            border: 1px solid rgb(153, 153, 153);
            border-right: none;
            .iconfont {
              line-height:49px;
              color: red;
            }
          }
          .item-input-wrap {
            width: 198px;
            height: 54px;
            float: left;
            border: 1px solid rgb(153, 153, 153);
            border-left: 1px solid transparent;
            overflow: hidden;
            position: relative;
            input {
              color: #333;
              font-size: 14px;
              margin: 0px 0 0 20px;
              line-height: 52px;
              outline: none;
              border: none;
            }
            .gou {
              color: green;
              position: absolute;
              right: 28px;
              top: 16px;
              font-size: 16px;
            }
            &:focus-within {
              border: 1px solid #333;
            }
          }
          .get_focus {
            width: 100%;
            margin-top: 6px;
            font-size: 12px;
            color: #333;
          }
        }
      }
      .form-item-getcode {
        height: 54px;
        position: relative;
        z-index: 2;
        line-height: 52px;
        text-align: center;
        font-size: 14px;
        color: #333;
        cursor: pointer;
        border: 1px solid rgb(153, 153, 153);
      }
      .btn-register {
        width: 100%;
        height: 54px;
        line-height: 54px;
        text-align: center;
        color: #fff;
        background: #e2231a;
        border: 0;
        font-size: 16px;
        cursor: pointer;
        margin-top: 24px;
      }
    }
  }
}
.footer {
  width: 1210px;
  text-align: center;
  color: #999;
  padding-bottom: 30px;
  margin: 0 auto;
  .links {
    padding-bottom: 15px;
    a {
      color: #999;
      margin: 0 10px;
    }
  }
}
</style>


