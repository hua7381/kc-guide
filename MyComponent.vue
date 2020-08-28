<template>
  <!-- 参考vuejs官方示例代码及风格指南：https://cn.vuejs.org/v2/style-guide/ -->
  <!-- 缩进统一为2个空格，缩进需对齐 -->
  <!-- 属性用双引号, js代码字符串用单引号，注意空格（逗号后、冒号后、大括号内两侧）-->
  <div @click="func1('val1', { aa: 1, bb: '2' })">
    <div class="btn-close">
      <!-- 注意此处空格 -->
      {{ aaa }}
    </div>
    <!-- 组件名单词大写开头 (PascalCase) -->
    <!-- 模板中属性名用短横线隔开（kebab-case） -->
    <!-- 有多个属性时，一行一个属性 -->
    <!-- 无内容时要‘自闭和’ -->
    <MyComponentSub1
      prop-of-cc="cc" 
      prop-of-dd="dd"
    />
    <MyComponentSub2
      v-show="xxxx"
      @click="func1()"
    />
  </div>
</template>

<script>
// 注释的双斜杠后有1个空格
// 组件命名大写开头 (PascalCase)
// 组件命名要使父子组件能‘按文件名排在一起’，体现父子关系
import MyComponentSub1 from '@/components/xxx/MyComponentSub1.vue'
import MyComponentSub2 from '@/components/xxx/MyComponentSub2.vue'
export default {
  components: { MyComponentSub1, MyComponentSub2 },// 注意空格
  props: {// 必须指定属性的类型
    propOfAa: String,
    propOfBb: Number
  },
  data() {
    return {
      aaa: 'xxx',
      ddd: {
        d1: 1,
        d2: 2
      }
    }
  },
  methods: {
    func1(param1, param2) {// 多个参数间逗号后1个空格，大括号前1空格
      if (this.aaa == '阿斯蒂芬') {// 空格: if条件前后、运算符前后
        this.ddd.d1 = 'xxx';
      }
    }
  }
}
</script>

<style scoped>
/* 除跟组件外，必须加scoped */
/* 尽量都用类选择器，避免用元素选择器 */
.btn-close {
  padding-top: 5px;
}
</style>