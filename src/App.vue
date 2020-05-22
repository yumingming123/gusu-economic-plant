<template>
  <div id="app">
    <div id="nav">
      <div id="nav-center">
        <div id="nav-c-l">
          <img src="@/assets/logo.png" alt />
          <div>
            <p>姑苏招商云平台</p>
            <p><span>GUSU</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  INVESTMENT</p>
          </div>
        </div>
        <div id="nav-c-c">
          <!-- <router-link v-for="item in list" :key="item.name" :to="item.path" @click="enter(item)">{{item.name}}</router-link> -->
          <a
            v-for="item in list"
            :key="item.name"
            @click="enter(item)"
            :class="nowAct == item.name ? 'router-act':''"
          >{{item.name }}</a>
        </div>
        <img src="@/assets/img/home/lake.png" alt />
      </div>
    </div>
    <router-view />
  </div>
</template>

<script>
// import 'babel-polyfill'
export default {
  data() {
    return {
      list: [
        {
          name: "首页",
          path: "/index"
        },
        {
          name: "投资环境",
          path: "/about"
        },
        {
          name: "投资热力图",
          path: "http://gszs.gusu.gov.cn/maps/index.html"
        },
        {
          name: "政策扶持",
          path: "/policy"
        },
        {
          name: "宣传视频",
          path: "/advideo"
        },
        {
          name: "企业服务",
          path: "http://qyfw.gusu.gov.cn/"
        }
      ],
      nowAct: "首页"
    };
  },
  watch: {
    // $route: {
    // handler: function(val, oldVal) {
    //   console.log(val);
    //   var obj = this.list.find(el => el.path == this.$route.fullPath);
    //   if(obj){
    //     this.nowAct = obj.name;
    //   }else {
    //     this.nowAct = '';
    //   }
    // },
    // // 深度观察监听
    // deep: true
    // }
    $route(to, from) {
      // console.log(to.path);
      var obj = this.list.find(el => el.path == this.$route.fullPath);
      if(obj){
        this.nowAct = obj.name;
      }else {
        this.nowAct = '';
      }
    }
  },
  methods: {
    enter(item) {
      if (item.name == "投资热力图") {
        window.location.href = item.path;
      } else if (item.name == "企业服务") {
        window.location.href = item.path;
      } else {
        console.log(this.$route.path);
        if (this.$route.path != item.path) {
          this.$router.push(item.path);
        }
      }
      this.nowAct = item.name;
    }
  },
  mounted() {
  },
  created() {
    var obj = this.list.filter(el => el.path == this.$route.fullPath);
    // console.log(obj);
  }
};
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  width: 100%;
  #nav-center {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
    width: 1200px;
    height: 85px;
    // background-color: rgb(175, 175, 175);
    #nav-c-l {
      display: flex;
      margin: 10px 20px 0 0;
      > img {
        width: 85px;
        height: 45px;
      }
      > div {
        p:nth-child(1) {
          font-size: 20px;
          letter-spacing: 1.5px;
          color: rgb(230, 74, 25);
        }
        p:nth-child(2) {
          margin-top: 10px;
          height: 19px;
          line-height: 19px;
          font-size: 16px;
          span {
            // margin-right: 10px;
          }
        }
      }
    }
    #nav-c-c {
      font-size: 16px;
      > a {
        display: inline-block;
        width: 100px;
        height: 35px;
        color: black;
        line-height: 35px;
        text-decoration: none;
        cursor: pointer;
        &.router-act,
        &:hover {
          color: white;
          border-radius: 17.5px;
          background-color: #fa643f;
        }
      }
    }
    > img {
      display: inline-block;
      margin-left: 10px;
      width: 122px;
      height: 34px;
    }
  }
  // padding: 30px;

  // a {
  //   font-weight: bold;
  //   color: #2c3e50;

  //   &.router-link-exact-active {
  //     color: #42b983;
  //   }
  // }
}
</style>
