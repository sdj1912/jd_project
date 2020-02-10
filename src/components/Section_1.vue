<template>
  <section class="section_1">
    <div class="bg"></div>
    <div class="content">
      <div class="wrap">
        <ul class="wrap_ul">
          <li class="cate_menu_item" v-for="(items, indexs) in wrap_ul" :key="indexs">
            <span target="_blank" class="cate_menu_lk" href="#" v-for="(item, index) in items" :key="index">
              {{ item }}
              <span class="cate_menu_line" v-if="index != 0">/</span>
            </span>
          </li>
        </ul>
        <div class="cate_pop"></div>
      </div>
      <div class="banner">
        <ul class="lunbo">
          <li
            v-for="(item, index) in lunboList"
            v-bind:key="index"
            class="lunbo_li"
            v-bind:class="{ show: index == lunboIndex }"
          >
            <img :src="item.imgUrl" alt>
          </li>
          <a href="javascript:;" id="left" v-on:click="leftClick">
            <span>&lt;</span>
          </a>
          <a href="javascript:;" id="right" v-on:click="rightClick">
            <span>&gt;</span>
          </a>
          <ul class="btnlist">
            <li
              v-for="(item, index) in lunboList"
              :key="index"
              class="btnlist_li"
              :class="{ btnShow: index == lunboIndex }"
              v-on:mouseover="btnover(index)"
            ></li>
          </ul>
        </ul>

        <div class="focus_change">
          <a href="#" class="images">
            <img src="../assets/images/2a8bc80726f21303.jpg.webp" alt>
          </a>
          <a href="#" class="images">
            <img src="../assets/images/2a8bc80726f21303.jpg.webp" alt>
          </a>
          <a href="#" class="images">
            <img src="../assets/images/2a8bc80726f21303.jpg.webp" alt>
          </a>
        </div>
      </div>
      <div class="detail">
        <div class="first_part">
          <div class="first_top">
            <img src="../assets/images/small.png" alt>
            <div class="font">
              <p>hi~欢迎逛京东</p>
              <p>登录 | 注册</p>
            </div>
          </div>
          <div class="first_button">
            <button class="new">新人福利</button>
            <button class="member">PLUS会员</button>
          </div>
          <!-- ::after -->
        </div>
        <div class="second_part">
          <div class="second_top">
            <h3>京东快报</h3>
            <p>更多 ></p>
          </div>
          <ul>
            <li>
              <a href="#">热门</a>
              <p>iphone 12再次确认真全面屏+苹果A14+5G</p>
            </li>
            <li>
              <a href="#">推荐</a>
              <p>买太早了！华为P30一夜沦为“小米价”，售价感人</p>
            </li>
            <li>
              <a href="#">最新</a>
              <p>iPhone 11买早了，iPhone SE2正式确认</p>
            </li>
            <li>
              <a href="#">热门</a>
              <p>华为6000mAh新机曝光！麒麟1020坐镇支持5G！</p>
            </li>
          </ul>
        </div>
        <ul class="third_part">
          <li v-for="(item ,index) in thirdPartList" v-bind:key="index">
            <span class="iconfont" :class="item.iconName" :style="{color:item.color}"></span>
            <a href="#">{{ item.name }}</a>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      lunboList: [],
      lunboIndex: 0,
      thirdPartList: [
        {
          iconName: "icon-huafei",
          color: "#7fb3e4",
          name: "话费"
        },
        {
          iconName: "icon-guoneijipiaotongji",
          color: "#e7a54c",
          name: "机票"
        },
        {
          iconName: "icon-jiudian",
          color: "#71d4c7",
          name: "酒店"
        },
        {
          iconName: "icon-youxi",
          color: "#e7a54c",
          name: "游戏"
        },
        {
          iconName: "icon-shuidi",
          color: "#71d4c7",
          name: "加油卡"
        },
        {
          iconName: "icon-huochepiao",
          color: "#df8076",
          name: "火车票"
        },
        {
          iconName: "icon-jingdongzhongchou",
          color: "#7fb3e4",
          name: "众筹"
        },
        {
          iconName: "icon-licai",
          color: "#71d4c7",
          name: "理财"
        },
        {
          iconName: "icon-baitiaoshanfu",
          color: "#df8076",
          name: "白条"
        },
        {
          iconName: "icon-dianyingpiao",
          color: "#df8076",
          name: "电影票"
        },
        {
          iconName: "icon-qiyegou-e",
          color: "#7fb3e4",
          name: "企业购"
        },
        {
          iconName: "icon-lipinqia",
          color: "#e7a54c",
          name: "礼品卡"
        }
      ],
      wrap_ul:[]

    };
  },
  mounted() {
    // 获取数据
    this.getLunboList();
    this.getWrap_ul();
  },
  methods: {
    getLunboList() {
      let _this = this;
      axios
        .get("http://118.24.239.63:3000/lunbo")
        .then(function(response) {
          if (response.data.status == 0) {
            _this.lunboList = response.data.result.list;
          }
        })
        .catch(function(error) {
          console.log(error);
        });
    },
    getWrap_ul() {
      let _this = this;
      axios
        .get("http://118.24.239.63:3000/tabs")
        .then(function(response) {
           if (response.data.status == 0) {
            _this.wrap_ul = response.data.result;
          }
        })
        .catch(function(error) {
          console.log(error);
        });
    },
    leftClick() {
      this.lunboIndex > 0 ? this.lunboIndex-- : (this.lunboIndex = 7);
    },
    rightClick() {
      this.lunboIndex < 7 ? this.lunboIndex++ : (this.lunboIndex = 0);
    },
    btnover(index) {
      this.lunboIndex = index;
    }
  }
};
</script>

