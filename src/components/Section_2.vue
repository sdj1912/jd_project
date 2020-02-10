<template>
  <section class="section_2 louceng">
    <div class="sale">
      <div class="countdown-title">京东秒杀</div>
      <div class="countdown-desc"><strong>12:00</strong>点场 倒计时</div>
      <span class="timmer countdown-main">
        <span class="timmer__unit timmer__unit--hour">01</span>
        <span class="timmer__unit timmer__unit--minute">52</span>
        <span class="timmer__unit timmer__unit--second">29</span>
      </span>
    </div>
    <div class="goods">
      <ul>
        <li class="goods_list">
          <img src="../assets/images/shoes.webp" alt="" />
          <p>【今日必抢 精选皮质】【单绒可选 品质男鞋】</p>
          <div class="price">
            <div class="left">￥99.00</div>
            <div class="right">￥329.99</div>
          </div>
        </li>
        <li class="goods_list">
          <img src="../assets/images/ring.webp" alt="" />
          <p>【今日必抢 精选皮质】【单绒可选 品质男鞋】</p>
          <div class="price">
            <div class="left">￥129.00</div>
            <div class="right">￥529.88</div>
          </div>
        </li>
        <li class="goods_list">
          <img src="../assets/images/watch.webp" alt="" />
          <p>【今日必抢 精选皮质】【单绒可选 品质男鞋】</p>
          <div class="price">
            <div class="left">￥1299.00</div>
            <div class="right">￥3599.00</div>
          </div>
        </li>
        <li class="goods_list">
          <img src="../assets/images/bag.webp" alt="" />
          <p>【今日必抢 精选皮质】【单绒可选 品质男鞋】</p>
          <div class="price">
            <div class="left">￥1599.00</div>
            <div class="right">￥4799.00</div>
          </div>
        </li>
      </ul>
    </div>
    <div class="pictrue">
      <div class="wrap">
        <img src="../assets/images/tool.webp" alt="" />

        <p>相机品类秒杀</p>
        <h3>三脚架低至29.9</h3>
        <button>品类秒杀 ></button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  
}
</script>

<style lang="scss" scoped>
.section_2 {
    width:1190px;
    height: 260px;
    display: flex;
    justify-content: space-between;
    margin-top: 25px;
    margin: auto;
    .sale {
        width:190px;
        height:100%;
        background: url(../assets/images/613f39ecb60e42dfec798a4ffc0bc012.png);
        background-size: 100% 100%;
        color: #fff;
        .countdown-title {
            width: 100%;
            text-align: center;
            font-size: 30px;
            font-weight: 700;
            margin-top: 31px;
        }
        .countdown-desc {
            margin-top: 110px;
            font-size: 14px;
            text-align: center;
            strong {
                font-size: 18px;
                padding-right: 2px;
                vertical-align: middle;
                display: inline-block;
                margin-top: -1px;
            }
        }
        .countdown-main {
            margin-left: auto;
            margin-right: auto;
            width: 130px;
            height: 30px;
            margin-top: 10px;
            display: block;
            color: #333;
            font-weight: 700;
            .timmer__unit {
                position: relative;
                float: left;
                width: 30px;
                height: 30px;
                text-align: center;
                background-color: #2f3430;
                margin-right: 0px;
                color: white;
                font-size: 20px;
                line-height: 30px;
            }
            .timmer__unit--hour, .timmer__unit--minute {
                margin-right: 20px;
                &::after {
                    content: ":";
                    display: block;
                    position: absolute;
                    right: -20px;
                    font-weight: bolder;
                    font-size: 18px;
                    width: 20px;
                    height: 100%;
                    top: 0;
                }
            }
        }
    }
    .goods {
        width:800px;
        height:100%;
        overflow: hidden;
        ul {
            width: 800px;
            height: 100%;
            display: flex;
            background: #fff;
            font-size: 12px;
            font-weight: 400;
            color: rgb(51, 51, 51);
        }
        .goods_list {
            width:200px;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            &::after {
                content: "";
                display: block;
                position: absolute;
                top: 50%;
                right: 0;
                width: 1px;
                height: 200px;
                transform: translateY(-50%);
                background: linear-gradient(180deg,white,#eeeeee,white);
            }
            img {
                width: 140px;
                height: 140px;
                margin-top: 30px;
            }
            p {
                width: 160px;
                font-size: 12px;
                margin-top: 13px;
                overflow: hidden;
                white-space: nowrap;
                text-overflow: ellipsis;
            }
            .price {
                font-size: 14px;
                width: 160px;
                border: 1px solid #cf3a2b;
                margin-top: 7px;
                display: flex;
                .left {
                    width: 92px;
                    height: 22px;
                    background: #cf3a2b;
                    position: relative;
                    color:#fff;
                    line-height: 22px;
                    &::after {
                        content: '';
                        width: 0;
                        height: 0;
                        border: solid;
                        border-width: 11px 6px;
                        border-color: transparent #fff #fff transparent;
                        position: absolute;
                        right: 0;
                        top: 0;
                    }
                }
                .right {
                    width: 68px;
                    height: 100%;
                    background: #fff;
                    color:#999;
                    line-height: 22px;
                    text-decoration: line-through;
                }
            }
        }

    }
    .pictrue {
        width: 200px;
        height:100%;
        padding: 10px;
        box-sizing: border-box;
        background: #fff;
        .wrap {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            img {
                width:120px;
                height:120px;
            }
            p {
                font-size:14px;
                color:#666; 
                width:180px;
                height:21px;
                text-align: center;
                margin-top: 4px;
            }
            h3 {
                font-size: 14px;
                color:#333;
                width:180px;
                height:21px;
                text-align: center;
            }
            button {
                font-size: 12px;
                color:#e1251b;
                width:82px;
                height:24px;
                border-radius: 14px;
                line-height: 22px;
                font-weight: 700;
                border: 1px solid #e1251b;
                margin-top: 4px;
                padding-left: 4px;
            }   
        }
    }
}
</style>


