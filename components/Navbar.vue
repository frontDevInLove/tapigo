<template>
  <div>
    <div class="bg-slate-700 p-4 shadow-md h-16 lg:flex lg:items-center">
      <!-- Кнопка открытия мобильного меню -->
      <div class="lg:hidden focus:outline-none text-right">
        <button @click="toggleMenu">
          <Icon
            name="material-symbols:menu"
            width="32px"
            height="32px"
            color="white"
          />
        </button>
      </div>

      <!-- десктопное меню -->
      <ul class="hidden lg:flex space-x-4 text-slate-50">
        <li>
          <NuxtLink
            to="/"
            exact
            active-class="bg-blue-500 text-white"
            class="p-2 rounded-md hover:bg-blue-600"
            >Главная страница</NuxtLink
          >
        </li>
        <li>
          <NuxtLink
            to="/form"
            active-class="bg-blue-500 text-white"
            class="p-2 rounded-md hover:bg-blue-600"
            >Страница с формой отправки данных</NuxtLink
          >
        </li>
        <li>
          <NuxtLink
            to="/layout"
            active-class="bg-blue-500 text-white"
            class="p-2 rounded-md hover:bg-blue-600"
            >Адаптивный макет</NuxtLink
          >
        </li>
        <li>
          <NuxtLink
            to="/articles"
            active-class="bg-blue-500 text-white"
            :class="{ 'bg-blue-500 text-white': isActive }"
            class="p-2 rounded-md hover:bg-blue-600"
            >Страница-статья</NuxtLink
          >
        </li>
      </ul>
    </div>

    <!-- Фон, закрывающий меню при нажатии -->
    <div
      v-if="isOpen"
      class="fixed inset-0 bg-black bg-opacity-75 z-40"
      @click="toggleMenu"
    ></div>

    <!-- мобильное меню -->
    <div v-if="isOpen" class="fixed top-0 left-0 right-0 bg-white m-3 z-50">
      <ul class="flex flex-col text-center">
        <NuxtLink to="/" @click="toggleMenu" active-class="bg-gray-200" exact>
          <li class="p-4">Главная страница</li>
        </NuxtLink>

        <NuxtLink to="/form" @click="toggleMenu" active-class="bg-gray-200">
          <li class="p-4">Страница с формой отправки данных</li>
        </NuxtLink>

        <NuxtLink to="/layout" @click="toggleMenu" active-class="bg-gray-200">
          <li class="p-4">Адаптивный макет</li>
        </NuxtLink>

        <NuxtLink to="/articles" @click="toggleMenu" active-class="bg-gray-200">
          <li class="p-4">Страница-статья</li>
        </NuxtLink>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;

  if (isOpen.value) {
    document.body.style.overflow = "hidden";
  } else {
    document.body.style.overflow = "";
  }
};

const route = useRoute();
const isActive = computed(() => route.path.startsWith("/articles"));
</script>

<style scoped></style>
