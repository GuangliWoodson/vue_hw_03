<template>
  <button :class="`one-button-${type}`" @click="clickFn">{{ title }}</button>
</template>

<script>
// 需求： 要求 title 和背景颜色自定义
export default {
  props: {
    title: String,
    type: {
      type: String,
      default: "primary",
      validator: (val) => {
        // val type 传递进来的值
        // return true 验证通过
        return ["primary", "success", "warning", "danger"].includes(val)
      }
    },
  },
  methods: {
      clickFn() {
        this.$emit("click1")
      }
    }
};
</script>

<style scoped>
button {
  color: #fff;
  outline: none;
  border: none;
  padding: 8px 24px;
  border-radius: 4px;
  font-size: 18px;
}
.one-button-primary {
  background-color: skyblue;
}
.one-button-success {
  background-color: hotpink;
}
.one-button-warning {
  background-color: yellow;
}
.one-button-danger {
  background-color: red;
}
</style>
