<template>
  <div class="register">
    <div class="welcome">
      <div class="welcome_content">
        <a href="#" class="logo"></a>
        <div class="logo_title">欢迎注册</div>
        <div class="have_account">
          已有账号?
          <span @click="gotologin">请登录></span>
        </div>
      </div>
    </div>
    <div class="container">
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
                  <input
                    type="text"
                    maxlength="11"
                    class="feild"
                    placeholder="建议使用常用手机号"
                    v-model="inputValue"
                    @focus="inputFocus"
                    @blur="inputBlur"
                  >
                  <span class="gou" v-if="gouShow">√</span>
                </p>
              </div>
            </div>

            <p class="get_focus" :style="{color: fontColor}">{{ info }}</p>
          </div>
        </div>
        <div class="item-phone-wrap">
          <div class="form-item form-item-phone">
            <div style="overflow:hidden">
              <div class="select_country">密码</div>
              <div class="item-input-wrap">
                <p class="biaodan">
                  <input
                    type="text"
                    class="feild"
                    placeholder="请输入密码"
                    v-model="pwValue"
                    @focus="passwordFocus"
                    @blur="passwordBlur"
                    @input="passwordChange"
                  >
                  <span class="gou" v-if="pwgouShow">√</span>
                </p>
              </div>
            </div>
            <p class="get_focus" :style="{color: pwColor}">{{ pwinfo }}</p>
          </div>
        </div>
        <div class="btn-register" @click="register">下一步</div>
        <div class="reg-other">
          <span href="#" style="float:left;">
            <span class="iconfont icon-yonghuzhuce"></span>
            企业用户注册
          </span>
          <span href="#" style="float:right;">
            <span class="iconfont icon-quanqiu"></span>
            海外用户注册
          </span>
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
import axios from 'axios';
export default {
  data() {
    return {
      info: "",
      inputValue: "",
      gouShow: false,
      fontColor: "#333",
      pwValue: "",
      pwinfo: "",
      pwgouShow: false,
      pwColor: "#333",
    };
  },
  methods: {
    gotologin() {
      this.$router.push('/login');
    },
    inputFocus() {
      if (!this.inputValue) {
        this.info = "验证完成后，你可以使用该手机登录或找回密码";
        this.fontColor = "#333";
      }
    },
    inputBlur() {
      if (this.inputValue) {
        let reg = /^1[3578]\d{9}$/;
        if (reg.test(this.inputValue)) {
          this.info = "";
          this.gouShow = true;
          this.fontColor = "#333";
        } else {
          this.info = "格式错误";
          this.gouShow = false;
          this.fontColor = "orange";
        }
      } else {
        this.info = "";
      }
    },
    passwordFocus() {
      if (!this.pwValue) {
        this.pwinfo = "请输入6-16位密码";
        this.pwColor = "#333";
      }
    },
    passwordBlur() {
      if (!this.pwValue) {
        this.pwinfo = "";
      }
    },
    passwordChange() {
      if (this.pwValue.length >= 6 && this.pwValue.length <= 16) {
        let regnum = /\d+/; //数字
        let reglower = /[a-z]+/; //小写字母
        let regupper = /[A-Z]+/; //大写字母
        let other = /[W_]+/; //特殊字符
        let count = 0;
        if (regnum.test(this.pwValue)) {
          count++;
        }
        if (reglower.test(this.pwValue)) {
          count++;
        }
        if (regupper.test(this.pwValue)) {
          count++;
        }
        if (other.test(this.pwValue)) {
          count++;
        }

        switch (count) {
          case 1:
            this.pwinfo = "弱";
            this.pwColor = "red";
            break;
          case 2:
          case 3:
            this.pwinfo = "中";
            this.pwColor = "orange";
            break;
          case 4:
            this.pwinfo = "强";
            this.pwColor = "green";
            break;
        }
      } else {
        this.pwinfo = "密码长度有问题";
        this.pwColor = "orange";
      }
    },
    register() {
      axios
        .post("http://118.24.239.63:3000/users/register", {
          userName: this.inputValue,
          userPwd: this.pwValue
        })
        .then(function(response) {
          if (response.data.status == '0') {
            //alert(response.data.msg);
            alert('注册成功，请登录');
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
.welcome {
  width: 100%;
  height: 110px;
  background: url(//misc.360buyimg.com/user/reg/3.0.0/css/i/headbg.jpg) repeat-x
    left bottom;
  .welcome_content {
    width: 1210px;
    height: 76px;
    margin: 0 auto;
    .logo {
      width: 160px;
      height: 50px;
      background: url(//misc.360buyimg.com/user/reg/3.0.0/css/i/icon.png)
        no-repeat;
      float: left;
      margin-top: 24px;
    }
    .logo_title {
      float: left;
      height: 34px;
      line-height: 34px;
      font-size: 24px;
      color: #333;
      margin-top: 34px;
    }
    .have_account {
      font-size: 16px;
      float: right;
      margin-top: 55px;
      color: #999;
      span {
        color: #ee2222;
        cursor: pointer;
      }
    }
  }
}
.container {
  width: 1210px;
  margin: 100px auto;
  display: flex;
  justify-content: center;
  align-items: center;
  .center {
    width: 400px;
    .item-phone-wrap {
      height: 86px;
      position: relative;
      z-index: 2;
      .form-item {
        position: relative;
        width: 398px;
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
            line-height: 49px;
            color: red;
          }
        }
        .item-input-wrap {
          width: 290px;
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
    .reg-other {
      width: 100%;
      margin-top: 28px;
      a {
        display: inline-block;
        width: 118px;
        height: 28px;
        color: #333;
        cursor: pointer;
        font-size: 14px;

        .icon-yonghuzhuce,
        .icon-quanqiu {
          display: inline-block;
          margin: 0 8px 2px 0;
          vertical-align: middle;
          font-size: 22px;
        }
      }
    }
  }
}
.footer {
  width: 1210px;
  text-align: center;
  border-top: solid 1px #e6e6e6;
  color: #999;
  padding-bottom: 30px;
  margin: 0 auto;
  .links {
    padding-top: 30px;
    padding-bottom: 15px;
    a {
      color: #999;
      margin: 0 10px;
    }
  }
}
</style>