<style lang="scss" scoped>
.section_1 {
  width: 100%;
  height: 480px;
  position: relative;
  .bg {
    position: absolute;
    width: 100%;
    height: 100%;
    background: url(../assets/images/31e19d93197249c1.png.webp) no-repeat center;
  }
  .content {
    background: #f4f4f4;
    width: 1190px;
    margin: 0 auto;
    overflow: hidden;
    height: 100%;
    .wrap {
      width: 190px;
      margin-right: 10px;
      float: left;
      height: 100%;
      .wrap_ul {
        overflow: hidden;
        padding: 10px 0;
        height: 480px;
        background-color: #fefefe;
        color: #636363;
        margin-top: 10px;
        .cate_menu_item {
          overflow: hidden;
          padding-left: 18px;
          height: 24px;
          line-height: 24px;
          font-size: 14px;
          -webkit-transition: background-color 0.2s ease;
          transition: background-color 0.2s ease;
          .cate_menu_lk {
            text-decoration: none;
            color: #333;
            float: left;
          }
          .cate_menu_line {
            padding: 0 2px;
            font-size: 12px;
            float: left;
          }
        }
      }
      .cate_pop {
        display: none;
        position: absolute;
        left: 191px;
        top: 0;
        width: 998px;
        min-height: 468px;
        border: 1px solid #f7f7f7;
        background-color: #fff;
        -webkit-box-shadow: 2px 0 5px rgba(0, 0, 0, 0.3);
        box-shadow: 2px 0 5px rgba(0, 0, 0, 0.3);
        -webkit-transition: top 0.25s ease;
        transition: top 0.25s ease;
      }
    }
    .banner {
      width: 790px;
      margin-right: 10px;
      margin-top: 10px;
      float: left;
      height: 470px;
      display: flex;
      justify-content: space-between;
      .lunbo {
        width: 590px;
        height: 470px;
        overflow: hidden;
        position: relative;
        .lunbo_li {
          width: 590px;
          height: 470px;
          position: absolute;
          top: 0;
          left: 0;
          opacity: 0;
          transition: 1s;
          img {
            width: 590px;
            height: 100%;
            display: block;
          }
        }
        .show {
          opacity: 1;
        }
        .btnlist {
          width: 127px;
          height: 15px;
          z-index: 2;
          margin-left: 0 !important;
          left: 30px;
          bottom: 20px;
          position: absolute;

          .btnlist_li {
            width: 8px;
            height: 8px;
            margin-right: 4px;
            border: 1px solid rgba(0, 0, 0, 0.05);
            background: rgba(255, 255, 255, 0.4);
            border-radius: 5px;
            float: left;
          }
          .btnShow {
            width: 10px;
            height: 10px;
            margin-right: 4px;
            background: #fff;
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.4);
          }
        }

        a {
          width: 50px;
          height: 35px;
          line-height: 30px;
          background-color: #b4b4bf;
          outline: none;
          margin-top: -20px;
          font-size: 10px;
          z-index: 2;
          position: absolute;
          top: 50%;
          border: none;
          border-radius: 20px;
          color: rgba(255, 255, 255, 0.8);
          &:hover {
            background-color: #999;
          }
        }
        #left {
          left: -25px;
          span {
            position: absolute;
            left: 30px;
            top: 2px;
          }
        }
        #right {
          right: -25px;
          span {
            position: absolute;
            right: 30px;
            top: 2px;
          }
        }
      }

      .focus_change {
        width: 190px;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        .images {
          width: 190px;
          height: 150px;
          img {
            width: 190px;
            height: 100%;
          }
        }
      }
    }
    .detail {
      background: #fff;
      float: right;
      width: 190px;
      z-index: 1;
      height: calc(100% - 10px);
      margin-top: 10px;
      .first_part {
        display: flex;
        flex-direction: column;
        align-items: center;
        .first_top {
          width: 100%;
          height: 77px;
          font-size: 12px;
          display: flex;
          justify-content: center;
          align-items: center;

          img {
            width: 40px;
            height: 40px;
            border-radius: 20px;
            margin-right: 10px;
          }
          .font {
            display: flex;
            flex-direction: column;
          }
          p {
            margin-bottom: 5px;
            color: #666;
          }
        }
        .first_button {
          width: 100%;
          height: 25px;
          font-size: 12px;
          display: flex;
          justify-content: center;
          .new {
            width: 75px;
            height: 25px;
            border-radius: 13px;
            color: #fff;
            margin: 0 5px;
            background: #e1251b;
          }
          .member {
            width: 75px;
            height: 25px;
            border-radius: 13px;
            color: #e5d790;
            margin: 0 5px;
            background: #363634;
            &:hover {
              background: #e1251b;
              color: #fff;
            }
          }
        }
        .first_part::after {
          position: absolute;
          height: 1px;
          left: 15px;
          right: 15px;
          background: linear-gradient(270deg, white, #eeeeee, #eeeeee, white);
          content: " ";
          bottom: 0;
        }
      }
      .second_part {
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 130px;
        .second_top {
          width: 100%;
          height: 20px;
          margin-bottom: 8px;
          padding-top: 10px;
          display: flex;
          justify-content: space-between;
          h3 {
            width: 56px;
            height: 20px;
            font-weight: 700;
            font-size: 14px;
            color: #333;
            margin-left: 15px;
            line-height: 20px;
          }
          p {
            width: 40px;
            height: 21px;
            color: #999;
            font-size: 12px;
            margin-right: 15px;
            line-height: 21px;
          }
        }
        ul {
          width: 160px;
          height: 88px;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          font-size: 12px;

          li {
            display: flex;
            justify-content: space-between;
            width: 100%;
            height: 16px;
            margin-bottom: 6px;
            a {
              width: 35px;
              height: 100%;
              color: #e1251b;
              margin-right: 6px;
              background: rgba(225, 37, 27, 0.08);
              line-height: 16px;
              text-align: center;
            }
            p {
              width: 100%;
              color: #666;
              overflow: hidden;
              white-space: nowrap;
              text-overflow: ellipsis;
            }
          }
        }
      }
      .third_part {
        width: 100%;
        height: 240px;
        font-size: 12px;
        color: #666;
        padding: 5px 0.5px;
        li {
          width: 63px;
          height: 55px;
          text-align: center;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          float: left;
          cursor: pointer;
          .iconfont {
            display: block;
            width: 28px;
            height: 28px;
            font-size: 20px;
            font-weight: 900;
          }
          a {
            display: block;
            width: 100%;
            height: 27px;
            color: #333;
          }
        }
      }
    }
  }
}
</style>

