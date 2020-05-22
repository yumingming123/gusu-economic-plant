<template>
  <div id="about">
    <div class="about-center">
      <div class="head">
        <span
          v-for="item in list"
          :key="item"
          :class="show == item ? 'act': ''"
          @mouseenter="show = item"
        >{{item}}</span>
      </div>
      <div class="market" v-show="show == '市场简介'">
        <p>苏州，地处长江三角洲中部。东临上海，南接浙江，西抱太湖，北依长江。境内京杭大运河纵贯南北。总面积8,488平方公里，其中河流、湖泊、滩涂面积占全市土地面积的36.6%，是著名的江南水乡。苏州是闻名遐迩的鱼米之乡、园林之城、丝绸之府、工艺之肆，素有“人间天堂”之美誉。</p>
        <img src="@/assets/img/about/market-1.gif" alt />
        <p>苏州是中国历史文化名城和重点风景旅游城市。苏州古城始建于公元前514年，距今已有2500多年，目前仍座落在春秋时期的原址上，基本保持着“水陆并行、河街相邻”的双棋盘格局，“三纵三横一环”的河道水系和“小桥流水、粉墙黛瓦、史迹名园”的独特风貌。苏州拥有丰富的物质和非物质文化遗产。全市保存完好的苏州古典园林58处，其中拙政园、留园等9座园林被列入《世界文化遗产名录》。昆曲、古琴艺术等6个项目被列入联合国教科文组织“人类口述和非物质遗产代表作”。平江、山塘历史街区分别被评为中国历史文化名街和中国最受欢迎的旅游历史文化名街。</p>
        <img src="@/assets/img/about/market-2.gif" alt />
        <p>今天的苏州又是一个经济发达的现代化城市。改革开放30多年，苏州经济保持了又好又快的发展态势。苏州对外开放程度较高。目前已有150家世界500强企业在苏州投资项目（企业）。国际友好城市达53个。苏州常住外籍人士近5万人，连续六年入选“魅力中国——外籍人才眼中最具吸引力的中国城市”。苏州还被世界银行评为“中国投资环境金牌城市”，充分展示了活力与魅力、吸引力与竞争力兼具的城市形象。</p>
      </div>
      <div class="market" v-show="show == '区情简介'">
        <p>姑苏区、苏州国家历史文化名城保护区成立于2012年10月26日，由苏州原平江、沧浪、金阊三个老城区合并而成，位于苏州城区中心，总面积85.1平方公里，包含14.2平方公里的苏州古城全部，常住人口约100万。保护区是全国首个也是唯一一个国家历史文化名城保护区。</p>
        <img src="@/assets/img/about/area-1.gif" alt />
        <p>姑苏区是苏州的政治、教育、文化、旅游中心，也是苏州历史最为悠久、人文积淀最为深厚的中心城区。拥有各级文物保护单位174处，其中全国重点文物保护单位24处，省级文保单位37处，控保建筑252处，古桥、古井等古构筑物790处。区内有虎丘、留园、拙政园等国家5A级景区，平江路、山塘街2条中国历史文化名街，沧浪亭、狮子林等8处园林和大运河5个核心点段列入世界文化遗产名录。此外，辖区内共有各类非物质文化遗产代表性项目106项，其中世界级4项，国家级18项，省级17项。</p>
        <img src="@/assets/img/about/area-2.gif" alt />
        <p>姑苏区是苏州“一核四城”发展战略中的“核”。当前，姑苏区突出“两聚一高”主题，重点实施古城复兴、创新驱动、文化引领、民生优先四大发展战略，全力推进历史文化名城保护和提升六大工程，努力建设“历史文化保护示范区、高端服务经济集聚区、文旅融合发展创新区、和谐社会建设样板区”，为做实做亮历史文化名城之“核”而努力奋斗。</p>
      </div>
      <div class="market" v-show="show == '产业简介'">
        <p>
          <span>科技创意产业：</span>依托自主创新广场、白鹭紫荆创新中心、姑苏软件园等产业园载体，重点扶持研发设计、检验检测、金融创新、互联网服务等科技型企业，形成高端科技服务体系。
        </p>
        <img src="@/assets/img/about/product-1.gif" alt />
        <p>
          <span>特色商贸产业：</span>引导观前、石路、南门三大商圈提档升级，重点发展百年老字号、时尚新零售、高端商务、跨境电商等主流、新型业态，打造特色商贸核心区。
        </p>
        <img src="@/assets/img/about/product-2.gif" alt />
        <p>
          <span>文化旅游产业：</span>以共建国家文化新经济试验区为契机，推进历史文化街区、精品主题酒店、互动文旅体验项目建设，重点培育文创IP、授权经济、全域旅游等新经济模式，实现文商旅产业的跨越式发展。
        </p>
        <img src="@/assets/img/about/product-3.gif" alt />
      </div>
    </div>
    <foot></foot>
  </div>
</template>

<script>
import foot from "@/components/foot.vue";
export default {
  name: "about",
  components: { foot },
  data() {
    return {
      list: ["市场简介", "区情简介", "产业简介"],
      show: "市场简介"
    };
  },

  methods: {},
  created() {}
};
</script>

<style lang='scss' scoped>
#about {
  width: 100%;
  background-image: linear-gradient(
    to bottom,
    rgb(230, 230, 230) 0,
    #ebe8eb 2%,
    #ebe8eb 100%
  );
  .about-center {
    margin: 0 auto;
    width: 1200px;
    height: 2011px;
    padding: 0 150px;
    box-sizing: border-box;
    .head {
      height: 60px;
      line-height: 60px;
      text-align: left;
      span {
        display: inline-block;
        margin: 0 20px;
        width: 130px;
        height: 36px;
        line-height: 36px;
        text-align: center;
        border-radius: 18px;
        color: #666;
        cursor: default;
        transition: all 0.5s;
        &.act {
          color: #fff;
          background-color: #fa643f;
        }
      }
    }
    .market {
      p {
        line-height: 31px;
        color: #666;
        font-size: 22px;
        font-family: 微软雅黑;
        text-indent: 2em;
        text-align: justify;
        &:nth-child(1) {
          margin-top: 20px;
        }
        span {
          font-weight: bold;
        }
      }
      img {
        margin: 50px 0;
      }
    }
  }
}
</style>

