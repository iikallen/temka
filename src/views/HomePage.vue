<template>
  <div class="home-page">
    <header class="hero">
      <h1>Добро пожаловать в наш магазин!</h1>
      <p>Здесь вы найдете лучшие продукты для вашего дома.</p>
      <button @click="navigateToProducts">Посмотреть продукты</button>
    </header>
    <section class="featured">
      <h2>Рекомендуемые продукты</h2>
      <div class="product-list">
        <div class="product" v-for="product in featuredProducts" :key="product.id">
          <img :src="product.image" :alt="product.title" />
          <h3>{{ product.title }}</h3>
          <p>{{ product.price }} тенге</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

// Логика компонента
const router = useRouter();

const navigateToProducts = () => {
  router.push('/products'); // Перенаправление на страницу продуктов
};

// Пример данных для демонстрации
const featuredProducts = ref([
  { id: 1, title: 'Продукт 1', price: 5000, image: '/images/product1.jpg' },
  { id: 2, title: 'Продукт 2', price: 3000, image: '/images/product2.jpg' },
  { id: 3, title: 'Продукт 3', price: 7000, image: '/images/product3.jpg' }
]);
</script>

<style scoped>
.home-page {
  padding: 20px;
  font-family: Arial, sans-serif;
}

.hero {
  text-align: center;
  margin-bottom: 20px;
}

.hero h1 {
  font-size: 2em;
  color: #333;
}

.hero p {
  font-size: 1.2em;
  color: #666;
}

.hero button {
  padding: 10px 20px;
  font-size: 1em;
  color: #fff;
  background-color: #007bff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.featured {
  margin-top: 20px;
}

.featured h2 {
  font-size: 1.5em;
  color: #333;
}

.product-list {
  display: flex;
  gap: 10px;
  overflow-x: auto;
}

.product {
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 10px;
  text-align: center;
  width: 150px;
}

.product img {
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.product h3 {
  font-size: 1em;
  color: #333;
}

.product p {
  font-size: 0.9em;
  color: #666;
}
</style>
