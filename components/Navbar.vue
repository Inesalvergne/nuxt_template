<template>
  <div>
    <!-- On Desktop -->
    <div class="hidden mx-auto mt-10 border rounded-lg tablet:block border-pink w-fit ">
      <div class="flex items-center gap-16 px-10 py-3 text-brick">
        <NuxtLink to="/">
          <img src="@/assets/images/logo.png" alt="placeholder logo" width="40" height="40">
        </NuxtLink>
        <NuxtLink
          :to="localePath(`${link.to}`)"
          v-for="(link, index) in navLinks"
          :key="index"
          class="text-[20px] uppercase hover:text-gradient">
          {{ $t(link.text) }}
        </NuxtLink>

        <LanguageSwitcher />
      </div>
    </div>

    <!-- on Mobile -->
    <div class="flex items-center justify-between px-6 py-4 bg-white tablet:hidden">
        <NuxtLink to="/">
          <img src="@/assets/images/logo.png" alt="placeholder logo" width="40" height="40">
        </NuxtLink>
        <div class="my-auto">
          <IconsBurger :showMenu="showMenu" @click="toggleMenu"/>
        </div>
    </div>
    <div v-if="showMenu" class="laptop:hidden absolute top-[50px] w-full z-[1] inset-x-0 h-fit py-5 px-7  bg-white shadow-md">
      <div class="flex flex-col items-end gap-6 mt-3 text-brick">
        <NuxtLink
          v-for="(link, index) in navLinks"
          :key="index"
          :to="link.to"
          @click="closeMenu()"
          class="hover:text-gradient">
          {{ $t(link.text) }}
        </NuxtLink>

        <LanguageSwitcher />
      </div>
    </div>
  </div>
</template>

<style>
  /*  Apply style to active links in the navbar */
  /* .router-link-exact-active {
    @apply text-gradient font-semibold;
  } */
</style>

<script setup>
  import { ref } from 'vue'

  const localePath = useLocalePath()

  const navLinks = [
    { text: 'a link', to: '#' },
    { text: 'a link', to: '#' },
    { text: 'a link', to: '#' },
    { text: 'a link', to: '#' },
  ]

  const showMenu = ref(false)
  const toggleMenu = () => { showMenu.value = !showMenu.value }
  const closeMenu = () => { showMenu.value = false }
</script>
