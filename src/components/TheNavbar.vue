<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink class="router-link link-main-page" to="/">Главная&nbsp;страница</RouterLink>
        <RouterLink class="router-link link-about" to="/about">Обо&nbsp;мне</RouterLink>
        <RouterLink class="router-link" to="/prices">Цены</RouterLink>
        <RouterLink class="router-link" to="/clients">Клиенты</RouterLink>
        <RouterLink class="router-link" to="/learning">Обучение</RouterLink>
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
  font-size: 18px;
  text-align: center;
  padding: 1.2rem 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}

nav a.router-link-exact-active {
  color: var(--color-text);
  font-weight: 500;
}

/*nav a.router-link-exact-active:hover {*/
/*  background-color: transparent;*/
/*}*/

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

@media (max-width: 684px) {
  header {
    margin-bottom: 5px;
  }

  .contact-info {
    display: none;
  }

  nav {
    background-color: #fff;
    border-bottom: 1px solid var(--color-border);
    border-top: 1px solid var(--color-border);
    padding: 0;
  }

  nav a.router-link-exact-active {
    background-color: #e4e4e4;
  }

  .router-link {
    line-height: 1.1;
    font-size: 18px;
    /*background-color: #dcdcdc;*/
    padding: 12px 10px;
  }
}

@media (max-width: 568px) {
  .router-link {
    font-size: 15px;
    padding: 10px 8px;
    border: none;
  }
}
</style>
