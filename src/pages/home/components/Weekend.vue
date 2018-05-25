
<template>
  <div>
    <div class="title">今天去哪了</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
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
          imgUrl: 'static/images/week1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        },
        {
          id: '002',
          imgUrl: 'static/images/week1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        },
        {
          id: '003',
          imgUrl: 'static/images/week1.jpg',
          title: '大连生涯汉阳世界',
          desc: '浪漫大连首站,浪漫的涵养主题乐园'
        },
        {
          id: '004',
          imgUrl: 'static/images/week1.jpg',
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

  .item-img-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 37.09%;
  }

    .item-img {
      width:100%;
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
    }
</style>
