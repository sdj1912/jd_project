<template>
  <div class="home">
    <Top></Top>
    <JdHeader></JdHeader>
    <Section_1></Section_1>
    <Section_2 ref="s2"></Section_2>
    <Section_3 ref="s3"></Section_3>
    <Section_6 ref="s6"></Section_6>
    <Section_7 ref="s7"></Section_7>
    <Footer></Footer>
    <nav class="elevator" v-show="elevatorShow">
      <li
        v-for="(item, index) in navList"
        :key="index"
        :class="{ second: index == 1, active: index == navIndex }"
        v-text="item.name"
        @click="navChange(index, item.ref)"
      ></li>
      <li class="last" @click="goTop">顶部</li>
    </nav>
  </div>
</template>

<script>
import Top from "../components/Top";
import JdHeader from "../components/JdHeader";
import Section_1 from "../components/Section_1";
import Section_2 from "../components/Section_2";
import Section_3 from "../components/Section_3";
import Section_6 from "../components/Section_6";
import Section_7 from "../components/Section_7";
import Footer from "../components/Footer";
export default {
  name: "home",
  components: {
    Top,
    JdHeader,
    Section_1,
    Section_2,
    Section_3,
    Section_6,
    Section_7,
    Footer
  },
  data() {
    return {
      elevatorShow: false,
      navList: [
        {
          name: "京东秒杀",
          ref: "s2"
        },
        {
          name: "",
          ref: "s3"
        },
        {
          name: "频道广场",
          ref: "s6"
        },
        {
          name: "为你推荐",
          ref: "s7"
        }
      ],
      navIndex: 0
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll, true);
  },
  beforeRouteLeave(to, from, next) {
    //离开路由前执行
    window.removeEventListener("scroll", this.handleScroll);
    next();
  },
  methods: {
    handleScroll() {
      let scrollTop = document.documentElement.scrollTop;
      if (scrollTop > 260) {
        this.elevatorShow = true;
      } else {
        this.elevatorShow = false;
      }
    },
    goTop() {
      let scrollTop = document.documentElement.scrollTop;
      if (scrollTop > 0) {
        requestAnimationFrame(() => {
          this.goTop();
        });
        scrollTo(0, scrollTop - scrollTop / 8);
      } else {
        cancelAnimationFrame(() => {
          this.goTop();
        });
      }
    },
    navChange(index, ref) {
      this.navIndex = index;
      let scrollTop = document.documentElement.scrollTop;
      if (Math.abs(scrollTop - this.$refs[ref].$el.offsetTop) > 8) {
        requestAnimationFrame(() => {
          this.navChange(index, ref);
        });
        if (scrollTop > this.$refs[ref].$el.offsetTop) {
          scrollTo(
            0,
            scrollTop - (scrollTop - this.$refs[ref].$el.offsetTop) / 8
          );
        } else {
          scrollTo(
            0,
            scrollTop + (this.$refs[ref].$el.offsetTop - scrollTop) / 8
          );
        }
      } else {
        cancelAnimationFrame(() => {
          this.navChange(index, ref);
        });
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.home {
  background: #eee;
}
.elevator {
  width: 60px;
  position: fixed;
  top: 75px;
  left: 50%;
  background: #fff;
  margin-left: 615px;
  z-index: 100;

  li {
    width: 60px;
    height: 60px;
    padding: 10px 16px;
    font-size: 14px;
    color: #333;
    line-height: 19px;
    position: relative;
    cursor: pointer;
    img {
      width: 60px;
      height: 60px;
      position: absolute;
      left: 0;
      top: 0;
      z-index: 0;
      width: 100%;
    }
    &::after {
      content: "";
      width: 28px;
      height: 1px;
      background: #eee;
      position: absolute;
      bottom: 0;
      left: 16px;
    }
    &:hover {
      background: #c81623;
      color: #fff;
      &::after {
        background-color: #c81623;
      }
    }
  }
  .second {
    background: url(../assets/images/366f8c47ba15dc8a.gif);
    background-size: 100% 100%;
    &:hover {
      background: url(../assets/images/a379e58cf2e04385.png);
      background-size: 100% 100%;
    }
  }
  .active {
    color: #c81623;
  }
}
</style>

