<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <div class="banner">
      <!-- <swiper ref="mySwiper" :options="swiperOptions">
        <swiper-slide v-for="item in list" :key="item">
          <div :style="getImg(item)"></div>
        </swiper-slide>
        <div class="swiper-button-next swiper-btn" slot="button-next"></div>
        <div class="swiper-button-prev swiper-btn" slot="button-prev"></div>
      </swiper>-->
      <div class="swiper-container" @mouseenter="enterBox" @mouseleave="leaveBox">
        <div class="swiper-wrapper" ref="swi">
          <div class="swiper-slide" ref="swiItem" v-for="item in list" :key="item">
            <div :style="getImg(item)"></div>
          </div>
        </div>
        <div class="swiper-button-next swiper-btn" @click="arrR"></div>
        <div class="swiper-button-prev swiper-btn" @click="arrL"></div>
        <div class="banner-top-ad">
          <p>姑苏招商 &emsp; 一站服务</p>
          <h1>
            需求
            <span style="color: #F78B21">多变</span> 努力
            <span style="color: #F78B21">不变</span>
          </h1>
          <h2>全天候为您服务</h2>
        </div>
        <a v-if="showAd" @click="dd" class="banner-ad" href="/economicAd">
          <img class="banner-ad-img" src="@/assets/img/home/banner-p-1.jpg" alt />
          <img
            @click.stop="showAd = false"
            class="banner-ad-close"
            src="@/assets/img/home/close.svg"
            alt
          />
        </a>
        <div class="banner-bottom">
          <div class="banner-bottom-l">
            <p>FIND YOUR</p>
            <h1>NEEDS</h1>
          </div>
          <div class="banner-bottom-c">
            <div class="banner-b-c-t">
              <input type="text" placeholder="请输入载体名称..." />
              <img src="@/assets/img/home/search.svg" alt />
            </div>
            <div class="banner-b-c-b">
              <a
                href="http://gszs.gusu.gov.cn/maps/index.html"
                v-for="item in searchHot"
                :key="item"
              >{{item}}</a>
            </div>
          </div>
          <div class="banner-bottom-r">
            <img src="@/assets/img/home/map.svg" class="map" />
            <a href="http://gszs.gusu.gov.cn/maps/index.html">查看地图</a>
          </div>
        </div>
      </div>
    </div>
    <!-- <div :style="note"></div> -->
    <div class="content">
      <div class="content-center">
        <img src="@/assets/img/home/yuanlin.png" alt />
        <div class="content-center-r">
          <h1>关于我们</h1>
          <h2>About Us</h2>
          <p>
            姑苏区、苏州国家历史文化名城保护区成立于2012年10月26日，由苏州原平江、
            沧浪、金阊三个老城区合并而成，位于苏州城区中心，总面积85.1平方公里，包含14.2
            平方公里的苏州古城全部，常住人口约100万。保护区是全国首个也是唯一一个国家历
            史文化名城保护区。
          </p>
          <a href="/about">更多&emsp;&gt;&gt;</a>
        </div>
      </div>
    </div>
    <div class="foot">
      <div class="foot-center">
        <div class="foot-center-t">
          <div class="foot-center-t-l">
            <h1>
              联系我们
              <span>Contact Us</span>
            </h1>
            <img src="@/assets/img/home/qrcode.png" alt />
          </div>
          <div class="foot-center-t-r">
            <h1>
              姑苏区经济和科技局
              <span>Gusu Economy &amp; Technology</span>
            </h1>
            <p>电话 : 0512-68727505、68727506</p>
            <p>邮编：215031</p>
            <p>传真：68726266</p>
            <p>地址：苏州市姑苏区平川路510号</p>
          </div>
        </div>
        <div class="foot-center-b">
          <span>©2017 姑苏经科 版权所有</span>
          <span>
            友情链接：
            <a href="http://www.gusu.gov.cn/">中国 · 姑苏</a>
            <a href="http://qyfw.gusu.gov.cn/">姑苏企业服务网</a>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import Swiper from '@/assets/js/idangerous.swiper.min.js'
