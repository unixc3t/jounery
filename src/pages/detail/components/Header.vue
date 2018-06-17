<template>
 <div>
   <router-link  tag="div" to="/" class="header-abs" v-show="showAbs">
     <div class="iconfont header-abs-back">&#xe600;</div>
   </router-link>
   <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
    <router-link to="/">
      <div class="iconfont header-fixed-back">&#xe600;</div>
    </router-link>
     website info
   </div>
 </div>
</template>

<script>
export default {
  name: 'DetailHeade',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }

    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';

.header-abs {
  position: absolute;
  @include x-rem(top, .2);
  @include x-rem(left, .2);
  @include x-rem(width, .8);
  text-align: center;
  line-height: .8rem;
  @include x-rem(height, .8);
  @include x-rem(border-radius, .4);
  background: rgba(0,0,0, .8);
  .header-abs-back {
    color: #fff;
  @include x-rem(font-size, .4);
  }

}

.header-fixed {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    overflow: hidden;
    @include x-rem(height, $headerHeight);
    @include x-rem(line-height, $headerHeight);
    text-align: center;
    color: #fff;
    background: $bgColor;
    @include x-rem(font-size, .3);

    .header-fixed-back {
      position: absolute;
      top:0;
      left:0;
      @include x-rem(width, .64);
      text-align: center;
      @include x-rem(font-size, .4);
      color: #fff;
    }
  }
</style>
