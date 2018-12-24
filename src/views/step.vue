<template>
  <div class="step">
    <VueSteps :items="items" :activeIndex='activeIndex' />
    <div class="step-infos">
      <div v-if="activeIndex === 0">
      </div>
      <div v-if="activeIndex === 1">
      </div>
      <div v-if="activeIndex === 2">
      </div>
      <div v-if="activeIndex === 3">
      </div>
    </div>
    <div class="step-btn">
      <button class="next" @click="next">下一步</button>
    </div>
  </div>
</template>

<script>
import VueSteps from '@/components/VueSteps.vue'
export default {
  name: 'Step',
  components: {
    VueSteps
  },
  data() {
    return {
      activeIndex: 0,
      items: [
        {
          num: '1',
          text: '基础信息'
        },
        {
          num: '2',
          text: '扫描计划'
        },
        {
          num: '3',
          text: '扫描目标'
        },
        {
          num: '4',
          text: '完成'
        }
      ]
    }
  },
  methods: {
    next() {
      if (this.activeIndex++ > 2) {
        this.activeIndex = 0
      }
    }
  }
}
</script>

<style lang="scss">
.step {
  width: 800px;
  height: 545px;
  margin: 20px;
  background: #fff;
  padding: 15px;
  padding: 30px 50px;
  .step-infos {
    width: 55%;
    height: 50px;
    margin: 35px auto 0;
  }
  .step-btn {
    text-align: center;
    .next {
      cursor: pointer;
      outline: none;
      color: #409eff;
      background: #ecf5ff;
      border-color: #b3d8ff;
      border-radius: 3px;
      padding: 5px 10px;
    }
  }
}
</style>
