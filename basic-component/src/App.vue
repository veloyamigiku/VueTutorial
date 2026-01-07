<script setup>
import { ref } from 'vue'
import BlogPost from './components/BlogPost.vue'
import ButtonCounter from './components/ButtonCounter.vue'
import AlertBox from './components/AlertBox.vue'

const posts = ref([
  {
    id: 1,
    title: 'My journey with Vue'
  },
  {
    id: 2,
    title: 'Blogging with Vue'
  },
  {
    id: 3,
    title: 'Why Vue is so fun'
  }
])
const postFontSize = ref(1)

const currentTab = ref('AlertBox')
const tabs = {
  //'AlertBox': AlertBox,
  AlertBox,
  //'ButtonCounter': ButtonCounter,
  ButtonCounter
}
</script>

<template>
  <h1>コンポーネントの基礎</h1>
  <div>
    <h2>コンポーネントの定義・使用</h2>
    <h3>Here is a child component!</h3>
    <ButtonCounter />
  </div>
  <div>
    <h2>propsの受け渡し</h2>
    <BlogPost title="SampleTitle" />
  </div>
  <div>
    <h2>propsの受け渡し(v-for)</h2>
    <BlogPost
      v-for="post in posts"
      :key="post.id"
      :title="post.title" />
  </div>
  <div>
    <h2>イベントの購読</h2>
    <div :style="{ fontSize: postFontSize + 'em'}">
      <BlogPost
        v-for="post in posts"
        :key="post.id"
        :title="post.title"
        @enlarge-text="postFontSize += 0.1" />
    </div>
  </div>
  <div>
    <h2>スロットを使ったコンテンツ配信</h2>
    <AlertBox>
      何らかのエラーが発生しました。
    </AlertBox>
  </div>
  <div>
    <h2>動的コンポーネント</h2>
    <button
      v-for="(_, tab) in tabs"
      :key="tab"
      @click="currentTab = tab"
    >
      {{ tab }}
    </button>
    <component :is="tabs[currentTab]"></component>
  </div>
</template>

<style scoped></style>
