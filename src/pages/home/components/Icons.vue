<template>
  <div class="icons">
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
    <div class="icon">
      <div class="icon-img">
        <img class="icon-img-content" src="static/images/index-icon1.png" alt="">
      </div>
      <p class="icon-desc">
        热门景点
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons'
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
  .icons{
    width: 100%;
    height: 0;
    padding-bottom: 50%;
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
      }
    }
  }
</style>
