<template>
  <section id="banner-section" class="relative min-h-screen mt-25 md:mt-0 flex flex-col justify-center items-center">
    <div class="absolute inset-0 z-0">
      <img src="../assets/images/30012_hd.jpg" class="w-full h-full object-cover object-center absolute right-0 transition-opacity duration-1000" alt="Hero Background" id="heroBackground">
    </div>

    <div class="absolute inset-0 bg-[#0A122A]/20 z-10 mask-b-to-50%"></div>
    <div class="absolute inset-0 bg-[#0A122A] z-10 mask-r-from-5%"></div>
    <div class="absolute inset-0 bg-[#0A122A] z-10 mask-t-to-50%"></div>
    <div class="md:hidden absolute inset-0 bg-[#0A122A] z-10 mask-b-to-25%"></div>

    <div class="relative w-[90%] md:w-3/4 flex flex-col justify-center lg:top-70 z-20">
      <h1 class="w-full md:w-3/4 raleway-light text-white md:left-2 text-xs md:text-xl text-center md:text-left">
        SIMPLY BECAUSE,
      </h1>
      <h2 class="text-3xl md:text-6xl drop-shadow-lg leading-tight w-full montserrat font-bold top-2 text-center md:text-left uppercase text-transparent bg-clip-text bg-linear-to-r from-[#586BA4] via-[#F5DD90] via-30% to-[#F68E5F] to-60%">
        Every Animal Deserves a Voice
      </h2>
      <h3 class="w-[90%] md:w-1/2 text-white/90 text-xs md:text-lg hanken-light text-center md:text-left mx-auto md:mx-0 uppercase">
        Join us in building a kinder world for all creatures.
      </h3>
    </div>
  </section>

  <section class="relative min-h-screen flex flex-col justify-center items-center">
    <div class="w-screen relative min-h-screen flex items-center justify-center mx-auto z-30 text-center">
      <h1 class="select-none text-[150px] lg:text-[600px] montserrat-extrabold uppercase font-bold text-[#070F1F]/60 transition-all duration-1000 text-shadow-white outline">
        CPI
      </h1>
      <div class="w-3/4 flex flex-col items-center absolute top-1/2 right-1/2 translate-x-1/2 -translate-y-1/2">
        <h3 class="text-2xl md:text-4xl lg:text-5xl text-[#f1f1f1]/90 transition-all duration-1000 fadeIntersect z-20 font-extrabold show">
          "The greatness of a nation and its moral progress can be judged by the way its animals are treated." – 
          <span class="text-transparent bg-clip-text bg-linear-to-r from-[#586BA4] via-[#F5DD90] via-30% to-[#F68E5F]">
            Mahatma Gandhi
          </span>
        </h3>
        <a href="#/learn" class="text-sm lg:text-base mt-6 inline-block text-white backdrop-blur-xl w-max px-6 py-3 rounded-full font-[Montserrat] font-medium transition-all duration-300 border border-slate-500/40 hover:border-[#125E85/60]  hover:scale-105 active:scale-95">
          <span class="text-transparent bg-clip-text bg-linear-to-r from-[#586BA4] via-[#F5DD90] via-30% to-[#F68E5F]">
            Learn More
          </span>
        </a>
      </div>
    </div>

    <div class="absolute -bottom-50 -left-50 lg:-top-80 lg:-left-100 w-150 h-150 lg:w-350 lg:h-350 bg-[radial-gradient(circle,#1A0841_0%,transparent_50%)] opacity-20 -z-1 pointer-events-none">
    </div>
    <div class="absolute -bottom-50 -right-75 lg:-top-100 lg:-right-180 w-150 h-150 lg:w-500 lg:h-500 bg-[radial-gradient(circle,#0C2A3C_0%,transparent_50%)] opacity-20 -z-1 pointer-events-none">
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