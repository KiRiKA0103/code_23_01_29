<template>
  <div class="left-container">
    <h3>Left 组件</h3>
    <!-- 插槽默认内容 -->
    <slot>这是插槽的默认内容</slot>
    <slot name="pspan"></slot>

  </div>
</template>

<script>
export default {
  // 当提供了name属性之后 组件名称就是name属性值
  // 1. 组件的注册名称主要应用场景 以标签形式渲染到页面结构
  // 2. 组件声明时name名称主要应用场景 <keep-alive>中使用 调试页面看到
  // name: 'MyLeft',

  // 组件第一次被创建时 执行created生命周期函数和activated生命周期函数
  // 组件被激活时 只执行activated生命周期函数
  activated() {

  },
  deactivated() {

     
  },
}
</script>

<style lang="less">
.left-container {
  padding: 0 20px 20px;
  background-color: orange;
  min-height: 250px;
  flex: 1;
}
</style>
