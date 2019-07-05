<template>
<section class="m-istyle">
  <dl @mouseover="over">
    <dt>有格调</dt>
    <dd
      :class="{active:kind==='all'}"
      kind="all"
      keyword="景点">全部</dd>
    <dd
      :class="{active:kind==='part'}"
      kind="part"
      keyword="美食">约会聚餐</dd>
    <dd
      :class="{active:kind==='spa'}"
      kind="spa"
      keyword="丽人">丽人SPA</dd>
    <dd
      :class="{active:kind==='movie'}"
      kind="movie"
      keyword="电影">电影演出</dd>
    <dd
      :class="{active:kind==='travel'}"
      kind="travel"
      keyword="旅游">品质出游</dd>
  </dl>
  <ul class="ibody">
    <li
      v-for="item in cur"
      :key="item.title">
      <el-card
        :body-style="{ padding: '0px' }"
        shadow="never">
        <img
          :src="item.img"
          class="image">
        <ul class="cbody">
          <li class="title">{{ item.title }}</li>
          <li class="pos"><span>{{ item.pos[0]}}</span></li>
          <li class="price">￥<em>{{ item.price }}</em><span>/起</span></li>
        </ul>
      </el-card>
    </li>
  </ul>
</section>
</template>
<script>
export default {
  data() {
    return {
      kind: "all",
      list: {
        all: [{
          img: '//p1.meituan.net/tdchotel/030ec54a3c462d9c416f7cd813a441ed7121041.jpg@368w_208h_1e_1c',
          title: '博雅图国际公寓',
          pos: ['新客超值优惠', '预约发票', '房间内消费品'],
          price: '398'
        }],
        dataing: [{
          img: '//p1.meituan.net/deal/201212/29/172446_3275997.jpg@368w_208h_1e_1c',
          title: '太平洋咖啡（仁恒一店)',
          pos: ['标准杯美式1杯'],
          price: '0'
        }],
        spa: [{
          img: '//p0.meituan.net/joymerchant/6413292694796615731-1001051-1539171296022.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
          title: '君上SPA养生馆',
          pos: ['君上SPA养生馆'],
          price: '232'
        }],
        movie: [{
          img: '//p1.meituan.net/deal/201211/14/_1114152725.jpg@368w_208h_1e_1c',
          title: '卢米埃影城（来福士店）',
          pos: ['免押金', '可停车'],
          price: '32.9'
        }],
        travel: [{
          img: '//p1.meituan.net/tdchotel/030ec54a3c462d9c416f7cd813a441ed7121041.jpg@368w_208h_1e_1c',
          title: '成都禧悦酒店',
          pos: ['房量充足', '发票推荐', '含早'],
          price: '336'
        }]
      }
    }
  },
  computed: {
    cur: function () {
      return this.list[this.kind]
    }
  },
}
</script>

<style lang="scss">
 @import "@/assets/css/index/artistic.scss";

</style>
