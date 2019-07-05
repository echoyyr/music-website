<template>
  <div class="slide">
    <el-carousel height="240px">
      <el-carousel-item v-for="item in list" :key="item.img">
        <img :src="item.img" alt="">
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
<script>
export default {
  data: () => {
    return {
      list: [{
        url: '#abc',
        img: 'http://business.cdn.qianqian.com/qianqian/pic/bos_client_15621500494850ffb84f18a13a52793f18633f12c6.jpg@s_2,w_750,h_300'
      }, {
        url: '#bsbsb',
        img: 'http://business.cdn.qianqian.com/qianqian/pic/bos_client_156169410749dc342549b3b9c34d402305b5438aef.jpg@s_2,w_750,h_300'
      }, {
        url: '#sjfkajfj',
        img: 'http://business.cdn.qianqian.com/qianqian/pic/bos_client_1547466371f5a8864429456f49e904ab0430b8dc17.jpg@s_2,w_750,h_300'
      }, {
        url: '#sjfkajfja',
        img: 'http://business.cdn.qianqian.com/qianqian/pic/bos_client_15620524458c13f73bce9f0e9d7cef82896b9e6a8a.jpg@s_2,w_750,h_300'
      }, {
        url: '#kjljj',
        img: 'http://business.cdn.qianqian.com/qianqian/pic/bos_client_1561951684ca8e283f0cb726ec627b7aa533c9925b.jpg@s_2,w_750,h_300'
      }]
    }
  }
}
</script>
