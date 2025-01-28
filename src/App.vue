<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";

const closesidebar = () => {
  const element = document.querySelector(".aside");
  if (element) {
    element.classList.toggle("opened");
  }
};
</script>

<template>
  <div class="container">
    <header class="header">
      <div class="header-control">
        <button class="header-burger">..</button>
        <div class="logo">
          <img src="" alt="Constructor X" />
        </div>
      </div>

      <ul class="header-list">
        <li class="header-item">
          <router-link to="#" class="header-link"> Dashboard </router-link>
        </li>
        <li class="header-item">
          <router-link to="#" class="header-link"> News </router-link>
        </li>
        <li class="header-item">
          <router-link to="#" class="header-link"> Support </router-link>
        </li>
        <li class="header-item">
          <router-link to="#" class="header-link"> More </router-link>
        </li>
      </ul>
      <div class="header-avatar">
        <button class="header-avatar-button">Upgrade</button>
        <img src="https://ui-avatars.com/api/?name=John+Doe" alt="" />
      </div>
    </header>
    <aside class="aside opened">
      <div class="aside-container">
        <img
          src="https://ui-avatars.com/api/?name=John+Doe"
          class="aside-avatar"
          alt=""
        />
        <ul class="aside-list">
          <li class="aside-item">
            <RouterLink to="#dashboard" class="aside-link">
              Dashboard
            </RouterLink>
          </li>
          <li class="aside-item">
            <RouterLink to="#news" class="aside-link"> News </RouterLink>
          </li>
          <li class="aside-item">
            <RouterLink to="#support" class="aside-link"> Support </RouterLink>
          </li>
          <li class="aside-item">
            <RouterLink to="#" class="aside-link"> Logout </RouterLink>
          </li>
        </ul>
        <button class="aside-back"><</button>
      </div>
    </aside>
    <RouterView />
  </div>
</template>

<style scoped>
@import "../src/assets/header/app.css";
@import "../src/assets/sidebar/app.css";
</style>