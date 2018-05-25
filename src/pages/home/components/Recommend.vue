<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <img class="item-img" :src="item.imgUrl"/>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data () {
    return ({
      recommendList: [
        {
          id: '001',
          imgUrl: 'static/images/re1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        },
        {
          id: '002',
          imgUrl: 'static/images/re1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        },
        {
          id: '003',
          imgUrl: 'static/images/re1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        },
        {
          id: '004',
          imgUrl: 'static/images/re1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        }
      ]
    })
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
  .title {
    @include x-rem(margin-top, .2);
    @include x-rem(line-height, .8);
    background-color: #eee;
    @include x-rem(text-indent, .2);
  }
  .item {
    overflow: hidden;
    display: flex;
    @include x-rem(height, 1.9);
    .item-img {
      @include x-rem(height, 1.7);
      @include x-rem(width, 1.7);
      @include x-rem(padding, .1);
    }
    .item-info {
      flex: 1;
      @include x-rem(padding, .1);
      min-width: 0;
      .item-title {
        @include ellipsis;
        @include x-rem(line-height, .54);
        @include x-rem(font-size, .32);
      }
      .item-desc {
        @include ellipsis;
        @include x-rem(line-height, .4);
        color: #ccc;
      }
      .item-button {
        @include x-rem(margin-top, .16);
        background: #ff9300;
        @include x-rem(padding-top,0);
        @include x-rem(padding-bottom,0);
        @include x-rem(padding-left,.2);
        @include x-rem(padding-right,.2);
        @include x-rem(border-radius, .06);
        @include x-rem(line-height, .44);
        color: #fff
      }
    }
  }
</style>
