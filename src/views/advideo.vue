<template>
  <div class="advideo">
    <ul>
      <li v-for="item in list" :key="item.title">
        <img :src="item.path" alt="">
        <p>{{item.title}}</p>
      </li>
    </ul>
    <div class="pageLine">
      <span>上一页</span>
      <span>1</span>
      <span>下一页</span>
    </div>
    <foot></foot>
  </div>
</template>

<script>
import foot from '@/components/foot.vue'
export default {
  name: 'advideo',
  components: {foot},
  data () {
    return {
      list: [
        {
          path: require('@/assets/img/video/video-1.png'),
          title: '姑苏招商（2017版）',
        },
        {
          path: require('@/assets/img/video/video-2.png'),
          title: '姑苏招商（2012版）',
        },
        {
          path: require('@/assets/img/video/video-2.png'),
          title: '姑苏招商（2012版英文版）',
        },{
          path: require('@/assets/img/video/video-4.png'),
          title: '苏州姑苏（飞越姑苏）',
        },
        {
          path: require('@/assets/img/video/video-5.png'),
          title: '苏州城市（美丽苏州）',
        },
        {
          path: require('@/assets/img/video/video-6.png'),
          title: '苏州城市（双面绣）',
        },
        {
          path: require('@/assets/img/video/video-7.png'),
          title: '桃花坞项目',
        },
        {
          path: require('@/assets/img/video/video-8.png'),
          title: '渔家村项目',
        },
        {
          path: require('@/assets/img/video/video-9.png'),
          title: '虎丘综改项目',
        },
        {
          path: require('@/assets/img/video/video-10.png'),
          title: '姑苏软件园项目',
        },
        {
          path: require('@/assets/img/video/video-11.png'),
          title: '虎丘婚纱城项目',
        }
      ]
    }
  },

  methods: {

  },
  created() {

  }
}
</script>

<style lang='scss' scoped>
.advideo {
  --ft-color: #666;
  overflow: hidden;
  background-color: #ebe8eb;
  ul {
    display: flex;
    flex-wrap: wrap;
    margin: 0 auto;
    width: 1096px;
    li {
      margin: 20px 20px 0 20px;
      width: 234px;
      height: 225px;
      img {
        display: block;
        width: 234px;
        height: 175px;
      }
      p {
        margin: 10px 0 14px;
        width: 100%;
        height: 26px;
        color: #666;
        font-size: 20px;
        font-family: 微软雅黑;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
      }
    }
  }
  .pageLine {
    margin: 30px 0 60px;
    span {
      display: inline-block;
      width: 52px;
      height: 25px;
      font-size: 14px;
      color: var(--ft-color)
    }
  }
}
</style>
