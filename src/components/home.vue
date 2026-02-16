<template>
  <section id="banner-section" class="relative min-h-screen mt-25 md:mt-0 flex flex-col justify-center items-center">
    <div class="absolute inset-0 z-0">
      <img src="../assets/images/30012_hd.jpg" class="w-full h-full object-cover object-center absolute right-0 transition-opacity duration-1000" alt="Hero Background" id="heroBackground">
    </div>

    <div class="absolute inset-0 bg-[#FF9F1C]/80 z-10 mask-b-to-50%"></div>
    <div class="absolute inset-0 bg-[#110b02] z-10 mask-r-from-5%"></div>
    <div class="absolute inset-0 bg-[#030A17] z-10 mask-t-to-50%"></div>

    <div class="relative w-[90%] md:w-3/4 flex flex-col justify-center lg:top-70 z-20">
      <h1 class="w-full md:w-3/4 raleway-light text-white md:left-2 text-xs md:text-xl text-center md:text-left">
        SIMPLY BECAUSE,
      </h1>
      <h2 class="text-3xl md:text-6xl drop-shadow-lg leading-tight w-full montserrat font-bold top-2 text-center md:text-left uppercase text-transparent bg-clip-text bg-linear-to-r from-[#F7CE68] via-[#57BAA6] via-30% to-[#125E85] to-60%">
        Every Animal Deserves a Voice
      </h2>
      <h3 class="w-[90%] md:w-1/2 text-white/90 text-xs md:text-lg hanken-light text-center md:text-left mx-auto md:mx-0 uppercase">
        Join us in building a kinder world for all creatures.
      </h3>
    </div>
  </section>

  <section class="relative min-h-screen w-full flex flex-col items-center justify-center text-white ">
    <div class="mx-auto w-3/4">
      <div class="fadeIntersect relative lg:row-span-1">
        <div class="absolute inset-px rounded-lg bg-[#080b1d]/20 rounded-tl-4xl backdrop-blur-xl shadow-lg border border-[#1a1f29] transition-all duration-300 group-hover:border-[#252d3a] z-0">
        </div>
        <div class="relative flex h-full flex-col overflow-hidden px-8 pt-8 pb-6 sm:px-10  sm:py-10">
          <p class="mt-2 text-3xl text-gray-400">
            Welcome to the Compassionate Paws Initiative. We are a community of animal lovers, advocates, and changemakers dedicated to improving the lives of animals everywhere. Whether it’s a stray cat in need of shelter, a farm animal seeking humane treatment, or wildlife threatened by habitat loss, we believe every being deserves compassion.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      bg: null
    }
  },
  mounted() {
    this.bg = document.getElementById("heroBackground");

    this.fadeTogle(this.bg);
    setTimeout(() => {
      this.fadeTogle(this.bg)
    }, 400);
  },
  methods: {
    fadeTogle(img) {
      img.classList.toggle("opacity-0");
      img.classList.toggle("pointer-events-none");
    }
  }
}
</script>