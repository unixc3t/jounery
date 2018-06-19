<template>
  <div>
    <ul class="list">
      <li class="item" v-for="item of letters" :key="item" @click="clickKey"
      :ref = "item"
      @touchstart.prevent = "handleStart"
      @touchmove = "handleMove"
      @touchend = "handleEnd" >{{item}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    clickKey (e) {
      this.$emit('change', e.target.innerText)
    },
    handleStart () {
      this.touchStatus = true
    },
    handleMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          let clientY = e.touches[0].clientY - 79
          const index = Math.floor((clientY - this.startY) / 20)
          if (index >= 0 && index <= this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleEnd () {
      this.touchStatus = false
    }
  }
}
</script>
<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.list {
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  @include x-rem(top, 1.58);
  right: 0;
  bottom: 0;
  @include x-rem(width, .4);
  .item {
    @include x-rem(line-right, .4);
    text-align: center;
    color: $bgColor;
  }

}
</style>
