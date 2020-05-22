<template>
  <div id="foot">
    <p>
      <span>©2017 姑苏经科 版权所有 手机版</span>
      <span>
        关注我们 友情链接：
        <a href="http://www.gusu.gov.cn/">中国·姑苏</a>
        <a href="http://qyfw.gusu.gov.cn/">姑苏企业服务网</a>
      </span>
    </p>
  </div>
</template>

<script>
export default {
  name: "foot",
  data() {
    return {};
  },

  methods: {},
  created() {}
};
</script>

<style lang='scss' scoped>
#foot {
  width: 100%;
  color: #a9a9a9;
  font-size: 14px;
  font-family: 宋体;
  background-color: #303030;
  p {
    margin: 0 auto;
    width: 1200px;
    height: 39px;
    // line-height: 39px;
    text-align: left;
    span:nth-child(1) {
      display: inline-block;
      margin: 12.5px 50px 12.5px 50px;
      width: 462px;
      height: 14px;
    }
    span:nth-child(2) {
      a {
        color: #a9a9a9;
        margin-right: 10px;
      }
    }
  }
}
</style>
