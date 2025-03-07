<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink class="router-link" to="/">Главная страница</RouterLink>
        <RouterLink class="router-link" to="/about">Обо мне</RouterLink>
        <RouterLink class="router-link" to="/prices">Цены</RouterLink>
        <RouterLink class="router-link" to="/clients">Клиенты</RouterLink>
        <div class="contact-info">
          <span class="address">г. Казань, ул. Кави Наджми 8, офис. 23</span>
          <div class="phone">+7 960 087-20-86</div>
        </div>
      </nav>
    </div>
  </header>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

nav {
  width: 100%;
  font-size: 15px;
  text-align: center;
  padding: 1rem 0;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}

nav a.router-link-exact-active {
  color: var(--color-text);
  font-weight: 500;
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

.contact-info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-left: 1rem;
}

.contact-info .address {
  white-space: nowrap;
}

@media (max-width: 707px) {
  .contact-info {
    display: none;
  }

  .router-link {
    font-size: 13px;
  }
}
</style>
