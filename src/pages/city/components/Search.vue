<template>
  <div>
    <div class="search">
      <input type="text" v-model="keyword" placeholder="输入城市名字" class="search-input">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for = "item of list" :key="item.id" >{{item.name}}</li>
        <li class="search-item border-bottom" v-show = "hasNoData">没有找到数据</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }

      if (!this.keyword) {
        this.list = []
        return
      }

      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (value.spell.indexOf(this.keyword) > -1 ||
                  value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }

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
    color: #666;
  }
}
.search-content {
  z-index: 1;
  overflow: hidden;
  position: absolute;
  @include x-rem(top, 1.58);
  left:0;
  right: 0;
  bottom: 0;
  background: #eee;
  .search-item {
    @include x-rem(line-height, .62);
    @include x-rem(padding-left, .2);
    background: #fff;
    color: #666
  }

}
</style>
