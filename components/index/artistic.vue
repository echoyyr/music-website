<template>
<section class="m-istyle">
  <dl @mouseover="over">
    <dt>热门推荐</dt>
    <dd
      :class="{active:kind==='all'}"
      kind="all"
      keyword="景点">华语</dd>
    <dd
      :class="{active:kind==='part'}"
      kind="part"
      keyword="美食">流行</dd>
    <dd
      :class="{active:kind==='spa'}"
      kind="spa"
      keyword="丽人">摇滚</dd>
    <dd
      :class="{active:kind==='movie'}"
      kind="movie"
      keyword="电影">民谣</dd>
    <dd
      :class="{active:kind==='travel'}"
      kind="travel"
      keyword="旅游">电子</dd>
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
          <li class="pos" >
            <span>{{ item.pos[0] }}</span>
            <span>{{ item.pos[1] }}</span>
            <span>{{ item.pos[2] }}</span>
          </li>
          <li class="price">介绍：{{ item.price }}</li>
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
          img: 'http://p4.music.126.net/gaCgugOoWNWrpewdtMZXTQ==/109951164168003132.jpg?param=200y200',
          title: '氛围流行 浪漫是它的本色',
          pos: ['流行', '欧美', '浪漫'],
          price: '凭感觉走吧 闭上眼睛就好'
        }, {
            img: 'http://p4.music.126.net/c1c92E86Cq7h68xHCGj59w==/109951164151563947.jpg?param=200y200',
            title: '一个人熬过一些苦 才能无所不能',
            pos: ['华语', '民谣', '欧美'],
            price: '凭感觉走吧 闭上眼睛就好'
          },{
          img: 'http://p2.music.126.net/LL943yz4fpJNBNFZcqA0jQ==/18917097556521701.jpg?param=140y140',
          title: '未来的女朋友 你好',
          pos: ['情感','抒情','唯美'],
          price: '作品《致女友》作者爱你的小北'
        },{
          img: 'http://p4.music.126.net/5lkYvRR4AEA7hUwfy21mag==/109951163170167818.jpg?param=200y200',
          title: ' | 游戏☆ | 视频剪辑☆ | 运动 | ',
          pos: ['电子', '兴奋', '孤独'],
          price: '美剧《天赋异禀》里面的北极星'
        },{
          img: 'http://p1.music.126.net/trJOYanWB1-xa6GwhQSb_g==/109951164199991295.jpg?param=140y140',
          title: '十年前的歌还在，陪你一起听歌的人呢',
          pos: ['华语', '流行', '怀旧'],
          price: '十年前，手机功能还极其...'
        }
        ],
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
