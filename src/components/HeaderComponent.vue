<template>
  <header class="flex items-center justify-between p-10">
    <div class="flex gap-4 items-center">
      <img class="w-12" src="/logo.png" alt="Logo" />
      <div>
        <h1 class="font-bold text-xl">VUE FOOD</h1>
        <p class="text-gray-400">Магазин свежих продуктов</p>
      </div>
    </div>
    <ul class="flex gap-10 items-center">
      <li class="flex gap-2 items-center transition hover:font-bold cursor-pointer">
        <img src="/cart.svg" alt="Cart" />
        <b class="text-gray-500">17000 тенге</b>
      </li>
      <li class="flex gap-2 items-center transition hover:font-bold cursor-pointer">
        <img src="/heart.svg" alt="Favorites" />
        <span class="text-gray-500">Закладки</span>
      </li>
      <li class="flex gap-2 items-center transition hover:font-bold cursor-pointer">
        <img src="/profile.svg" alt="Profile" />
        <span class="text-gray-500">Профиль</span>
      </li>
    </ul>
  </header>
</template>

<script setup>
</script>

<style scoped>
/* Add any specific styles for the header here */
</style>
