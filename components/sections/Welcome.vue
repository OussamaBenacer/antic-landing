<script setup>
const scrollDown = () => window.scrollBy(0, window.innerHeight);
</script>
<template>
  <Header />
  <section id="welcome" class="container-auto h-svh">
    <div
      class="absolute top-0 right-0 h-full w-full lg:w-1/2 bg-brown-light bg-[url('/images/welcome-img.jpg')] bg-size-[100%_100%] lg:bg-size-[110%_135%] lg:bg-[0%_40%] bg-no-repeat -z-1"
    />
    <div
      class="absolute top-0 left-0 w-1/2 h-full max-lg:hidden bg-light -z-1"
    />

    <div
      class="flex items-center justify-center h-full text-center lg:justify-start lg:text-start"
    >
      <div class="space-y-6 lg:space-y-10">
        <p class="text-sm font-bold text-white uppercase lg:text-terracotta">
          home design
        </p>

        <div class="space-y-6 lg:space-y-8 lg:w-2/3">
          <h4
            class="max-w-md mx-auto text-4xl font-normal leading-9 text-white lg:text-5xl lg:leading-18 lg:text-terracotta font-merriweather"
          >
            Elegance for Interiors & Exteriors
          </h4>
          <p
            class="max-w-sm mx-auto text-lg text-white lg:text-xl lg:leading-8 max-lg:px-2 lg:text-brown-light"
          >
            We provide everyone with modern, trendy, quality furniture
          </p>
        </div>

        <button
          class="grid text-white border-2 rounded-full max-lg:mx-auto lg:text-terracotta cursor-pointer place-content-center size-13"
          @click="scrollDown"
        >
          <IconsChevronDown />
        </button>
      </div>
    </div>
  </section>
</template>
