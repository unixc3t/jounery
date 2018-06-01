<template>
  <div>
    <ul class="list">
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet'
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
