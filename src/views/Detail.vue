<template>
  <div class="detail">
    <Top></Top>
    <div class="wrap">
      <div class="wrap_content">
        <div class="logo_title">
          <div class="logo">
            <div class="list">
              <p>全部分类</p>
              <span class="iconfont icon--xiangxiajiantou"></span>
            </div>
          </div>
        </div>
        <div class="search">
          <input type="text">
          <button class="button_1">搜全站</button>
          <button class="button_2">搜本店</button>
        </div>
        <div class="settle">
          <span class="iconfont icon-icon22fuzhi"></span>
          <p class="shopping_car">
            我的购物车
            <span>></span>
          </p>
        </div>
      </div>
    </div>
    <div class="content">
      <div class="content_center">
        <div class="imginfo">
          <img class="spic" :src="detailInfo.goodsImg[0]" alt>
          <div class="imglist">
            <span class="zuo">&lt;</span>
            <ul>
              <li class="list_img" v-for="(item,index) in detailInfo.goodsImg" :key="index">
                <img :src="item" alt>
              </li>
            </ul>
            <span class="you">&gt;</span>
          </div>
          <div class="share">
            <div class="left-btns">
              <div class="part">
                <span class="iconfont icon-weibiaoti-icon-"></span>
                <em>关注</em>
              </div>
              <div class="part">
                <span class="iconfont icon-fenxiang"></span>
                <em>分享</em>
              </div>
            </div>
            <div class="right-btns">举报</div>
          </div>
          <div class="button_wrap">
            <button>企业购更优惠</button>
          </div>
        </div>
        <div class="main">
          <h2>{{ detailInfo.goodsName }}</h2>
          <div class="news">鼻敏感保湿纸40抽，特价秒杀，主图两种包装交替发货！</div>
          <div class="sale">
            <div class="sale_left">
              <span class="iconfont icon-clock"></span>
              <p>京东秒杀</p>
            </div>
            <div class="sale_right">
              <p>距离结束</p>
              <span>07</span>:
              <span>10</span>:
              <span>59</span>
            </div>
          </div>
          <div class="summary">
            <div class="price_wrap">
              <div class="sale_price">
                <div class="dt">秒 杀 价</div>
                <div class="dd">
                  <div class="p-price">
                    <span class="symbol">￥</span>
                    <span class="number">{{ detailInfo.currentPrice}}</span>
                  </div>
                  <div class="pricing" v-if="detailInfo.currentPrice!=detailInfo.originalPrice">
                    [
                    <span class="page_origin_price">￥{{ detailInfo.originalPrice}}</span>]
                  </div>
                  <div class="notice">降价通知</div>
                  <div class="summary-info">
                    <div class="item">
                      <p class="comment">累计评价</p>
                      <span class="count">1200+</span>
                    </div>
                  </div>
                </div>
              </div>
              <div class="summary-quan">
                <div class="summary-quan-dt">优 惠 券</div>
                <div class="dd">
                  <dl>
                    <dt class="fl"></dt>
                    <dd class="lh">
                      <a class="J-open-tb" href="#none">
                        <span class="quan-item" title="仅可购买优普爱纸品湿巾专营店商品 有效期2020-01-13至2020-01-31">
                          <s></s>
                          <b></b>
                          <span class="text">满59减5</span>
                        </span>
                        <span class="quan-item" title="仅可购买优普爱纸品湿巾专营店商品 有效期2020-01-13至2020-01-31">
                          <s></s>
                          <b></b>
                          <span class="text">满119减15</span>
                        </span>
                        <span class="quan-item" title="仅可购买优普爱纸品湿巾专营店商品 有效期2020-01-13至2020-01-31">
                          <s></s>
                          <b></b>
                          <span class="text">满199减30</span>
                        </span>
                        <span class="more-btn">更多&gt;&gt;</span>
                      </a>
                    </dd>
                  </dl>
                </div>
              </div>
              <div class="summary_bottom">
                <div class="summary_promotion">
                  <div class="promote_sales">
                    促
                    <span></span>销
                  </div>
                  <div class="p-promotions-wrap">
                    <div class="p-promotions">
                      <em class="hl_red_bg">限购</em>
                      <em class="hl_red">该商品购买1-10件时享受单件价￥9.90，超出数量以结算价为准，仅限购买一次</em>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="p-choose-wrap">
            <div class="summary-stock">
              <div class="dt">配 送 至</div>
              <div class="dd">
                <div class="store-clearfix">
                  <div class="stock-address">
                    <div class="ui-area-wrap">
                      <div class="ui-area-text-wrap">浙江杭州市萧山区戴村镇</div>
                      <div class="iconfont_wrap">
                        <span class="iconfont icon--xiangxiajiantou"></span>
                      </div>
                    </div>
                  </div>
                  <div class="youhuo">有货</div>
                  <div class="services">
                    <div class="zhichi">支持</div>
                    <div class="tuikuan">
                      闪电退款
                      <span>|</span>
                      极速审核
                    </div>
                  </div>
                  <div class="dcashDesc">
                    <p>在线支付免运费</p>
                    <span class="iconfont icon-wenhao"></span>
                  </div>
                </div>
              </div>
            </div>
            <div class="summary-supply">
              <div class="dd">
                <div class="summary-service">
                  <p>
                    由
                    <span>优普爱纸品湿巾专营店</span>从 辽宁大连市 发货, 并提供售后服务. 受春节影响1月18日至2月2日的商品发货时效较长，预计2月4日前发货，大件定制等特殊商品以店铺咨询为准
                  </p>
                </div>
              </div>
            </div>
            <div class="summary-line"></div>
            <div class="choose-attrs">
              <div id="choose-attr-1" class="li p-choose" data-type="产品" data-idx="0">
                <div class="dt">选择产品</div>
                <div class="dd">
                  <div
                    class="item"
                    data-sku="23697064057"
                    data-value="5°装 120抽*3包"
                    title="5°装 120抽*3包"
                  >
                    <b></b>
                    <a href="#none" clstag="shangpin|keycount|product|yanse-5°装 120抽*3包">
                      <img
                        data-img="1"
                        src="//img12.360buyimg.com/n9/s40x40_jfs/t18370/309/979685183/240830/1ae96aaf/5ab48490N7fdcf705.jpg"
                        width="40"
                        height="40"
                        alt="5°装 120抽*3包"
                      >
                      <i>5°装 120抽*3包</i>
                    </a>
                  </div>
                  <div
                    class="item"
                    data-sku="23697467130"
                    data-value="7°装 120抽*3包"
                    title="7°装 120抽*3包"
                  >
                    <b></b>
                    <a href="#none" clstag="shangpin|keycount|product|yanse-7°装 120抽*3包">
                      <img
                        data-img="1"
                        src="//img10.360buyimg.com/n9/s40x40_jfs/t19201/239/990674429/257789/5e22d7b2/5ab484a7Ncb739b26.jpg"
                        width="40"
                        height="40"
                        alt="7°装 120抽*3包"
                      >
                      <i>7°装 120抽*3包</i>
                    </a>
                  </div>
                  <div
                    class="item selected"
                    data-sku="26964817791"
                    data-value="便携装 40抽*6包"
                    title="便携装 40抽*6包"
                  >
                    <b></b>
                    <a href="#none" clstag="shangpin|keycount|product|yanse-便携装 40抽*6包">
                      <img
                        data-img="1"
                        src="//img11.360buyimg.com/n9/s40x40_jfs/t1/57799/14/6359/64211/5d40df69E27393f5d/b19760d235c88579.jpg"
                        width="40"
                        height="40"
                        alt="便携装 40抽*6包"
                      >
                      <i>便携装 40抽*6包</i>
                    </a>
                  </div>
                  <div
                    class="item"
                    data-sku="27096267104"
                    data-value="便携装 50抽*20包"
                    title="便携装 50抽*20包"
                  >
                    <b></b>
                    <a href="#none" clstag="shangpin|keycount|product|yanse-便携装 50抽*20包">
                      <img
                        data-img="1"
                        src="//img14.360buyimg.com/n9/s40x40_jfs/t1/91922/9/4841/79751/5de9fe93E4db305ce/dc2e95e87255c69e.jpg"
                        width="40"
                        height="40"
                        alt="便携装 50抽*20包"
                      >
                      <i>便携装 50抽*20包</i>
                    </a>
                  </div>
                  <div
                    class="item"
                    data-sku="56001008153"
                    data-value="便携装 40抽*14包"
                    title="便携装 40抽*14包"
                  >
                    <b></b>
                    <a href="#none" clstag="shangpin|keycount|product|yanse-便携装 40抽*14包">
                      <img
                        data-img="1"
                        src="//img13.360buyimg.com/n9/s40x40_jfs/t1/73394/4/8930/73505/5d6cd286Ed0ee8d05/26c3d15aa26a295b.jpg"
                        width="40"
                        height="40"
                        alt="便携装 40抽*14包"
                      >
                      <i>便携装 40抽*14包</i>
                    </a>
                  </div>
                </div>
              </div>
            </div>
            <div class="summary-line"></div>
            <div class="choose-btns">
              <div class="choose-amount"></div>
              <div class="wrap-input">
                <input type="text" class="buy-num" value="1">
                <span class="btn-reduce disabled">-</span>
                <span class="btn-add">+</span>
              </div>
              <div class="btn-lg">加入购物车</div>
            </div>
            <div class="summary-tips">
                <div class="dt">温馨提示</div>
                <div class="dd">
                  <ol class="tips-list clearfix">
                    <li class="local-txt">·支持7天无理由退货</li>
                    <li class="local-txt">·此商品不可使用全品类券</li>
                  </ol>
                </div>
              </div>
          </div>
        </div>
        <div class="right">
          <div class="track-tit">
            <h3>看了又看</h3>
            <span></span>
          </div>
          <div class="track-con">
            <ul>
              <li>
                <img src="../assets/images/paper.jpg" alt="">
                <div>优普爱 oupai 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 鼻敏感面巾抽纸 5°装 120抽*3包</div>
                <p>￥27.70</p>
              </li>
              <li>
                <img src="../assets/images/paper1.jpg" alt="">
                <div>优普爱 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 鼻敏感面巾抽纸 6°装 120抽*3包</div>
                <p>￥29.00</p>
              </li>
               <li>
                <img src="../assets/images/paper2.jpg" alt="">
                <div>优普爱 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 便携装 10抽*25包</div>
                <p>￥36.60</p>
              </li>
             <!--<li>
                <img src="../assets/images/paper3.jpg" alt="">
                <div>优普爱 oupai 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 鼻敏感面巾抽纸 5°装 120抽*3包</div>
                <p>￥27.70</p>
              </li>
               <li>
                <img src="../assets/images/paper4.jpg" alt="">
                <div>优普爱 oupai 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 鼻敏感面巾抽纸 5°装 120抽*3包</div>
                <p>￥27.70</p>
              </li>
              <li>
                <img src="../assets/images/paper5.jpg" alt="">
                <div>优普爱 oupai 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 鼻敏感面巾抽纸 5°装 120抽*3包</div>
                <p>￥27.70</p>
              </li>
              <li>
                <img src="../assets/images/paper6.jpg" alt="">
                <div>优普爱 oupai 保湿纸 柔嫩触感 亲和肌肤 婴儿可用 鼻敏感面巾抽纸 5°装 120抽*3包</div>
                <p>￥27.70</p>
              </li> -->
            </ul>
          </div>
          <div class="track-more">
            <span class="iconfont icon-up"></span>
            <span class="iconfont icon-up1"></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Top from "../components/Top";
