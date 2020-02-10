<template>
  <section class="section_3 louceng">
    <div class="content">
      <ul class="left">
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
      <div class="right">
        <img src="../assets/images/9c23355a04207846.png.webp" alt="" />
        <img src="../assets/images/9c23355a04207846.png.webp" alt="" />
        <img src="../assets/images/9c23355a04207846.png.webp" alt="" />
        <img src="../assets/images/9c23355a04207846.png.webp" alt="" />
      </div>
    </div>
  </section>
</template>


<script>
export default {
  
}
</script>

<style lang="scss" scoped>
.section_3 {
    width:1270px;
    margin: 0 auto;
    background-color: #f4f4f4;
    height:590px;
    margin-top: 20px;
    background: url(../assets/images/68b7594144a8e1a5.png.webp) no-repeat center center;
    background-size: 100% 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    .content {
        width: 1200px;
        height: 440px;
        margin-top: 140px;
        display: flex;
        justify-content: space-between;
        .left {
            width: 990px;
            height: 100%;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            li {
                width: 190px;
                height: 210px;
                margin-bottom: 10px;
                background: url(../assets/images/7b44581badfd39d3.png.webp) no-repeat;
                background-size: 100% 100%;
            }
        }
        .right {
            width: 200px;
            height: 100%;
            img {
                width: 200px;
                height: 100px;
                display: block;
                margin-bottom: 10px;
            }
        }
    }
}
</style>


