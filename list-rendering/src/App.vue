<script setup>
import { reactive } from 'vue'
import { ref } from 'vue'
import MyComponent from './components/MyComponent.vue'

const parentMessage = ref('Parent')
const items = ref([
  {
    message1: 'Foo1',
    message2: 'Foo2',
    message3: 'Foo3',
    children: [
      'child1',
      'child2',
      'child3'
    ]
  },
  {
    message1: 'Bar1',
    message2: 'Bar2',
    message3: 'Bar3',
    children: [
      'child4',
      'child5',
      'child6'
    ]
  }
])

const myObject = reactive({
  title: 'How to do lists in vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})
</script>

<template>
  <div>
    <h1>v-for</h1>
    
    <h3>エイリアス</h3>
    <li v-for="(item, index) in items">
      {{ parentMessage }} - {{ index }} - {{ item.message1 }}
    </li>

    <h3>分割代入</h3>
    <li v-for="({message1, message3}, index) in items">
      {{ parentMessage }} - {{ index }} - {{ message1 }} - {{ message3 }}
    </li>

    <h3>親のスコープ</h3>
    <li v-for="item in items">
      {{ item.message1 }}
      <span v-for="childItem in item.children">
        <div>
          {{ childItem }}
        </div>
      </span>
    </li>

  </div>

  <div>
    <h1>v-forをオブジェクトに適用する</h1>

    <h3>エイリアス(値)</h3>
    <ul>
      <li v-for="value in myObject">
        {{ value }}
      </li>
    </ul>

    <h3>エイリアス(キー、値)</h3>
    <ul>
      <li v-for="(value, key) in myObject">
        {{ key }} : {{ value }}
      </li>
    </ul>

  </div>

  <div>
    <h1>v-forで範囲を使用する</h1>
    <span v-for="(n, index) in 10">
      <template v-if="index === 0">{{ n }}</template>
      <template v-else>,{{ n }}</template>
    </span>
  </div>

  <div>
    <h1>&lt;template&gt;にv-forを適用する</h1>
    <ul>
      <template v-for="item in items">
        <li>{{ item.message1 }}</li>
        <li class="divider" role="presentation">divider</li>
      </template>
    </ul>
  </div>

  <div>
    <h1>v-forをコンポーネントに適用する</h1>
    <MyComponent
      v-for="(item, index) in items"
      :item="item"
      :key="index"
    />
  </div>

</template>

<style scoped></style>
