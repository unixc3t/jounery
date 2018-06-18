<template>
  <div>
    <div class="item" v-for="(item, index) of list" :key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list = "item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';

  .item-title-icon {
    display: inline-block;
    position: relative;
    width: .36rem;
    height: .36rem;
    top: .06rem;
    left: .06rem;
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right: .1rem;
    background-size: .4rem 3rem;
  }
  .item-title {
    @include x-rem(line-height, .8);
    @include x-rem(font-size, .32);
    @include x-rem(font-size, .2);
    padding-top: 0;
    padding-bottom: 0;
    @include x-rem(padding-left, .2);
    @include x-rem(padding-right, .2);
  }
  .item-children {
    padding: 0 .2rem;
  }
</style>
