<template>
  <div class="economicAd">
      <img src="@/assets/img/home/economic-ad.png" alt="">
      <img src="@/assets/img/home/transparentAd.png" class="inImg" @click="enter" alt="">
  </div>
</template>

<script>
export default {
  name: 'economicAd',
  data () {
    return {

    }
  },

  methods: {
    enter(){
      // window.location.href = 'http://gszs.gusu.gov.cn/maps/index.html';
      window.open('http://gszs.gusu.gov.cn/maps/index.html', '_blank')
    }
  },
  created() {

  }
}
</script>

<style lang='scss' scoped>
.economicAd {
  position: relative;
  margin: 0 auto;
  width: 1000px;
    user-select: none;
    img {
    user-select: none;
    }
      .inImg {
        position: absolute;
        bottom: 300px;
        right: 100px;
        z-index: 10;
        cursor: pointer;
      }
}
</style>