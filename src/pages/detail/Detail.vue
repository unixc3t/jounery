<template>
  <div>
    <banner/>
    <detail-header/>
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from './components/Banner'
import DetailHeader from './components/Header'
export default {
  components: {
    Banner,
    DetailHeader
  },
  name: 'Detail'
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.content {
  @include x-rem(height, 50)
}
</style>
