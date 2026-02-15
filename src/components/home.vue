<template>
  <section id="banner-section" class="relative min-h-screen mt-25 md:mt-0 flex flex-col justify-center items-center">
    <div class="absolute inset-0 z-0">
      <img src="../assets/images/30012_hd.jpg" class="w-full h-full object-cover object-center absolute right-0 transition-opacity duration-1000" alt="Hero Background" id="heroBackground">
    </div>

    <div class="absolute inset-0 bg-[#030A17]/80 z-10 mask-b-to-50%"></div>
    <div class="absolute inset-0 bg-[#030A17] z-10 mask-r-from-5%"></div>
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