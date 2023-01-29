<template>
  <div class="app-container">
    <h1>App 根组件</h1>
    <hr />
    <button @click="comName = 'Left'">显示Left</button>
    <button @click="comName = 'Right'">显示Right</button>
    <div class="box">

      <!-- 渲染 Left 组件和 Right 组件 -->
      <keep-alive include="Left">
        <component :is="comName"></component>
      </keep-alive>

      <!-- 组件中内容默认填充到default插槽中 -->
      <Left>
        <!-- 填充到指定名称的插槽 -->
        <template v-slot:default>
          <p>这是一个p标签</p>
        </template>
        <!-- 简写形式 -->
        <template #pspan>
          <span>这是一个span标签</span>
        </template>
      </Left>
    </div>

    <Article>
      <template #title>
        <h2>一首诗</h2>
      </template>
      <template #content="{ msg, user }">
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Optio quasi necessitatibus dignissimos cupiditate
        libero tempore? Iure fugit nesciunt, laboriosam a recusandae praesentium! Tenetur in, ipsam repudiandae est modi
        id sit!
        <p>{{ msg }}</p>
        <p>{{ user.uname }}</p>
      </template>
      <template #author>
        <span>作者:张三</span>
      </template>
    </Article>
  </div>
</template>

<script>
import Left from '@/components/Left.vue'
import Right from '@/components/Right.vue'
import Article from '@/components/Article.vue'

export default {
  data() {
    return {
      comName: 'Left'
    }
  },
  components: {
    Left,
    Right,
    Article,
  },

}
</script>

<style lang="less">
.app-container {
  padding: 1px 20px 20px;
  background-color: #efefef;
}

.box {
  display: flex;
}
</style>
