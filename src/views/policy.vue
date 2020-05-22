<template>
  <div id="policy">
    <iframe ref="iframe" src="http://qyfw.gusu.gov.cn/ZhengCe/YiLan" frameborder="0"></iframe>
    <foot></foot>
  </div>
</template>

<script>
import foot from "@/components/foot";
export default {
  name: "policy",
  components: { foot },
  data() {
    return {};
  },

  methods: {},
  created() {
    console.log(this.$refs.iframe);
  }
};
</script>

<style lang='scss' scoped>
#policy {
  background-color: #ebe8eb;
  iframe {
    margin: 0 auto;
    width: 1200px;
    // height: 612px;
    height: calc(100vh - 127px);
    overflow-y: hidden;
    &::-webkit-scrollbar {
      width: 10px;
      background-color: #fff;
    }
  }
}
</style>
