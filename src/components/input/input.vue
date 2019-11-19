<template>
  <div class="app-component">
    <input
      ref="cyyInput"
      @focus="cyyFocusInput"
      @blur="cyyBlurInput"
      :value="value"
      @input="input"
      :placeholder="placeholder"
      :style="{
            backgroundColor:backgroundColor,
            width:width,
        }"
      class="cyy-inputFirst"
      type="text">
  </div>
</template>

<script>
export default {
  name: '',
  components: {},
  computed: {},
  props: ['backgroundColor', 'placeholder', 'width', 'value'],
  data () {
    return {}
  },
  created () {},
  mounted () {},
  methods: {
    // 获得焦点为input标签添加边框
    cyyFocusInput () {
      this.$refs.cyyInput.style.border = '1px solid rgb(3,169,244)'
    },
    // 失去焦点将input标签的边框设置为默认值
    cyyBlurInput () {
      this.$refs.cyyInput.style.border = '1px solid rgb(150,150,150)'
    },
    // 实现v-modle的功能
    input () {
      this.$emit('input', event.target.value)
    }
  },
  destroyed () {}
}
</script>

<style scoped>
  .cyy-inputFirst {
    border: 1px solid rgb(150, 150, 150);
    border-radius: 10px;
    outline: none;
    padding-left: 5px;
    height: 25px;
    width: 200px;
    margin: 6px;
  }
</style>
