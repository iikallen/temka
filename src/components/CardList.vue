<script setup>
import FoodItem from './FoodItem.vue'

defineProps({
  items: Array
})

const onClickAdd = () => {
  alert('Добавлено в корзину!')
}
</script>

<template>
  <div class="p-10 grid grid-cols-4 gap-5">
    <FoodItem
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :image="item.imageUrl"
      :price="item.price"
      :isAdded="item.isAdded"
      :isFavourite="item.isFavourite"
      :onClickAdd="onClickAdd"
    />
  </div>
</template>

<style scoped>
/* Add any specific styles for the card list here */
</style>
