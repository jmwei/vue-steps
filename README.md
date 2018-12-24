# Vue 进度条

*一款基于Vue的建议进度条组件*

### 使用用例

```
<template>
  <div class="step">
    <VueSteps :items="items" :activeIndex='activeIndex' />
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
  }
}
</script>
```

### 示例

![Steps](https://github.com/jmwei/vue-steps/blob/master/src/assets/step.gif "Steps")
