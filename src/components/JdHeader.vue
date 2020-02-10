<template>
  <div id="header">
    <div class="header">
      <img src="../assets/images/logo.gif" alt class="logo">
      <div class="pictrue"></div>
      <div id="search">
        <div class="search-m">
          <div class="form" role="serachbox">
            <div id="J_searchbg" class="search_bg">{{ searchList[searchIndex] }}</div>
            <input
              clstag="h|keycount|head|search_c"
              type="text"
              autocomplete="off"
              id="key"
              accesskey="s"
              class="text"
              aria-label="搜索"
              style="background: transparent;"
            >
            <button clstag="h|keycount|head|search_a" class="button" aria-label="搜索">
              <span class="iconfont icon-fangdajing"></span>
            </button>
          </div>

          <div id="settleup" class="dropdown" clstag="h|keycount|head|cart_null">
            <div class="cw-icon" @click="$router.push('/cartlist')">
              <span class="iconfont icon-icon22fuzhi"></span>
              <span>我的购物车</span>
              <i class="ci-count" id="shopping-amount">0</i>
            </div>
          </div>
        </div>
      </div>
      <div id="hotwords" clstag="h|keycount|head|search_d" role aria-label="热搜词">
        <a href="#" target="_blank" 
          v-for="(item, index) in rsList" 
          v-bind:key="index" 
          v-bind:class="{ styleRed: index == 0 }">{{ item }}</a>
      </div>
      <div id="navitems" role="navigation">
        <ul id="navitems-group1">
          <li v-for="(item, index) in navList"
            v-bind:key="index">
            <a class="navitems-lk" target="_blank" href="#">{{ item }}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rsList: ['抢五折神券', '二手浪琴', '超市年货', '车品5折', '美妆护肤', '爆款电视', '买一赠一', '每100-50', '限时7折'],
      navList: ['秒杀', '优惠券', 'PLUS会员', '品牌闪购', '拍卖', '京东家电', '京东超市', '京东生鲜', '京东国际', '京东金融'],
      searchList: ['恒温调奶器', '二手浪琴', '京东家电'],
      searchIndex: 0
    }
  },
  mounted() {
    setInterval(() => {
      this.searchIndex < 2 ? this.searchIndex++ : this.searchIndex = 0
    }, 2000)
  }
};
</script>

<style lang="scss" scoped>
#header {
  width: 100%;
  background: #fff;
  border-bottom: 1px solid #ddd;
  .header {
    width: 1190px;
    height: 141px;
    position: relative;
    margin: 0 auto;
    .logo {
      width: 190px;
      height: 120px;
      position: absolute;
      top: 10px;
    }

    .pictrue {
      width: 190px;
      height: 120px;
      position: absolute;
      bottom: 10px;
      right: 0;
      background: url(../assets/images/48b1a7b2af63b1e7.png.webp);
    }

    #search {
      .search-m {
        position: relative;
        z-index: 1;
        height: 60px;

        .form {
          position: absolute;
          left: 260px;
          top: 25px;
          width: 546px;
          height: 32px;
          border: 2px solid #e2231a;
          background: #fff;

          .search_bg {
            left: 0;
            padding: 2px 44px 2px 17px;
            width: 425px;
            height: 26px;
            border: 1px solid transparent;
            line-height: 26px;
            font-size: 12px;
          }

          .text {
            left: 0;
            padding: 2px 44px 2px 17px;
            width: 425px;
            height: 26px;
            border: 1px solid transparent;
            line-height: 26px;
            font-size: 12px;
            position: absolute;
            top: 0;
            outline: none;
          }

          .button {
            border-radius: 0;
            right: 0;
            width: 58px;
            height: 100%;
            line-height: 28px;
            border: none;
            background-color: #e1251b;
            font-size: 20px;
            font-weight: 700;
            color: #fff;
            -webkit-transition: background 0.2s ease;
            transition: background 0.2s ease;
            position: absolute;
            top: 0;
            outline: none;
          }
        }

        #settleup {
          position: absolute;
          right: 230px;
          top: 25px;
          z-index: 21;

          .cw-icon {
            width: 130px;
            height: 34px;
            background-color: #fff;
            text-align: center;
            line-height: 34px;
            border-color: #eee;
            overflow: hidden;
            position: relative;
            z-index: 1;
            float: left;
            border: 1px solid #e3e4e5;

            .iconfont {
              color: #e1251b;
              -webkit-transition: color 0.2s ease;
              transition: color 0.2s ease;
              margin-right: 13px;
              font-size: 20px;
            }

            a {
              color: #e1251b;
              -webkit-transition: color 0.2s ease;
              transition: color 0.2s ease;
            }

            .ci-count {
              position: absolute;
              top: 1px;
              left: 29px;
              right: auto;
              display: inline-block;
              padding: 1px 3px;
              font-size: 12px;
              line-height: 12px;
              color: #fff;
              background-color: #e1251b;
              border-radius: 7px;
              min-width: 12px;
              text-align: center;
            }
          }
        }
      }
    }

    #hotwords {
      overflow: hidden;
      position: absolute;
      left: 260px;
      top: 65px;
      width: 550px;
      height: 20px;
      line-height: 20px;

      .styleRed {
        color: #e1251b;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }

      a {
        float: left;
        margin-right: 10px;
        white-space: nowrap;
        color: #999;
        font-size: 12px;
        text-decoration: none;
      }
    }

    #navitems {
      overflow: hidden;
      position: absolute;
      left: 203px;
      bottom: 0;
      height: 40px;

      ul {
        float: left;

        li {
          float: left;

          a {
            position: relative;
            display: block;
            height: 40px;
            line-height: 40px;
            font-size: 15px;
            color: #333;
            margin: 0 11px;
            -webkit-transition: color 0.2s ease;
            transition: color 0.2s ease;
          }
        }
      }
    }
  }
}
</style>

