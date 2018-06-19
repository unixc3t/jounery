<template>
<div>
  <div class="banner" @click = "showClickBanner">
      <img class="banner-img" :src="bannerImg" alt="" />
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe612;</span>
            {{this.bannerImgs.length}}
          </div>
      </div>
  </div>
  <fade-animation>
    <common-gallary :imgs="imgs" v-show="showGallary" @close = "gallaryClose"/>
  </fade-animation>
</div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/201403/10/6a18aabe4e02e211552c25da2c8d6c93.jpg_1190x550_e128d7d3.jpg',
        'http://img1.qunarzz.com/sight/p0/201403/10/f78fd60f6201bdc1f536c8f31941e306.jpg_1190x550_e26db53f.jpg'],
      showGallary: false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  methods: {
    showClickBanner () {
      this.showGallary = true
    },
    gallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 48%;
  .banner-img {
    width: 100%;
  }
  .banner-info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    color:#fff;
    @include x-rem(line-height, .6);
    .banner-title {
      flex: 1;
      @include x-rem(font-size, .32);
      padding-top: 0;
      padding-bottom: 0;
      @include x-rem(padding-left, .2);
      @include x-rem(padding-right, .2);
    }
   .banner-number {
      padding-top: 0;
      padding-bottom: 0;
      @include x-rem(padding-left, .4);
      @include x-rem(padding-right, .4);
      @include x-rem(line-height, .4);
      @include x-rem(margin-top, .1);
      @include x-rem(height, .32);
      @include x-rem(border-radius, .2);
      background: rgba(0, 0, 0, .8);
      @include x-rem(font-size, .24);
      .banner-icon {
        @include x-rem(font-size, .24);
      }
   }

  }
}
</style>
