<script setup>
const footerLinks = [
  {
    category: "About",
    links: ["Our story", "Our stores", "Our partners"],
  },
  {
    category: "Services",
    links: [
      "Click and collect",
      "Conception",
      "Installation",
      "Advices",
      "Gift card",
    ],
  },
  {
    category: "Rooms",
    links: [
      "Living room",
      "Dining room",
      "Cooked",
      "Bedroom",
      "Bathroom",
      "Office",
      "Laundry",
      "Garage",
    ],
  },
  {
    category: "Products",
    links: [
      "Furniture",
      "Decoration",
      "Storage",
      "Baby and child",
      "Connected home",
    ],
  },
];
</script>
<template>
  <footer id="footer" class="py-12 bg-light lg:pt-18 lg:pb-16">
    <div class="container-custom">
      <div
        class="mb-10 space-y-10 lg:items-start lg:justify-between lg:flex lg:mb-12"
      >
        <!-- logo -->
        <h2
          class="relative text-4xl font-bold text-center text-brown-dark font-merriweather lg:-translate-y-2"
        >
          antic
        </h2>

        <!-- links -->
        <div
          class="gap-8 xl:gap-12 sm:justify-between max-sm:space-y-10 sm:flex sm:flex-row-reverse lg:w-fit"
        >
          <div v-for="item in footerLinks" :key="item.category">
            <h4
              class="mb-2.5 sm:mb-5 text-[#121212] sm:text-brown-dark text-2xl font-semibold"
            >
              {{ item.category }}
            </h4>
            <ul class="space-y-3 text-lg text-brown">
              <li v-for="link in item.links" :key="link">
                <a href="#">{{ link }}</a>
              </li>
            </ul>
          </div>
        </div>

        <!-- respect -->
        <article>
          <h3 class="mb-5 text-2xl font-semibold text-brown-dark">
            We respect our planet
          </h3>

          <div class="gap-4 sm:max-lg:flex">
            <div
              class="relative h-40 mb-4 overflow-hidden w-75 max-w-full lg:w-59 shrink-0 bg-white/50"
            >
              <NuxtImg
                src="/images/footer-img.jpg"
                class="absolute right-0 -translate-y-1/2 h-50 min-w-77 lg:min-w-69 lg:h-46 top-1/2 lg:right-1/2 lg:translate-x-1/2"
                alt="footer image"
              />
            </div>

            <div>
              <p class="mb-4 text-lg text-black/45 lg:max-w-59">
                We’re taking positive steps to reduce our impact on the planet.
                For us, that means retailing responsibly. We’ve set a number of
                goals to get us there.
              </p>

              <SpecialLink>Learn more</SpecialLink>
            </div>
          </div>
        </article>
      </div>

      <!-- social media -->
      <div
        class="flex items-center justify-center gap-5 text-brown-light lg:gap-6 mb-10 lg:mb-5"
      >
        <a href="#"><IconsFacebook /></a>
        <a href="#"><IconsTwitter /></a>
        <a href="#"><IconsLinkedin /></a>
        <a href="#"><IconsInstagram /></a>
      </div>

      <!-- copyright  -->

      <div
        class="max-sm:space-y-8 sm:flex sm:flex-row-reverse sm:items-center sm:justify-between"
      >
        <div
          class="text-lg text-black/45 flex items-center flex-wrap gap-x-6 gap-y-2"
        >
          <p>Privacy policy</p>
          <p>Term of service</p>
          <p>Language</p>
        </div>
        <p class="text-lg text-brown-light">© 2021 Agence Dnd</p>
      </div>
    </div>
  </footer>
</template>
