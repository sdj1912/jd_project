<template>
  <div class="top">
    <div class="main">
      <div class="left">
        <span class="iconfont icon-danseshixintubiao-"></span>
        <span class="province">北京</span>
      </div>
      <nav class="right">
        <a href="#" class="hello" v-on:click="goToLogin" v-if="!username">你好,请登录</a>
        <a href="#" class="free" v-on:click="goToRegister" v-if="!username">免费注册</a>
        <a href="#" v-if="username">欢迎你，{{ username }}</a>
        <a href="#" v-if="username" @click="exit">退出</a>
        <span>|</span>
        <a href="#" class="order">我的订单</a>
        <span>|</span>
        <a href="#" class="order">
          我的京东
          <i class="iconfont icon--xiangxiajiantou"></i>
        </a>
        <span>|</span>
        <a href="#" class="order">京东会员</a>
        <span>|</span>
        <a href="#" class="free">
          企业采购
          <i class="iconfont icon--xiangxiajiantou"></i>
        </a>
        <span>|</span>
        <a href="#" class="order">
          客户服务
          <i class="iconfont icon--xiangxiajiantou"></i>
        </a>
        <span>|</span>
        <a href="#" class="order">
          网站导航
          <i class="iconfont icon--xiangxiajiantou"></i>
        </a>
        <span>|</span>
        <a href="#" class="order">手机京东</a>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: localStorage.getItem('username')
    }
  },
  methods: {
    goToLogin() {
      this.$router.push('/login')
    },
    goToRegister() {
      this.$router.push('/register')
    },
    exit() {
      localStorage.removeItem('username')
      this.username = ''
    }
  }
};
</script>

<style lang="scss" scoped>
.top {
  height: 30px;
  width: 100%;
  background: #e3e4e5;
  display: flex;
  justify-content: center;

  .main {
    width: 1190px;
    height: 100%;
    display: flex;
    justify-content: space-between;

    .left {
      display: flex;
      align-items: center;

      .province {
        color: #999;
        font-size: 12px;
      }

      .iconfont {
        color: rgb(194, 26, 39);
      }
    }

    .right {
      font-size: 12px;
      display: flex;
      align-items: center;
      color: #999;

      a {
        color: inherit;
        text-decoration: none;
        padding: 0 7px;

        &:hover {
          color: rgb(194, 26, 39);
        }

        .iconfont {
          font-size: 12px;
        }
      }

      .hello {
        margin-right: 7px;
      }

      .free {
        color: rgb(194, 26, 39);
      }

      span {
        margin: 0 7px;
      }
    }
  }
}
</style>

