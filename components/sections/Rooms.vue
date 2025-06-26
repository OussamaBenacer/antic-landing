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

const nextSlide = () => {
  swiperRef.value?.slideNext();
};
</script>
<template>
  <section id="rooms" class="py-12 sm:pt-16 sm:pb-17 bg-light">
    <div class="container-auto">
      <h2
        class="text-4xl text-brown-dark font-merriweather sm:text-5xl lg:text-[3.5rem] mb-5 sm:mb-12"
      >
        Find your room
      </h2>

      <div class="gap-6 mb-8 sm:mb-12 sm:flex">
        <p class="text-lg text-brown-light sm:w-42 shrink-0 max-sm:mb-8">
          Dining room, bedroom, bathroom or office. Find what you need
        </p>

        <Swiper
          :slides-per-view="1"
          :space-between="32"
          :breakpoints="{
            1024: {
              slidesPerView: 2,
              spaceBetween: 32,
            },
          }"
          :loop="true"
          :grab-cursor="true"
          class="grow h-88"
          @swiper="handleSwiper"
        >
          <SwiperSlide class="relative !flex grow gap-4 sm:gap-6">
            <div class="relative w-1/2 h-full bg-brown/20 sm:w-56/100 shrink-0">
              <NuxtImg
                src="/images/rooms/bedroom.png"
                alt="living room"
                placeholder
                class="absolute bottom-0 object-cover w-22/10 h-25/10"
              />
            </div>
            <p class="text-lg text-black/45">News arrivals</p>

            <p
              class="absolute text-terracotta z-1 top-1/2 text-center left-1/2 -translate-1/2 font-merriweather text-4xl sm:text-[3.5rem]"
            >
              Bedroom
            </p>
          </SwiperSlide>

          <SwiperSlide class="relative !flex grow gap-4 sm:gap-6">
            <div class="relative w-1/2 h-full bg-brown/20 sm:w-56/100 shrink-0">
              <NuxtImg
                src="/images/rooms/living-room.jpg"
                alt="living room"
                placeholder
                class="object-cover object-center size-full"
              />
            </div>
            <p class="text-lg text-black/45">News arrivals</p>

            <p
              class="absolute text-terracotta z-1 top-1/2 text-center left-1/2 -translate-1/2 font-merriweather text-4xl sm:text-[3.5rem]"
            >
              Living Room
            </p>
          </SwiperSlide>

          <SwiperSlide class="relative !flex grow gap-4 sm:gap-6">
            <div class="relative w-1/2 h-full bg-brown/20 sm:w-56/100 shrink-0">
              <NuxtImg
                src="/images/rooms/bedroom.png"
                alt="living room"
                placeholder
                class="absolute bottom-0 object-cover w-22/10 h-25/10"
              />
            </div>
            <p class="text-lg text-black/45">News arrivals</p>

            <p
              class="absolute text-terracotta z-1 top-1/2 text-center left-1/2 -translate-1/2 font-merriweather text-4xl sm:text-[3.5rem]"
            >
              Bedroom
            </p>
          </SwiperSlide>

          <SwiperSlide class="relative !flex grow gap-4 sm:gap-6">
            <div class="relative w-1/2 h-full bg-brown/20 sm:w-56/100 shrink-0">
              <NuxtImg
                src="/images/rooms/living-room.jpg"
                alt="living room"
                placeholder
                class="object-cover object-center size-full"
              />
            </div>
            <p class="text-lg text-black/45">News arrivals</p>

            <p
              class="absolute text-terracotta z-1 top-1/2 text-center left-1/2 -translate-1/2 font-merriweather text-4xl sm:text-[3.5rem]"
            >
              Living Room
            </p>
          </SwiperSlide>
        </Swiper>
      </div>

      <div
        class="flex items-center justify-between gap-6 sm:flex-row-reverse sm:justify-end"
      >
        <button
          class="flex items-center gap-1 font-bold cursor-pointer sm:gap-2 font-karla text-terracotta"
          @click="nextSlide"
        >
          <span class="text-xl">Next</span>
          <IconsChevronDown class-name="-rotate-90 w-3 sm:w-3.5" />
        </button>
        <div class="text-lg text-brown-light sm:w-42">
          {{ currentIndex }} / {{ formatNumber(total) }}
        </div>
      </div>
    </div>
  </section>
</template>
