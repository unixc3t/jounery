<template>
  <div class="container" @click = "getHandleClick">
  <div class="wrapper">
     <swiper :options="swiperOptions">
    <swiper-slide v-for = "(item, key) of imgs" :key = "key">
      <img  class="gallary-img" :src="item">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    getHandleClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.container >>> .swiper-pagination {
  overflow: inherit;
}
  .container {
    display: flex;
    position: fixed;
    z-index: 99;
    flex-direction: column;
    justify-content: center;
    left:0;
    right: 0;
    top:0;
    bottom: 0;
    background: #000;
    .wrapper {
      width: 100%;
      height: 0;
      padding-bottom: 100%;
      .gallary-img {
        width:100%;
      }
      .swiper-pagination {
        color: #fff;
        @include x-rem(bottom, 0.1);
      }
    }
  }
</style>
