<template>
  <nav>
    <button @click="toggleMenu" class="md:hidden" title="Toggle menu">
      <AppBurger :is-active="isMenuToggled" />
    </button>
    <Transition>
      <div
        v-if="isMenuToggled || isDesktop"
        :class="
          twMerge(
            'container absolute left-0 top-20 z-10 flex h-full w-full flex-col gap-6 bg-zinc-950/60 pb-24 pt-12 backdrop-blur-md md:static md:h-auto md:w-auto md:flex-row md:items-center md:bg-transparent md:py-0 md:backdrop-blur-none'
          )
        "
      >
        <NuxtLink
          @click="toggleMenuIfMobile"
          class="nav-link link-bg-hover"
          to="/"
        >
          Home
        </NuxtLink>
        <NuxtLink
          @click="toggleMenuIfMobile"
          class="nav-link link-bg-hover"
          to="/product"
        >
          Product
        </NuxtLink>
        <NuxtLink
          @click="toggleMenuIfMobile"
          class="nav-link link-bg-hover"
          to="/recruiter"
        >
          About
        </NuxtLink>

        <div class="mt-auto flex gap-4 md:hidden">
          <NuxtLink class="text-white" to="/terms">Terms</NuxtLink>
          <NuxtLink class="text-white" to="/privacy">Privacy</NuxtLink>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script setup lang="ts">
import { twMerge } from "tailwind-merge";

const isMenuToggled = ref(false);
const isDesktop = ref(false);

const toggleMenu = () => {
  isMenuToggled.value = !isMenuToggled.value;
  document.body.classList.toggle("overflow-hidden", isMenuToggled.value);
};

const toggleMenuIfMobile = () => {
  if (!isDesktop.value) {
    toggleMenu();
  }
};

const updateIsDesktop = () => {
  isDesktop.value = window.innerWidth >= 768;
};

onMounted(() => {
  updateIsDesktop();
  window.addEventListener("resize", updateIsDesktop);
});

onUnmounted(() => {
  window.removeEventListener("resize", updateIsDesktop);
});
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
