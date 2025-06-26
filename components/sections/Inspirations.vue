<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";
const formatNumber = (number = 0) =>
  number < 9 ? "0" + number : number?.toString();

const swiperRef = ref(null);
const currentIndex = computed(() => {
  const index = swiperRef.value?.realIndex + 1;
  return formatNumber(index);
});
const total = 4;

const handleSwiper = (swiper) => {
  swiperRef.value = swiper;
};

const nextSlide = () => swiperRef.value?.slideNext();
const prevSlide = () => swiperRef.value?.slidePrev();
</script>
<template>
  <section id="inspirations" class="py-12 bg-white sm:pt-16 sm:pb-17">
    <div>
      <div
        class="mb-16 container-auto lg:flex lg:items-center lg:justify-between lg:gap-10"
      >
        <div class="max-lg:mb-8">
          <h3 class="text-[#121212] text-4xl font-merriweather mb-4">
            Be aware of the latest trends
          </h3>
          <p class="text-lg text-brown-light mb-4 lg:mb-2.5">
            Stay informed of new trends, but also of our various offers.
          </p>

          <SpecialLink>Learn more</SpecialLink>
        </div>

        <form class="gap-4 sm:flex" @submit.prevent>
          <input
            required
            type="text"
            class="block w-full max-sm:mb-4 h-12.5 p-4 lg:w-75 rounded-xs text-lg placeholder:text-brown-light"
            placeholder="email@address.com"
          >

          <button
            class="max-w-full py-3 text-center text-white cursor-pointer bg-brown-dark max-sm:w-95/100 sm:w-60 lg:w-36 font-karla"
          >
            Subscribe
          </button>
        </form>
      </div>

      <!-- swiper slides in tablet and desktop  -->
      <div class="mb-10 max-sm:hidden sm:container-start">
        <Swiper
          :space-between="30"
          slides-per-view="auto"
          grab-cursor
          class="!pe-8"
          loop
          @swiper="handleSwiper"
        >
          <SwiperSlide class="!w-fit">
            <div class="bg-brown-light aspect-145/175 w-114">
              <NuxtImg />
            </div>
          </SwiperSlide>

          <SwiperSlide class="!w-fit">
            <div class="bg-brown-light aspect-145/175 w-114">
              <NuxtImg />
            </div>
          </SwiperSlide>

          <SwiperSlide class="!w-fit">
            <div class="bg-brown-light aspect-145/175 w-114">
              <NuxtImg />
            </div>
          </SwiperSlide>

          <SwiperSlide class="!w-fit">
            <div class="bg-brown-light aspect-145/175 w-114">
              <NuxtImg />
            </div>
          </SwiperSlide>
        </Swiper>
      </div>

      <!-- inspiration + swiper navigation and pagination -->
      <div
        class="justify-between container-auto max-sm:mb-10 sm:gap-16 sm:flex sm:items-start"
      >
        <div class="max-w-3xl lg:flex lg:gap-10 xl:gap-36">
          <h2
            class="text-4xl max-lg:mb-5 sm:text-5xl font-merriweather text-brown-dark"
          >
            Inspirations
          </h2>
          <p class="text-lg text-brown">
            Our experts are keen to stay on top of trends in order to offer you
            new inspirations for your interior and exterior every day. Remember
            that to inspire you we have to inspire ourselves and we want to
            share that with you.
          </p>
        </div>

        <div class="max-sm:hidden xl:min-w-70">
          <div class="flex items-center gap-2.5 mb-5">
            <button
              class="grid border-2 rounded-full cursor-pointer text-terracotta place-content-center size-10"
              @click="prevSlide"
            >
              <IconsChevronDown class-name="rotate-90 size-4" />
            </button>

            <button
              class="grid border-2 rounded-full cursor-pointer text-terracotta place-content-center size-10"
              @click="nextSlide"
            >
              <IconsChevronDown class-name="-rotate-90 size-4" />
            </button>
          </div>
          <div class="text-lg text-brown-light">
            {{ currentIndex }} / {{ formatNumber(total) }}
          </div>
        </div>
      </div>
    </div>

    <!-- mobile slides   -->
    <div class="grid grid-cols-2 gap-5 container-auto sm:hidden">
      <div>
        <div class="max-sm:mb-4 bg-brown aspect-145/175">
          <NuxtImg />
        </div>
        <p class="text-[#121212] sm:hidden">Chair</p>
      </div>

      <div>
        <div class="max-sm:mb-4 bg-brown aspect-145/175">
          <NuxtImg />
        </div>
        <p class="text-[#121212] sm:hidden">Chair</p>
      </div>

      <div>
        <div class="max-sm:mb-4 bg-brown aspect-145/175">
          <NuxtImg />
        </div>
        <p class="text-[#121212] sm:hidden">Chair</p>
      </div>

      <div>
        <div class="max-sm:mb-4 bg-brown aspect-145/175">
          <NuxtImg />
        </div>
        <p class="text-[#121212] sm:hidden">Chair</p>
      </div>
    </div>
  </section>
</template>
