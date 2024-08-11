<template>
  <div class="user-profile">
    <header class="profile-header">
      <img class="profile-avatar" :src="user.avatar" alt="User Avatar" />
      <h1 class="profile-name">{{ user.name }}</h1>
      <p class="profile-email">{{ user.email }}</p>
    </header>
    <section class="profile-details">
      <h2>About Me</h2>
      <p>{{ user.bio }}</p>
    </section>
    <section class="profile-actions">
      <button @click="editProfile">Edit Profile</button>
      <button @click="logout">Logout</button>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

// Логика компонента
const router = useRouter();

// Пример данных о пользователе
const user = ref({
  name: 'John Doe',
  email: 'john.doe@example.com',
  avatar: '/images/avatar.jpg',
  bio: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent euismod.'
});

const editProfile = () => {
  router.push('/edit-profile'); // Перенаправление на страницу редактирования профиля
};

const logout = () => {
  // Логика выхода из системы
  console.log('User logged out');
  router.push('/login'); // Перенаправление на страницу входа
};
</script>

<style scoped>
.user-profile {
  padding: 20px;
  font-family: Arial, sans-serif;
}

.profile-header {
  text-align: center;
  margin-bottom: 20px;
}

.profile-avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #007bff;
}

.profile-name {
  font-size: 2em;
  color: #333;
}

.profile-email {
  font-size: 1.2em;
  color: #666;
}

.profile-details {
  margin-bottom: 20px;
}

.profile-details h2 {
  font-size: 1.5em;
  color: #333;
}

.profile-details p {
  font-size: 1em;
  color: #666;
}

.profile-actions {
  text-align: center;
}

.profile-actions button {
  margin: 0 10px;
  padding: 10px 20px;
  font-size: 1em;
  color: #fff;
  background-color: #007bff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.profile-actions button:hover {
  background-color: #0056b3;
}
</style>
