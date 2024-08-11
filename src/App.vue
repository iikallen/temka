<script setup>
import Header from './components/HeaderComponent.vue'
import CardList from './components/CardList.vue'
import axios from 'axios'
import { onMounted, ref, watch } from 'vue'

const items = ref([])
const sortBy = ref('')

const fetchItems = async (sort = '') => {
  try {
    const { data } = await axios.get(`https://your-api-url.com/items?sortBy=${sort}`)
    items.value = data
  } catch (error) {
    console.error('Error fetching items:', error)
  }
}

watch(sortBy, (newSortBy) => {
  fetchItems(newSortBy)
})

const onChangeSelect = (event) => {
  sortBy.value = event.target.value
}

onMounted(() => {
  fetchItems()
})
</script>

<template>
  <div class="bg-white m-20 shadow-xl rounded-xl">
    <Header />
    <div class="flex justify-between items-center mb-10 p-10">
      <div>
        <h1 class="text-3xl font-bold">Все продукты</h1>
      </div>

      <div class="flex items-center gap-4">
        <select
          @change="onChangeSelect"
          class="py-2 px-3 border border-gray-200 focus:border-gray-400 rounded-md focus:outline-none"
        >
          <option value="title">По названию</option>
          <option value="price">По цене (дешевые)</option>
          <option value="-price">По цене (дорогие)</option>
        </select>
        <div class="relative">
          <input
            type="text"
            class="border border-gray-200 rounded-md py-2 pl-10 pr-4 focus:outline-none focus:border-gray-400"
            placeholder="Поиск..."
          />
          <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
            <img src="/search.svg" alt="Search" />
          </div>
        </div>
      </div>
    </div>

    <CardList :items="items" />
  </div>
</template>

<style scoped>
/* Add any specific styles for the app here */
</style>