export default {
  name: "Home",
  data() {
    return {
      searchHot: [
        "平江",
        "金阊",
        "沧浪",
        "双塔",
        "虎丘",
        "苏锦",
        "吴门桥",
        "白洋湾"
      ],
      showAd: true,
      list: [
        require("@/assets/img/home/page-1.jpg"),
        require("@/assets/img/home/page-2.jpg"),
        require("@/assets/img/home/page-3.jpg"),
        require("@/assets/img/home/page-4.jpg"),
        require("@/assets/img/home/page-5.jpg"),
        require("@/assets/img/home/page-6.jpg"),
        require("@/assets/img/home/page-7.jpg"),
        require("@/assets/img/home/page-8.jpg"),
        require("@/assets/img/home/page-9.jpg")
      ],
      note: {
        backgroundImage: "url(" + require("@/assets/img/home/page-1.jpg") + ")",
        backgroundRepeat: "no-repeat",
        backgroundSize: "contain",
        marginTop: "5px",
        height: "500px",
        width: "100%"
      },
      isOver: true,
      timer: null,
      count: 0,
      autoTimer: null
    };
  },
  methods: {
    getImg(img) {
      const obj = {
        backgroundImage: "url(" + img + ")",
        backgroundRepeat: "no-repeat",
        backgroundPosition: "center",
        backgroundSize: "cover",
        height: "500px",
        width: "100%"
      };
      return obj;
    },
    dd() {
      console.log("didi");
    },
    arrL() {
      if (!this.isOver) {
        return;
      }
      this.count--;
      if (this.count == -1) {
        this.count = 7;
        this.$refs.swi.style.left =
          -this.$refs.swiItem[0].offsetWidth * 8 + "px";
      }
      let target = -this.$refs.swiItem[0].offsetWidth * this.count;
      this.slowMove(target);
    },
    arrR() {
      if (!this.isOver) {
        return;
      }
      this.count++;
      if (this.count == 9) {
        this.count = 1;
        this.$refs.swi.style.left = "0px";
      }
      let target = -this.$refs.swiItem[0].offsetWidth * this.count;
      this.slowMove(target);
    },
    slowMove(target) {
      this.isOver = false;
      this.timer = setInterval(() => {
        var start = this.$refs.swi.offsetLeft;
        var step = (target - start) / 10;
        if (step < 1) {
          step = step > 0 ? 1 : Math.floor(step);
        }
        this.$refs.swi.style.left = start + step + "px";
        if (start + step == target) {
          console.log("stop...");
          this.isOver = true;
          clearInterval(this.timer);
        }
      }, 17);
    },
    autoPlay() {
      this.autoTimer = setInterval(() => {
        this.arrR();
      }, 3000);
    },
    enterBox() {
      clearInterval(this.autoTimer);
      console.log("鼠标进入盒子了");
    },
    leaveBox() {
      this.autoPlay();
      console.log("鼠标离开盒子了");
    }
  },
  mounted() {
    this.$nextTick(() => {
      // console.log(this.$refs.swi.offsetLeft);
      // console.log(this.$refs.swiItem[0].offsetWidth)
      this.autoPlay();
    });
  },
  created() {}
};
</script>

