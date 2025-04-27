<template>
  <div>
    <section class="text-center">
      <h1 class="my-5 text-brick text-[32px] font-semibold leading-[50px] laptop:text-[38px] ">
        {{ t('home.header.title') }}
      </h1>
      <p class="text-xl">{{ t('home.header.description') }}</p>

      <NuxtLink to="/services" class="mx-auto mt-5 btn-primary">
        {{ t('home.header.cta') }}
      </NuxtLink>
    </section>
  </div>
</template>

<script setup lang="ts">
  import { useI18n } from 'vue-i18n';
  const { t, tm, rt } = useI18n();

  definePageMeta({
    title: "A title",
    description: "A description"
  })
</script>
