<template>
<div class="header">
  <div class="header-left">
    <div class="iconfont icon-back">&#xe600;</div>
  </div>
  <div class="header-input">
    <span class="iconfont">&#xe612;</span>输入城市/景点/游玩主题</div>
  <div class="header-right">城市
    <span class="iconfont arrow-icon">&#xe61c;</span>
  </div>
</div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.header {
  display: flex;
  background: $bgColor;
  @include x-rem(line-height,.86);
  color: #fff;
  .header-left {
      @include x-rem(width,.64);
      float:left;
      .icon-back{
        text-align: center;
        @include x-rem(font-size,.4)
      }
  }
  .header-input{
    flex:1;
    background: #fff;
    @include x-rem(height,.62);
    @include x-rem(line-height,.62);
    @include x-rem(margin-left,.2);
    @include x-rem(padding-left,.2);
    @include x-rem(margin-top,.12);
    @include x-rem(border-radius,.1);
    color: #ccc;
  }
  .header-right{
    @include x-rem(width,1.24);
    float:right;
    text-align: center;
    .arrow-icon{
      @include x-rem(font-size,.2);
      @include x-rem(margin-left,-.04);
    }
  }
}
</style>
