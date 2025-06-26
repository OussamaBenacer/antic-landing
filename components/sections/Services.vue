<script setup>
const services = [
  {
    id: 1,
    title: "Our Advices",
    description:
      "What if you took advantage of this rather special period to rethink your interior? You spend more time at home so you might as well feel good there.",
  },
  {
    id: 2,
    title: "Click and Collect",
    description:
      "Adapted and contactless. Free from €200 of purchases in stores offering the service.",
  },
  {
    id: 3,
    title: "Conception Service",
    description:
      "Personalized service with an expert advisor for your interior and exterior decoration or layout projects.",
  },
  {
    id: 4,
    title: "Installation Service",
    description:
      "Our furniture packaged in flat packs are designed for easy assembly. But you can call on our partner.",
  },
];
</script>

<template>
  <section id="services" class="py-12 sm:pt-16 sm:pb-17 bg-light">
    <div class="container-auto lg:grid lg:grid-cols-2 lg:gap-12">
      <div class="space-y-8 max-lg:mb-10">
        <h2
          class="text-4xl text-brown-dark font-merriweather max-w-2xs sm:text-5xl sm:max-w-md lg:text-[3.5rem]"
        >
          We stay by your side to design your projects
        </h2>

        <SpecialLink>Find out more</SpecialLink>
      </div>
      <div class="gap-8 max-sm:space-y-10 sm:grid sm:grid-cols-2">
        <article
          v-for="service in services"
          :key="service.id"
          class="sm:space-y-3"
        >
          <h3 class="text-2xl font-semibold text-terracotta">
            {{ service.title }}
          </h3>
          <p class="text-lg text-brown-light">{{ service.description }}</p>
        </article>
      </div>
    </div>
  </section>
</template>
