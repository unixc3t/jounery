<template>
<div class="list" ref="wrapper">
  <div>
  <div class="area">
    <div class="title border-topbottom">当前城市</div>
    <div class="button-list">
       <div class="button-wrapper">
         <div class="button">北京</div>
       </div>
    </div>
  </div>
  <div class="area">
    <div class="title border-topbottom">热门城市</div>
    <div class="button-list">
       <div class="button-wrapper" v-for="city of hot" :key="city.id">
         <div class="button">{{city.name}}</div>
       </div>
    </div>
  </div>
  <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
    <div class="title border-topbottom">{{key}}</div>
    <div class="item-list">
      <div class="item border-bottom" v-for="city of item" :key="city.id">
        {{city.name}}
      </div>
    </div>
  </div>
  </div>
</div>
</template>
<script>
import Bscroll from 'better-scroll'

export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>
<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.border-topbottom {
  &:before {
    border-color: #ccc;
  }
  &:after {
    border-color: #ccc;
  }
}
.border-bottom {
  &:before {
    border-color: #ccc;
  }
}
.list{
  position: absolute;
  overflow: hidden;
  @include x-rem(top, 1.58);
  right:0;
  left:0;
  bottom:0;
.title {
  @include x-rem(line-height, .54);
  background: #eee;
  @include x-rem(padding-left, .2);
  color: #666;
  @include x-rem(font-size, .26);
}
.button-list {
  overflow: hidden;
  @include x-rem(padding, .1, .6rem, .1rem, .1rem);
  .button-wrapper {
    float: left;
    width: 33.33%;
    .button {
      @include x-rem(margin, .1);
      text-align: center;
      @include x-rem(border, .02, solid, #ccc);
      @include x-rem(padding, .1, 0);
      @include x-rem(border-radius, .06)
    }
  }
}
.item-list {
  .item {
    @include x-rem(line-height, .76);
    color: #666;
    @include x-rem(padding-left, .2);
  }
}
}
</style>
