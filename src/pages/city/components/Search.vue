<template>
  <div class="search">
    <input type="text" placeholder="输入城市名字" class="search-input">
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>
<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';

.search {
  @include x-rem(height, .72);
  @include x-rem(padding-left, .1);
  @include x-rem(padding-right, .1);
  padding-top: 0;
  padding-bottom: 0;
  background: $bgColor;
  .search-input{
    width: 100%;
    box-sizing: border-box;
    text-align: center;
    @include x-rem(padding-left, .1);
    @include x-rem(padding-right, .1);
    padding-top: 0;
    padding-bottom: 0;
    @include x-rem(height, .62);
    @include x-rem(line-height, .62);
    @include x-rem(border-radius, .06);
    color:#666;
  }
}
</style>
