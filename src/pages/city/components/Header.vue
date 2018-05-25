<template>
  <div class="header">
    城市选择
    <router-link to="/">
    <div class="iconfont header-back">&#xe600;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
  .header {
    position: relative;
    overflow: hidden;
    @include x-rem(height, $headerHeight);
    @include x-rem(line-height, $headerHeight);
    text-align: center;
    color: #fff;
    background: $bgColor;
    @include x-rem(font-size, .3);
    .header-back {
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
