<template>
  <div class="icons" >
      <swiper :options="swiperOption">
        <swiper-slide v-for="(page, index) of pages" :key="index">
          <div class="icon" v-for="item of pages[index]" :key="item.id">
            <div class="icon-img">
              <img class="icon-img-content" :src="item.imgUrl" alt="">
            </div>
            <p class="icon-desc">
              {{item.desc}}
            </p>
          </div>
      </swiper-slide>
         <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return ({
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: false
      },
      iconList: [
        {
          id: '0001',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0002',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0003',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0004',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0005',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0006',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0007',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0008',
          imgUrl: 'static/images/icon-index1.png',
          desc: '景点门票'
        }, {
          id: '0009',
          imgUrl: 'static/images/icon-index2.png',
          desc: '必游榜单'
        }

      ]
    })
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }

        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
  .icons >>> .swiper-container{
    height: 0;
    padding-bottom: 50%;
  }
   .icon{
      position: relative;
      float: left;
      width: 25%;
      height: 0;
      padding-bottom: 25%;
      .icon-img{
        position: absolute;
        top:0;
        left:0;
        right:0;
        @include x-rem(bottom,.22);
        box-sizing: border-box;
        @include x-rem(padding,.1);
        .icon-img-content {
          display: block;
          margin: 0 auto;
          height: 100%;
        }
      }
      .icon-desc{
        position: absolute;
        left:0;
        right:0;
        bottom:0;
        @include x-rem(line-height,.44);
        @include x-rem(height,.44);
        text-align: center;
        color:$darkTextColor;
        @include ellipsis;
      }
    }
</style>
