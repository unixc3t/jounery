<template>
<div class="header">
  <div class="header-left">返回</div>
  <div class="header-input">输入城市/景点/游玩主题</div>
  <div class="header-right">城市</div>
</div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
@import '../../../assets/styles/base.scss';
.header {
  display: flex;
  background: #00bcd4;
  @include x-rem(line-height,.86);
  color: #fff;
  .header-left {
      @include x-rem(width,.64);
      float:left;
  }
  .header-input{
    flex:1;
    background: #fff;
    @include x-rem(height,.62);
    @include x-rem(line-height,.62);
    @include x-rem(margin-left,.2);
    @include x-rem(margin-top,.12);
    @include x-rem(border-radius,.1);
    color: #ccc;
  }
  .header-right{
    @include x-rem(width,1.24);
    float:right;
    text-align: center;
  }
}
</style>
