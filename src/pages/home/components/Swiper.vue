  <template>
  <div class="wrapper">
  <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img  class="swiper-img" :src="item.url">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '1',
          url: 'static/images/index1.jpg'},
        {
          id: '2',
          url: 'static/images/index2.jpg'}
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.wrapper /deep/ .swiper-pagination-bullet-active{
  background: #fff;
}
.wrapper {
  overflow: hidden;
  width: 100%;
  height:0;
  padding-bottom: 26.66%;
  .swiper-img {
    width:100%;
  }
}
</style>