import axios from 'axios';
export default {
  components: {
    Top
  },
  data() {
    return {
      id: '',
      detailInfo: {}
    }
  },
  mounted() {
    this.id = this.$route.query.id
    let _this = this;
      axios
        .get(`http://118.24.239.63:3000/goods/detail?id=${_this.id}`)
        .then(function(response) {
          if (response.data.status == 0) {
            _this.detailInfo = response.data.result;
            console.log(_this.detailInfo)
          }
        })
        .catch(function(error) {
          console.log(error);
        });
  }
};
</script>


<style lang="scss" scoped>
.wrap {
  width: 100%;
  .wrap_content {
    width: 1210px;
    height: 100px;
    margin: 0 auto;
    .logo_title {
      width: 362px;
      float: left;
      position: relative;
      height: 60px;
      padding: 20px 0;
      .logo {
        display: block;
        width: 270px;
        height: 60px;
        background: url(../assets/images/logo.png) no-repeat left 0;
        float: left;
        .list {
          float: right;
          color: #ccc;
          position: relative;
          width: 78px;
          height: 25px;
          border: 1px solid #ccc;
          line-height: 25px;
          z-index: 1;
          background: #fff;
          padding: 0 5px;
          margin-top: 18px;
          p {
            float: left;
          }
          span {
            float: right;
          }
        }
      }
    }
    .search {
      position: relative;
      float: left;
      width: 560px;
      margin-top: 20px;
      background: plum;
      height: 40px;
      input {
        height: 40px;
        float: left;
        width: 456px;
        line-height: 24px;
        color: #666;
        padding: 4px;
        margin-bottom: 4px;
        border-width: 2px 0 2px 2px;
        border-color: #b61d1d;
        border-style: solid;
        outline: 0;
        font-size: 14px;
      }
      button {
        width: auto;
        padding: 0 8px;
        font: 12px;
        overflow: visible;
      }
      .button_1 {
        float: left;
        height: 40px;
        background: #b61d1d;
        border: none;
        border-radius: 0;
        color: #fff;
        cursor: pointer;
      }
      .button_2 {
        float: left;
        height: 40px;
        border: none;
        border-radius: 0;
        background: #474e5c;
        color: #fff;
        cursor: pointer;
      }
    }
    .settle {
      width: 141px;
      position: relative;
      margin-right: 65px;
      float: right;
      height: 36px;
      margin-top: 25px;
      background: red;
      background: #f9f9f9;
      border: 1px solid #dfdfdf;
      line-height: 36px;
      .icon-icon22fuzhi {
        color: #b61d1d;
        float: left;
        margin-left: 20px;
      }
      .shopping_car {
        color: #666;
        margin-left: 45px;
      }
      span {
        margin-left: 15px;
      }
    }
  }
}
.content {
  width: 100%;
  .content_center {
    width: 1210px;
    height: 643px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    .imginfo {
      width: 352px;
      height: 537px;
      background: #fff;
      .spic {
        width: 352px;
        height: 352px;
        margin-bottom: 20px;
        border: 1px solid #999;
      }
      .imglist {
        width: 352px;
        height: 54px;
        background: #fff;
        margin-bottom: 20px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        ul {
          width: 290px;
          height: 54px;
          overflow: hidden;
          .list_img {
            width: 54px;
            height: 54px;
            float: left;
            margin: 0 2px;

            img {
              width: 100%;
              height: 100%;
            }
          }
        }
        span {
          font-size: 32px;
        }
      }
      .share {
        width: 352px;
        height: 20px;
        .left-btns {
          width: 95px;
          height: 18px;
          float: left;
          display: flex;

          .part {
            cursor: pointer;
            margin-right: 3px;
            color: #666;
            span {
              width: 14px;
              height: 13px;
              margin-right: 3px;
              color: #b61d1d;
            }
          }
        }
        .right-btns {
          float: right;
          width: 24px;
          height: 18px;
          line-height: 18px;
          font-size: 12px;
        }
      }
      .button_wrap {
        width: 352px;
        height: 58px;
        padding-top: 30px;
        background: #fff;
        text-align: center;
        button {
          display: inline-block;
          line-height: 26px;
          padding: 0 16px;
          border: 1px solid #ccc;
          color: #666;
        }
      }
    }
    .main {
      width: 590px;
      height: 600px;

      h2 {
        font-size: 16px;
        font-weight: 700;
        color: #666;
        padding-top: 10px;
        line-height: 28px;
        margin-bottom: 5px;
      }
      .news {
        margin-bottom: 5px;
        width: 590px;
        color: #e4393c;
        line-height: 1.5em;
      }
      .sale {
        height: 32px;
        line-height: 32px;
        padding: 0 10px;
        overflow: hidden;
        background-color: #fe0851;
        .sale_left {
          width: 93px;
          height: 34px;
          float: left;
          span {
            float: left;
            font-size: 20px;
            vertical-align: -4px;
            margin-right: 5px;
            color: #fff;
          }
          p {
            float: left;
            font-size: 16px;
            color: #fff;
            font-weight: 400;
          }
        }
        .sale_right {
          width: 145px;
          height: 32px;
          float: right;
          p {
            color: #fbe2e2;
            font-size: 12px;
            float: left;
          }
          span {
            font-size: 14px;
            color: #fff;
            width: 22px;
            background: #443b3b;
            margin: 0 4px;
          }
        }
      }
      .summary {
        width: 590px;
        height: 144px;
        padding-bottom: 5px;
        .price_wrap {
          width: 590px;
          height: 139px;
          padding-top: 10px;
          background: #f3f3f3;
          .sale_price {
            width: 590px;
            height: 22px;
            .dt {
              width: 54px;
              height: 22px;
              float: left;
              padding-left: 10px;
              font-family: simsun;
              color: #999;
              line-height: 22px;
            }
            .dd {
              width: 520px;
              height: 22px;
              margin-left: 70px;
              .p-price {
                color: #e4393c;
                margin-right: 10px;
                float: left;
                .symbol {
                  font-size: 16px;
                }
                .number {
                  font-size: 22px;
                }
              }
              .pricing {
                width: 52px;
                height: 14px;
                float: left;
                line-height: 23px;
                margin-right: 5px;
                .page_origin_price {
                  font-size: 12px;
                  color: #666;
                  text-decoration: line-through;
                }
              }
              .notice {
                color: #005aa0;
                vertical-align: 2px;
                float: left;
                line-height: 20px;
              }
              .summary-info {
                float: right;
                width: 73px;
                height: 32px;
                margin-right: 10px;
                margin-top: 8px;
                color: #999;
                .item {
                  border-left: solid 1px #e6e6e6;
                  text-align: center;
                  padding: 0 10px;
                  line-height: 15px;
                  .comment {
                    color: #999;
                  }
                  .count {
                    font: 14px;
                    color: #005ea7;
                    margin-left: 5px;
                  }
                }
              }
            }
          }
          .summary-quan {
            width: 590px;
            height: 34px;
            display: flex;
            .summary-quan-dt {
              width: 54px;
              height: 32px;
              line-height: 32px;
              padding-left: 10px;
              color: #999;
              font-family: simsun;
              padding-bottom: 2px;
            }
            .dd {
              width: 460px;
              height: 26px;
              padding-top: 8px;
              margin-left: 20px;
              .fl {
                float: left;
              }
              .lh {
                width: 520px;
                height: 18px;
                .quan-item {
                  position: relative;
                  float: left;
                  height: 16px;
                  padding-left: 2px;
                  line-height: 15px;
                  text-align: center;
                  border-top: 1px solid #df3033;
                  border-bottom: 1px solid #df3033;
                  background: #ffdedf;
                  font-size: 14px;
                  white-space: nowrap;
                  margin-right: 13px;
                  cursor: pointer;
                }
                .more-btn {
                  font-family: SimSun;
                  color: #999;
                  position: relative;
                  float: left;
                  height: 16px;
                  line-height: 18px;
                  cursor: pointer;
                }
              }
            }
          }
          .summary_bottom {
            width: 590px;
            height: 65px;
            .summary_promotion {
              width: 590px;
              height: 65px;
              background: url(../assets/images/price-bg.png) 0 -12px repeat-x #efefef;
              padding-bottom: 5px;
              .promote_sales {
                line-height: 30px;
                float: left;
                padding-left: 10px;
                color: #999;
                font-family: simsun;
                span {
                  display: inline-block;
                  width: 17px;
                  height: 100%;
                }
              }
              .p-promotions-wrap {
                width: 520px;
                height: 60px;
                margin-left: 70px;
                .p-promotions {
                  line-height: 30px;
                  padding-right: 90px;
                  min-height: 35px;
                  .hl_red_bg {
                    width: 32px;
                    height: 22px;
                    border: 1px solid #df3033;
                    font-size: 13px;
                    color: #df3033;
                    margin-right: 10px;
                    line-height: 16px;
                  }
                  .hl_red {
                    color: #666;
                    line-height: 18px;
                    font-weight: normal;
                  }
                }
              }
            }
          }
        }
      }
      .p-choose-wrap {
        width: 590px;
        height: 316px;
        position: relative;
        .summary-stock {
          width: 590px;
          height: 26px;
          .dt {
            float: left;
            padding-left: 10px;
            font-family: simsun;
            color: #999;
            line-height: 24px;
          }
          .dd {
            width: 520px;
            height: 26px;
            margin-left: 70px;
            .store-clearfix {
              width: 520px;
              height: 26px;
              margin-bottom: 5px;
              .stock-address {
                width: 168px;
                height: 26px;
                float: left;
                margin-left: -5px;
                .ui-area-wrap {
                  height: 26px;
                  margin-right: 6px;
                  border: 1px solid #cecbce;
                  padding: 0 24px 0 4px;
                  position: relative;
                  .ui-area-text-wrap {
                    float: left;
                    font-size: 12px;
                    height: 24px;
                    background: #ccc;
                    line-height: 23px;
                  }
                  .iconfont_wrap {
                    padding: 3px 4px;
                    background: #fff;
                    position: absolute;
                    top: 0;
                    right: 0;
                    span {
                      display: inline-block;
                      width: 17px;
                      height: 17px;
                      line-height: 17px;
                      text-align: center;
                    }
                  }
                }
              }
              .youhuo {
                margin-left: 5px;
                line-height: 24px;
                margin-right: 5px;
                float: left;
                font-size: 12px;
                color: #999;
              }
              .services {
                width: 162px;
                height: 24px;
                float: left;
                .zhichi {
                  margin-left: 5px;
                  line-height: 24px;
                  margin-right: 5px;
                  float: left;
                  font-size: 12px;
                  color: #999;
                }
                .tuikuan {
                  width: 146px;
                  padding: 0 10px;
                  font-size: 12px;
                  margin-left: 5px;
                  line-height: 24px;
                  margin-right: 5px;
                  color: blue;
                }
              }
              .dcashDesc {
                width: 104px;
                height: 19px;
                float: left;
                margin-top: 3px;
                margin-left: -15px;
                p {
                  float: left;
                  line-height: 19px;
                }
                span {
                  float: right;
                }
              }
            }
          }
        }
        .summary-supply {
          width: 590px;
          height: 64px;
          .dd {
            width: 520px;
            height: 64px;
            margin-left: 70px;
            .summary-service {
              p {
                color: #999;
                line-height: 32px;
                span {
                  color: #e4393c;
                  margin: 0 5px;
                }
              }
            }
          }
        }
        .summary-line {
          height: 0;
          overflow: hidden;
          border-bottom: 1px dotted #dfdfdf;
          margin-bottom: 15px;
        }
        .choose-attrs {
          overflow: hidden;
          #choose-attr-1 {
            line-height: 40px;
          }
          .li {
            margin-bottom: 3px;
            line-height: 32px;
            display: block;
            .dt {
              float: left;
              padding-left: 10px;
              font-family: simsun;
              color: #999;
            }
            .dd {
              margin-left: 70px;
              .item {
                background-color: #f7f7f7;
                float: left;
                color: #666;
                margin-right: 7px;
                margin-bottom: 4px;
                position: relative;
                b {
                  font-weight: bold;
                }
                a {
                  height: 42px;
                  border: 1px solid #ccc;
                  display: block;
                  white-space: nowrap;
                  color: #666;
                  img {
                    width: 40px;
                    height: 40px;
                  }
                  i {
                    padding: 0 8px;
                    font-size: 12px;
                    vertical-align: top;
                  }
                }
              }
            }
          }
        }
        .choose-btns {
          width: 590px;
          height: 46px;
          margin-top: 10px;
          margin-bottom: 20px;
          padding: 0 10px;
          .choose-amount {
            width: 58px;
            height: 44px;
            overflow: hidden;
            border: 1px solid #ccc;
            position: relative;
            margin-right: 10px;
            float: left;
          }
          .wrap-input {
            float: left;
            input {
              display: block;
              width: 43px;
              height: 42px;
              line-height: 42px;
              position: absolute;
              top: 215px;
              left: 11px;
              border: 0;
              text-align: center;
            }
            span {
              display: block;
              width: 15px;
              text-align: center;
              height: 22px;
              line-height: 22px;
              overflow: hidden;
              background: #f1f1f1;
              color: #666;
              position: absolute;
              left: 52px;
              border: 1px solid #ccc;
              border-right: 0;
            }
            .disabled {
              color: #ccc;
              cursor: not-allowed;
            }
            .btn-reduce {
              bottom: 59px;
              border-bottom: 0;
            }
            .btn-add {
              top: 215px;
              border-top: 0;
            }
          }
          .btn-lg {
            width: 142px;
            height: 46px;
            line-height: 46px;
            padding: 0 26px;
            font-size: 18px;
            font-weight: 700;
            background-color: #df3033;
            color: #fff;
            text-align: center;
            vertical-align: middle;
            cursor: pointer;
            float: left;
          }
        }
        .summary-tips {
          margin-bottom: 5px;
          .dt {
            float: left;
            padding-left: 10px;
            font-family: simsun;
            color: #999;
          }
          .dd {
            margin-left: 70px;
            .tips-list {
              li {
                float: left;
                margin-right: 15px;
                font-family: simsun;
                color: #999;
              }
            }
          }
        }
      }
    }
    .right {
      width: 210px;
      height: 600px;
      .track-tit {
        height:50px;
        position: relative;
        line-height: 50px;
        font-size: 12px;
        color: #666;
        font-weight: 400;
        text-align: center;
         h3 {
          position: relative;
          z-index: 2;
          display: inline-block;
          background: #fff;
          padding: 0 25px;
        }
        span {
          position: absolute;
          z-index: 1;
          left: 0;
          right: 0;
          top: 25px;
          height: 1px;
          background: #f2f2f2;
        }
      }
      .track-con {
        position: relative;
        width: 150px;
        height: 564px;
        overflow: hidden;
        margin: 0 auto;
         ul {
          position: absolute;
          width: 150px;
          height: 2820px;
          top: 0px;
          left: 0px;
          li {
            float: left;
            position: relative;
            padding: 10px 0;
            div {
              overflow: hidden;
              text-overflow: ellipsis;
              white-space: nowrap;
              position: absolute;
              left: 0;
              right: 0;
              top: 126px;
              line-height: 12px;
              background: rgba(255,255,255,.9);
              padding: 6px;
            }
            p {
              line-height: 18px;
              color: #C81623;
              text-align: center;
            }
          }
         }
      }
      .track-more {
        padding-top: 10px;
        text-align: center;
        clear: both;
        span {
          margin: 0 10px;
          text-indent: -9999px;
          font-size: 30px;
          color:#ccc;
        }
      } 
    }
  }
}
</style>


