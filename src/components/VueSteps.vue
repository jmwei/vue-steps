<template>
  <div class="the-steps">
    <div class="the-steps-item" v-for="(item, index) in items" :key="index">
      <div :class="['the-steps-item-num', activeIndex >= index ? 'activeImage' : '']">
        <span v-if="activeIndex < index">{{item.num}}</span>
      </div>
      <div :class="['the-steps-item-text', activeIndex >= index ? 'activeText' : '']">{{item.text}}</div>
      <div :class="['the-steps-item-line', activeIndex >= index ? 'activeLine' : '']"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VueSteps',
  props: {
    items: {
      type: Array
    },
    activeIndex: {
      type: Number,
      default: 0
    }
  }
}
</script>

<style lang='scss'>
.the-steps {
  width: 100%;
  display: flex;
  &-item {
    display: flex;
    width: 100%;
    height: 34px;
    &:last-child {
      width: 45%;
      .the-steps-item-line {
        display: none;
      }
    }
    &-num {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      line-height: 30px;
      color: #00000072;
      text-align: center;
    }
    &-text {
      color: #00000072;
      font-size: 16px;
      line-height: 30px;
      margin-left: 10px;
    }
    &-line {
      flex: 1;
      height: 1px;
      background: #ccc;
      margin: 15px 15px 0;
    }

    .activeImage {
      width: 30px;
      height: 30px;
      background: url(../assets/icon-success.png) no-repeat;
      background-size: 100%;
    }
    .activeText {
      color: #000000d8;
      font-size: 16px;
      font-weight: 700;
    }
    .activeLine {
      color: #fff;
      background: #1890ff;
    }
  }
}
</style>
