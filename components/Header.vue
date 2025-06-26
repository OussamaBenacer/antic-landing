<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
const navLinks = ["products", "rooms", "services", "inspirations"];
</script>

<template>
  <header class="absolute w-full -translate-x-1/2 top-8 left-1/2">
    <div class="flex items-center gap-6 xl:gap-8 container-auto">
      <h2
        class="text-4xl font-bold text-white lg:text-terracotta font-merriweather"
      >
        antic
      </h2>

      <nav class="max-lg:hidden">
        <ul class="flex items-center gap-4 xl:gap-6 leading-6">
          <li
            v-for="(link, index) in navLinks"
            :key="index"
            class="text-lg capitalize text-brown"
          >
            <a :href="`#${link}`">
              {{ link }}
            </a>
          </li>
        </ul>
      </nav>

      <button class="lg:hidden ms-auto cursor-pointer">
        <IconsMenu />
      </button>

      <button
        class="max-lg:hidden absolute top-1/2 right-10 -translate-y-1/2 cursor-pointer"
      >
        <IconsContact />
      </button>
    </div>
  </header>
</template>
