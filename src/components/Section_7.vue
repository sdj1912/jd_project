<template>
  <section class="section_7 louceng">
    <div class="header">
      <h3>为你推荐</h3>
    </div>
    <div class="content">
      <div class="title">
        <ul class="title_item">
          <li class="item_li">
            <button>精选</button>
            <span class="first_color">猜你喜欢</span>
          </li>
          <li class="item_li">
            <p class="other">智能先锋</p>
            <span class="color">猜你喜欢</span>
          </li>
          <li class="item_li">
            <p class="other">居家优品</p>
            <span class="color">猜你喜欢</span>
          </li>
          <li class="item_li">
            <p class="other">超市百货</p>
            <span class="color">猜你喜欢</span>
          </li>
          <li class="item_li">
            <p class="other">时尚达人</p>
            <span class="color">猜你喜欢</span>
          </li>
          <li class="item_li">
            <p class="other">进口好物</p>
            <span class="color">猜你喜欢</span>
          </li>
        </ul>
      </div>
    </div>
    <ul class="main">
      <li
        class="main_li"
        v-for="(item,index) in goodsList"
        :key="index"
        @click="goTodetail(item.id)"
      >
        <div class="pictrue">
          <img :src="item.goodsImg[0]" alt>
        </div>
        <div class="wrap">
          <p class="description">{{ item.goodsName }}</p>
        </div>
        <div class="last">
          <p>
            ￥
            <span>{{ item.currentPrice.toFixed(2) }}</span>
          </p>
          <div class="quan" v-if="item.status==1">自营</div>
          <div class="quan" v-if="item.status==2">热卖</div>
          <div class="quan" v-if="item.status==3">新品</div>
        </div>
      </li>
    </ul>
  </section>
</template>


<script>
import axios from "axios";
export default {
  data() {
    return {
      goodsList: []
    };
  },
  mounted() {
    this.getGoodsList();
  },
  methods: {
    getGoodsList() {
      let _this = this;
      axios
        .get("http://118.24.239.63:3000/goods")
        .then(function(response) {
          if (response.data.status == 0) {
            _this.goodsList = response.data.list;
          }
        })
        .catch(function(error) {
          console.log(error);
        });
    },
    goTodetail(id) {
      this.$router.push(`/detail?id=${id}`);
    }
  }
};
// import axios from "axios";
// export default {
//   data() {
//     return {
//       goodsList: []
//     };
//   },
//   mounted() {
//     this.getGoodList();
//   },
//   methods: {
//     getGoodList() {
//       let _this = this;
//       axios
//         .get("http://118.24.239.63:3000/goods")
//         .then(function(response) {
//           if (response.data.status == 0) {
//             _this.goodsList = response.data.result.list;
//           }
//         })
//         .catch(function(error) {
//           console.log(error);
//         });
//     },
//     goTodetail(id) {
//       this.$router.push(`/detail?id=${id}`);
//     }
//   }
// };
</script>

<style lang="scss" scoped>
.section_7 {
  width: 1190px;
  margin-top: 20px;
  margin: 20px auto 0;
  .header {
    height: 45px;
    margin-bottom: 20px;
    h3 {
      text-align: center;
      line-height: 45px;
      font-size: 28px;
      font-weight: 700;
      text-align: center;
      color: rgb(51, 51, 51);
      &::before {
        content: "";
        width: 25px;
        height: 20px;
        display: inline-block;
        background: url(../assets/images/sprite@2x.png) no-repeat;
        background-size: 200% 100%;
        margin-right: 30px;
      }
      &::after {
        content: "";
        width: 25px;
        height: 20px;
        display: inline-block;
        background: url(../assets/images/sprite@2x.png) no-repeat right center;
        background-size: 200% 100%;
        margin-left: 30px;
      }
    }
  }
  .content {
    width: 1190px;
    background: #ddd;
    .title {
      width: 1190px;
      height: 60px;
      background: #e1251b;

      .title_item {
        width: 1190px;
        height: 100%;
        background: #fff;
        display: flex;
        justify-content: space-around;
        align-items: center;
        .item_li {
          width: 150px;
          display: flex;
          flex-direction: column;
          align-items: center;
          button {
            background: #e1251b;
            color: #fff;
            width: 70px;
            height: 27px;
            display: inline-block;
            border-radius: 50px;
            padding: 0 5px;
            text-align: center;
            font-size: 16px;
            margin-bottom: 3px;
          }
          span {
            display: block;
            width: 150px;
            height: 21px;
            font-size: 14px;
            text-align: center;
          }
          .first_color {
            color: #e1251b;
          }
          .color {
            color: #999;
          }
          .other {
            color: #333;
            margin-top: 7px;
            font-size: 16px;
            font-weight: 700;
            line-height: 27px;
            height: 27px;
          }
        }
        &:hover {
          color: #e1251b;
        }
      }
    }
  }
  .main {
    width: 1190px;
    background: #f4f4f4;
    overflow: hidden;
    .main_li {
      position: relative;
      float: left;
      width: 230px;
      height: 322px;
      margin: 0 4px 10px;
      background: #fff;
      display: flex;
      flex-direction: column;
      .pictrue {
        width: 150px;
        height: 150px;
        margin: 30px auto 40px;
        img {
          display: block;
          width: auto;
          height: auto;
          max-width: 100%;
          max-height: 100%;
          margin: 0 auto;
        }
      }
      .wrap {
        width: 230px;
        height: 65px;
        padding: 0 20px;
        .description {
          width: 190px;
          height: 48px;
          font-size: 14px;
          line-height: 24px;
          text-align: left;
          color: #666;
          word-break: break-all;
          overflow: hidden;
          text-overflow: ellipsis;
          display: -webkit-box;
          -webkit-line-clamp: 2;
          -webkit-box-orient: vertical;
        }
      }
      .last {
        width: 190px;
        padding: 0 20px;
        background: #fff;
        color: #e1251b;
        p {
          font-size: 16px;
          float: left;
          span {
            font-weight: 700;
          }
        }
        .quan {
          text-align: center;
          width: 30px;
          font-size: 12px;
          float: right;
          border: 1px solid #e1251b;
        }
      }
    }
  }
}
</style>

