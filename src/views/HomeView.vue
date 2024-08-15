<template>
  <div class="flex flex-col gap-10">
    <h1 class="text-center">Users list</h1>
    <div class="flex flex-row justify-center text-center">
      <input type="text" placeholder="Filter users" v-model="search" @keyup="handleSearch" class="text-center">
    </div>
    <div class="flex flex-row gap-10 justify-center">
      <button @click="handleLayout(ListLayout)" class="btn">List</button>
      <button @click="handleLayout(CardLayout)" class="btn">Cards</button>
      <button @click="handleLayout(TableLayout)" class="btn">Table</button>
    </div>
    <component :is="layout" :content="filteredUsers" class="text-center" />
  </div>
</template>

<script lang="ts" setup>
import { ref, defineAsyncComponent, type Component } from 'vue'

const ListLayout = defineAsyncComponent(() => import('@/layouts/ListLayout.vue'))
const CardLayout = defineAsyncComponent(() => import('@/layouts/CardLayout.vue'))
const TableLayout = defineAsyncComponent(() => import('@/layouts/TableLayout.vue'))

const layout = ref<Component>(ListLayout)

const handleLayout = (cmp: Component) => layout.value = cmp

const search = ref('')

const handleSearch = () => {
  filteredUsers.value = users.value.filter(item => item.name.toLowerCase().includes(search.value.toLowerCase()))
}

const users = ref([
  { name: 'John', age: 25, position: 'frontend' },
  { name: 'Jane', age: 24, position: 'backend' },
  { name: 'Jack', age: 26, position: 'fullstack' },
  { name: 'Ana', age: 41, position: 'frontend' },
  { name: 'Roberto', age: 53, position: 'backend' },
  { name: 'Maria', age: 35, position: 'fullstack' },
])

const filteredUsers = ref<{ name: string; age: number; position: string; }[]>([])

filteredUsers.value = users.value

</script>

<style lang="css" scoped>
.btn {
  @apply bg-blue-700 text-white font-bold py-2 px-4 rounded;
}
</style>