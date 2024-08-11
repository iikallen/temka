<template>
  <div
    class="border p-8 border-slate-200 rounded-3xl relative cursor-pointer transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      class="absolute top-4 left-4"
      :src="isFavourite ? '/like-2.svg' : '/like-1.svg'"
      alt="Like"
    />
    <img class="w-52 h-52 object-contain" :src="image" alt="Food Item" />
    <p>{{ title }}</p>
    <div class="flex justify-between items-center">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена:</span>
        <span class="font-bold">{{ price }} тенге</span>
      </div>
      <img @click="handleAddClick" :src="isAdded ? '/checked.svg' : '/plus.svg'" alt="Add" />
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  image: {
    type: String,
    required: true
  },
  price: {
    type: Number,
    required: true
  },
  isAdded: {
    type: Boolean,
    required: true
  },
  isFavourite: {
    type: Boolean,
    required: true
  },
  onClickAdd: {
    type: Function,
    required: true
  }
});

const handleAddClick = () => {
  props.onClickAdd();
};
</script>

<style scoped>
/* Add any specific styles for the food item here */
</style>