<style lang="scss" scoped>
a {
  color: white;
  text-decoration: none;
}
.home {
  width: 100%;
  overflow: hidden;
  .banner {
    position: relative;
    width: 100%;
    height: 500px;
    .swiper-container {
      height: 500px;
      // overflow: hidden;
      .swiper-wrapper {
        position: relative;
        display: flex;
        width: 900%;
        height: 500px;
        .swiper-slide {
          height: 500px;
          width: 11.11%;
        }
      }
      .swiper-button-next {
        right: 100px;
        background: url("~@/assets/img/home/arrR.svg") no-repeat center/contain;
      }
      .swiper-button-prev {
        left: 100px;
        background: url("~@/assets/img/home/arrL.svg") no-repeat center/contain;
      }
      .swiper-btn {
        position: absolute;
        top: 230px;
        width: 71px;
        height: 71px;
        border-radius: 5px;
        color: #fff;
        background-color: rgba(106, 106, 106, 0.2);
        &:hover {
          background-color: rgba(0, 0, 0, 0.5);
        }
      }
      .banner-top-ad {
        position: absolute;
        top: 20px;
        left: 50%;
        transform: translate(-50%, 0);
        width: 358px;
        height: 144px;
        color: white;
        background-color: rgba(106, 105, 106, 0.5);
        z-index: 10;
        p {
          margin-top: 20px;
          height: 36px;
          line-height: 36px;
          font-size: 20px;
        }
        h1 {
          height: 42px;
          line-height: 42px;
          font-size: 36px;
        }
        h2 {
          height: 37px;
          line-height: 37px;
          font-size: 18px;
        }
      }
      > .banner-ad {
        position: absolute;
        top: 80px;
        right: 60px;
        display: block;
        width: 225px;
        height: 150px;
        z-index: 10;
        > .banner-ad-img {
          width: 100%;
          height: 100%;
        }
        > .banner-ad-close {
          position: absolute;
          top: 0;
          right: 0;
          width: 20px;
          height: 20px;
        }
      }
      > .banner-bottom {
        display: flex;
        justify-content: center;
        align-items: center;
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        margin: 0 auto;
        padding: 30px 0 40px;
        width: 900px;
        height: 140px;
        color: white;
        z-index: 10;
        box-sizing: border-box;
        .banner-bottom-l {
          padding-right: 8px;
          height: 47px;
          width: 80px;
          border-right: 3px solid white;
          p {
            height: 16px;
            line-height: 16px;
            font-size: 12px;
            letter-spacing: 1px;
          }
          h1 {
            height: 26px;
            line-height: 26px;
            font-size: 20px;
          }
        }
        .banner-bottom-c {
          margin: 0 50px;
          width: 580px;
          .banner-b-c-t {
            display: flex;
            padding: 10.5px 15px;
            height: 42px;
            border-radius: 21px;
            box-sizing: border-box;
            background-color: #fff;
            > input {
              height: 21px;
              width: 540px;
              padding: 0;
              border: none;
              outline: none;
            }
            img {
              height: 20px;
              width: 20px;
            }
          }
          .banner-b-c-b {
            margin-top: 10px;
            > a {
              margin-right: 20px;
              font-size: 14px;
            }
          }
        }
        .banner-bottom-r {
          display: flex;
          margin-bottom: 10px;
          .map {
            width: 25px;
            height: 25px;
          }
          > a {
            height: 25px;
            line-height: 25px;
          }
        }
      }
    }
  }
  .content {
    width: 100%;
    background-color: #ebe8eb;
    overflow: hidden;
    .content-center {
      display: flex;
      justify-content: center;
      margin: 20px auto 0;
      width: 1200px;
      > img {
        margin-right: 20px;
        width: 236px;
        height: 236px;
      }
      .content-center-r {
        width: 685px;
        text-align: left;
        h1 {
          margin-top: 20px;
          height: 26px;
          line-height: 26px;
          font-size: 20px;
          color: #f56d1e;
        }
        h2 {
          height: 24px;
          line-height: 24px;
          font-size: 18px;
          color: #fb8c00;
        }
        p {
          margin-bottom: 30px;
          color: #353535;
          font-size: 18px;
          line-height: 28px;
          text-indent: 2em;
        }
        > a {
          color: #353535;
        }
      }
    }
  }
  .foot {
    width: 100%;
    height: 341px;
    background-color: #858585;
    .foot-center {
      margin: 0 auto;
      width: 1200px;
      .foot-center-t {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        .foot-center-t-l {
          margin: 40px 50px;
          h1 {
            margin-bottom: 20px;
            height: 36px;
            line-height: 36px;
            font-size: 20px;
            color: #ff6600;
            span {
              margin-left: 10px;
              color: #fff;
              font-size: 16px;
            }
          }
          img {
            width: 136px;
            height: 136px;
          }
        }
        .foot-center-t-r {
          margin: 40px 50px;
          width: 419px;
          text-align: left;
          h1 {
            margin-bottom: 24px;
            height: 36px;
            line-height: 36px;
            font-size: 20px;
            color: #ff6600;
            span {
              margin-left: 10px;
              color: #fff;
              font-size: 16px;
            }
          }
          p {
            height: 24px;
            line-height: 24px;
            font-size: 14px;
            color: #212121;
          }
        }
      }
      .foot-center-b {
        font-size: 14px;
        color: #353535;
        span:nth-child(1) {
          margin-right: 50px;
        }
        a {
          color: #353535;
          &:nth-child(1) {
            margin-right: 20px;
          }
        }
      }
    }
  }
}
</style>