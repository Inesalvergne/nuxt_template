<template>
  <main role="main" class="flex flex-col min-h-screen">
    <div class="flex-grow">
      <Navbar />
      <div class="w-11/12 mx-auto laptop:w-9/12 desktop:w-7/12">
        <slot />
      </div>
    </div>
    <Footer />
  </main>
</template>

<script setup lang="ts">
  const route = useRoute()

  useSeoMeta({
    title: `${route.meta.title} | Nuxt Template`,
    description: `${route.meta.description}`,
    ogTitle: 'Nuxt Template',
    ogType: 'website',
    // ogImage: 'https://inesalvergne.com/og_image.png',
  })
</script>
