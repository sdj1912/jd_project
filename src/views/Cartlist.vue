<template>
  <div class="cartlist">
    <Top></Top>
    <div class="header">
      <div class="logo-2014">
        <div class="logo"></div>
        <div class="link2">购物车</div>
      </div>
      <div class="cart-search">
        <form>
          <input type="text" class="itxt" placeholder="自营">
          <input type="button" class="button" value="搜索">
        </form>
      </div>
    </div>
    <div class="cart-filter-bar">
      <div class="switch-cart">
        <em>全部商品</em>
        <span class="number">4</span>
      </div>
      <div class="cart-store">
        <p class="label">配送至：</p>
        <div class="ui-area-wrap">
          <div class="ui-area-text-wrap">浙江杭州市萧山区戴村镇</div>
          <div class="iconfont_wrap">
            <span class="iconfont icon--xiangxiajiantou"></span>
          </div>
        </div>
      </div>
      <div class="clr"></div>
      <div class="w-line">
        <div class="floater"></div>
      </div>
    </div>
    <div class="cart-warp">
      <div class="w">
        <div class="jd-cart">
          <div class="cart-thead">
            <div class="column t-checkbox">
              <div class="cart-checkbox">
                <input
                  type="checkbox"
                  name="toggle-checkboxes"
                  class="jdcheckbox"
                  clstag="clickcart|keycount|xincart|cart_allCheck"
                >
                <label for>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;全选</label>
              </div>
            </div>
            <div class="column t-goods">商品</div>
            <div class="column t-props"></div>
            <div class="column t-price">单价</div>
            <div class="column t-quantity">数量</div>
            <div class="column t-sum">小计</div>
            <div class="column t-action">操作</div>
          </div>
          <div class="cart-item-list">
            <div class="shop">
              <div class="cart-checkbox">
                <input type="checkbox" checked="checked" class="jdcheckbox">
                <label for></label>
              </div>
              <span class="shop-txt">
                <p class="shop-name">至诚川供生鲜专营店</p>
                <span class="iconfont icon-lianxikefu"></span>
              </span>
            </div>
            <div class="item-list" v-for="(item, index) in cartList" :key="index">
              <div class="item-single">
                <div class="item-form">
                  <div class="p-checkbox">
                    <div class="cart-checkbox">
                      <!--单品-->
                      <input
                        p-type="59764684496_1"
                        type="checkbox"
                        name="checkItem"
                        value="59764684496_1"
                        data-bind="cbid"
                        class="jdcheckbox"
                        clstag="clickcart|keycount|xincart|cart_checkOn_sku"
                      >
                      <label for>勾选商品</label>
                      <span class="line-circle"></span>
                    </div>
                  </div>
                  <div class="p-goods">
                    <div class="goods-item">
                      <div class="p-img">
                        <a
                          href="//item.jd.com/59764684496.html"
                          target="_blank"
                          class="J_zyyhq_59764684496"
                          pnc="false"
                          pncs
                        >
                          <img
                            alt="至诚 猕猴桃奇异果水果 24粒装单果70-90g精品果 新鲜水果"
                            clstag="clickcart|keycount|xincart|cart_sku_pic"
                            :src="item.goodsImg"
                          >
                        </a>
                      </div>
                      <div class="item-msg">
                        <div class="p-name">
                          <a
                            clstag="clickcart|keycount|xincart|cart_sku_name"
                            href="//item.jd.com/59764684496.html"
                            target="_blank"
                          >
                            <em class="fresh-icon"></em> {{ item.goodsName }}
                          </a>
                        </div>
                        <div class="p-extend p-extend-new">
                          <span
                            class="promise"
                            _yanbao="yanbao_59764684496_"
                            _service="service_59764684496_"
                            isproduct="1"
                            style="display:none"
                          ></span>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="p-props p-props-new">
                    <div class="props-txt" title="24粒装单果70-90g精品果">24粒装单果70-90g精品果</div>
                    <div class="props-txt" title="新鲜水果" t="${product.mainSku.sizeDesc}">新鲜水果</div>
                  </div>
                  <div class="p-price p-price-new">
                    <p class="plus-switch">
                      <strong>￥{{ item.currentPrice }}</strong>
                    </p>
                    <div>
                      <div class="clr"></div>
                    </div>
                    <p class="mt5" jj></p>
                    <p class="mt5" bt></p>
                  </div>
                  <div class="p-quantity">
                    <!--单品-->
                    <div class="quantity-form">
                      <a
                        href="javascript:void(0);"
                        clstag="clickcart|keycount|xincart|cart_num_down"
                        class="decrement disabled"
                        id="decrement_790629_59764684496_1_1"
                      >-</a>
                      <input
                        autocomplete="off"
                        type="text"
                        class="itxt"
                        :value="item.goodsCount"
                        id="changeQuantity_790629_59764684496_1_1_0"
                        minnum="1"
                      >
                      <a
                        href="javascript:void(0);"
                        clstag="clickcart|keycount|xincart|cart_num_up"
                        class="increment"
                        id="increment_790629_59764684496_1_1_0"
                      >+</a>
                    </div>
                    <div class="ac ftx-03 quantity-txt" _stock="stock_59764684496">有货</div>
                  </div>
                  <div class="p-sum">
                    <strong>¥{{item.currentPrice * item.goodsCount}}</strong>
                  </div>
                  <div class="p-ops">
                    <!--单品-->
                    <a
                      id="remove_790629_59764684496_1"
                      clstag="clickcart|keycount|xincart|cart_sku_del"
                      data-name="至诚 猕猴桃奇异果水果 24粒装单果70-90g精..."
                      data-more="removed_23.90_1"
                      class="cart-remove"
                      href="javascript:void(0);"
                      ob="false"
                    >删除</a>
                    <a
                      href="javascript:void(0);"
                      class="cart-follow"
                      id="follow_790629_59764684496_1"
                      clstag="clickcart|keycount|xincart|cart_sku_guanzhu"
                      ob="false"
                    >移到我的关注</a>
                  </div>
                </div>
              </div>
            </div>
            <div class="options-box">
              <div class="select-all">
                <div class="cart-checkbox">
                  <input
                    type="checkbox"
                    id="toggle-checkboxes_down"
                    name="toggle-checkboxes"
                    class="jdcheckbox"
                    clstag="clickcart|keycount|xincart|cart_allCheckDown"
                    checked="checked"
                  >
                  <label for>勾选全部商品</label>
                </div>全选
              </div>
              <div class="normal">
                <div class="comm-right">
                  <div class="btn-area">
                    <a
                      href="javascript:void(0);"
                      onclick="return false;"
                      clstag="clickcart|keycount|xincart|cart_gotoOrder"
                      class="submit-btn"
                      data-bind="1"
                    >
                      去结算
                      <b></b>
                    </a>
                  </div>
                  <div class="price-sum">
                    <div>
                      <span class="txt txt-new">总价：</span>
                      <span class="price sumPrice">
                        <em data-bind="68.40">¥68.40</em>
                      </span>
                      <b class="ml5 price-tips"></b>
                      <div class="price-tipsbox-new" style="display: none; left: 159.85px;">
                        <div class="ui-tips-main">不含运费及送装服务费</div>
                        <span class="price-tipsbox-arrow"></span>
                      </div>
                      <br>
                      <div id="price-sum-extra-1" class="price-sum-extra">
                        <span class>促销：</span>
                        <span class>-¥5.00</span>
                      </div>
                    </div>
                  </div>
                  <div class="amount-sum">
                    已选择
                    <em>6</em>件商品
                    <span class="iconfont icon-up"></span>
                  </div>
                  <div class="clr"></div>
                </div>
              </div>
            </div>
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
      cartList: []
    };
  },
  mounted(){
    this.getCartList();
  },
   methods: {
    getCartList() {
      axios
        .post("http://118.24.239.63:3000/cart", {
          id: localStorage.getItem('userId')
        })
        .then((response) => {
         if (response.data.status === '0') {
           this.cartList = response.data.result
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
.header {
  padding: 10px 0 0;
  width: 990px;
  margin: 0 auto;
  overflow: hidden;
  .logo-2014 {
    float: left;
    position: relative;
    width: 277px;
    padding: 0;
    height: 50px;
    margin: 15px 0 22px;
    .logo {
      display: block;
      margin-top: 2px;
      width: 134px;
      height: 42px;
      background: url(//misc.360buyimg.com/jdf/1.0.0/unit/global-header/5.0.0/i/jdlogo-201708-@1x.png)
        no-repeat 0 0;
      background-size: 134px 42px;
      text-indent: -20000px;
      float: left;
    }
    .link2 {
      float: left;
      overflow: hidden;
      display: block;
      position: absolute;
      width: 100px;
      height: 40px;
      top: 25px;
      right: 30px;
      background: #fff;
      font-size: 20px;
    }
  }
  .cart-search {
    float: right;
    border: 2px solid #c91623;
    background: #c91623;
    height: 24px;
    margin-top: 30px;
    overflow: hidden;
    .itxt {
      border: 0;
      height: 21px;
      line-height: 18px;
      width: 260px;
      padding: 3px 5px;
      outline: 0;
      color: rgb(153, 153, 153);
    }
    .button {
      display: inline-block;
      vertical-align: top;
      width: 48px;
      height: 21px;
      background: #c91623;
      text-align: center;
      color: #fff;
      font-weight: 700;
      -webkit-appearance: none;
      cursor: pointer;
      outline: none;
      border: 0;
    }
  }
}
.cart-filter-bar {
  width: 990px;
  height: 37px;
  margin-top: 10px;
  margin: 0 auto;
  position: relative;
  .switch-cart {
    float: left;
    position: relative;
    height: 26px;
    overflow: hidden;
    em {
      color: #e2231a;
      font-weight: 700;
      font-size: 16px;
      line-height: 26px;
      text-align: center;
    }
    span {
      color: #e2231a;
      font-weight: 700;
      font-size: 12px;
      line-height: 26px;
      text-align: center;
      margin-left: 5px;
    }
  }
  .cart-store {
    float: right;
    margin-bottom: 10px;
    padding-left: 122px;
    overflow: hidden;
    .label {
      float: left;
      line-height: 26px;
    }
    .ui-area-wrap {
      float: right;
      height: 26px;
      margin-right: 6px;
      border: 1px solid #cecbce;
      padding: 0 24px 0 4px;
      position: relative;
      .ui-area-text-wrap {
        float: left;
        font-size: 12px;
        height: 24px;
        line-height: 23px;
        background: #fff;
      }
      .iconfont_wrap {
        height: 24px;
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
  .clr {
    display: block;
    overflow: hidden;
    clear: both;
    height: 0;
    line-height: 0;
    font-size: 0;
  }
  .w-line {
    position: relative;
    height: 1px;
    background: #e0e0e0;
    .floater {
      position: absolute;
      height: 2px;
      background: #e2231a;
      width: 79px;
      left: 0px;
      overflow: hidden;
    }
  }
}
.cart-warp {
  background: #fff;
  margin-bottom: 20px;
  .w {
    width: 990px;
    margin: 0 auto;
    .jd-cart {
      .cart-thead {
        display: block;
        height: 32px;
        line-height: 32px;
        margin: 0 0 10px;
        padding: 5px 0;
        background: #f3f3f3;
        border: 1px solid #e9e9e9;
        border-top: 0;
        position: relative;
        .column {
          float: left;
        }
        .t-checkbox {
          height: 18px;
          line-height: 18px;
          padding-top: 7px;
          width: 122px;
          padding-left: 11px;
        }
        .t-goods {
          width: 208px;
        }
        .t-props {
          width: 140px;
          height: 32px;
          padding: 0 10px 0 20px;
        }
        .t-price {
          width: 120px;
          padding-right: 40px;
          text-align: right;
        }
        .t-quantity {
          width: 80px;
          text-align: center;
        }
        .t-sum {
          width: 100px;
          padding-right: 40px;
          text-align: right;
        }
        .t-action {
          width: 75px;
        }
      }
      .cart-item-list {
        width: 990px;
        .shop {
          height: 30px;
          line-height: 30px;
          padding-left: 11px;
          font-weight: 700;
          .cart-checkbox {
            position: relative;
            z-index: 3;
            float: left;
            margin-right: 5px;
            .jdcheckbox {
              float: none;
              position: relative;
              z-index: 5;
              vertical-align: middle;
              margin: 0 3px 0 0;
              padding: 0;
            }
          }
          .shop-txt {
            float: left;
            width: 42%;
            height: 30px;
            .shop-name {
              display: inline-block;
              max-width: 260px;
              overflow: hidden;
              vertical-align: middle;
              height: 30px;
              line-height: 30px;
            }
            .icon-lianxikefu {
              margin-left: 10px;
            }
          }
        }
        .item-list {
          border-style: solid;
          border-width: 2px 1px 1px;
          border-color: #aaa #f1f1f1 #f1f1f1;
          background: #fff;
          margin-bottom: 20px;
          .item-single {
            width: 988px;
            height: 118px;
            position: relative;
            line-height: 20px;
            padding-left: 10px;
          }
          .item-form {
            display: flex;
            justify-items: start;
            padding-top: 15px;

            label {
              display: none;
            }
            .p-checkbox {
              width: 30px;
              min-height: 10px;
              .cart-checkbox {
                width: 15px;
                margin-right: 5px;
              }
            }
            .p-goods {
              width: 300px;
              .goods-item {
                display: block;
                .p-img {
                  float: left;
                  width: 80px;
                  height: 80px;
                  border: 1px solid #eee;
                  margin-right: 10px;
                  background: #fff;
                  padding: 0;
                  text-align: center;
                  overflow: hidden;
                  img {
                    width: 100%;
                    height: 100%;
                  }
                }
                .p-name {
                  height: 40px;
                  line-height: 20px;
                  overflow: hidden;
                  a {
                    color: #333;
                  }
                }
                .fresh-icon {
                  display: inline-block;
                  width: 48px;
                  height: 20px;
                  background: url(//misc.360buyimg.com/user/cart/css/i/fresh-icon.png)
                    no-repeat;
                  vertical-align: middle;
                  overflow: hidden;
                  margin-right: 3px;
                }
                .p-extend {
                  margin-top: 2px;
                }
              }
            }
            .p-props {
              padding-left: 20px;
              line-height: 20px;
              overflow: hidden;
            }
            .p-price {
              width: 150px;
              padding-right: 40px;
              text-align: right;
            }
            .p-quantity {
              width: 80px;
              .quantity-form {
                position: relative;
                overflow: hidden;
                height: 22px;
                width: 80px;
                .disabled {
                  cursor: default;
                }
                .decrement {
                  border: 1px solid #cacbcb;
                  border-right: 0;
                  height: 18px;
                  line-height: 12px;
                  padding: 1px 0;
                  width: 16px;
                  text-align: center;
                  margin: 0;
                  background: #fff;
                  float: left;
                }
                .itxt {
                  border: 1px solid #cacbcb;
                  width: 42px;
                  height: 18px;
                  line-height: 18px;
                  text-align: center;
                  padding: 1px;
                  margin: 0;
                  font-size: 12px;
                  font-family: verdana;
                  color: #333;
                  -webkit-appearance: none;
                  float: left;
                }
                .increment {
                  border: 1px solid #cacbcb;
                  border-left: 0;
                  height: 18px;
                  line-height: 12px;
                  padding: 1px 0;
                  width: 16px;
                  text-align: center;
                  margin: 0;
                  background: #fff;
                  float: left;
                  margin-right: 0;
                }
              }
              .quantity-txt {
                position: relative;
                color: #aaa;
                text-align: center;
              }
            }
            .p-sum {
              width: 140px;
              height: 45px;
              padding-right: 40px;
              text-align: right;
              font-family: verdana;
            }
            .p-ops {
              width: 75px;
              position: relative;
              .cart-remove {
                display: block;
                width: 24px;
              }
            }
          }
        }
        .options-box {
          width: 988px;
          height: 52px;
          label {
            display: none;
          }
          .select-all {
            height: 18px;
            line-height: 18px;
            padding: 16px 0 16px 9px;
            white-space: nowrap;
            display: flex;
            float: left;
            .jdcheckbox {
              position: relative;
              float: none;
              vertical-align: middle;
              margin: 0 3px 0 0;
              padding: 0;
            }
          }
          .normal {
            width:720px;
            height: 52px;
            float: right;
            .comm-right {
              float: right;
              width: 650px;
              .btn-area {
                float: right;
                .submit-btn {
                  display: block;
                  position: relative;
                  width: 94px;
                  height: 52px;
                  line-height: 52px;
                  color: #fff;
                  text-align: center;
                  font-size: 18px;
                  background: #e54346;
                  overflow: hidden;
                  b {
                    display: block;
                    position: absolute;
                    width: 94px;
                    height: 52px;
                    top: 0;
                    left: 0;
                    overflow: hidden;
                    background: url(//misc.360buyimg.com/user/cart/css/i/cart-submit-btn-2019.png)
                      0 0 no-repeat;
                  }
                }
              }
              .price-sum {
                float: right;
                height: 43px;
                line-height: 20px;
                margin: 7px 5px 0 10px;
                color: #666;
                width: auto;
                position: relative;
                 em {
                  font-size: 16px;
                  color: #E2231A;
                  font-weight: 700;
                }
              }
              .amount-sum {
                float: right;
                color: #999;
                height: 44px;
                line-height: 20px;
                margin: 7px 0 0;
                cursor: pointer;
                em {
                  color: #E2231A;
                  font-family: verdana;
                  font-weight: 700;
                  margin: 0 3px;
                }
                .icon-up {
                  font-size: 10px;
                }
              }
              .clr {
                display: block;
                overflow: hidden;
                clear: both;
                height: 0;
                line-height: 0;
                font-size: 0;
              }
            }
          }
        }
      }
    }
  }
}
</style>


