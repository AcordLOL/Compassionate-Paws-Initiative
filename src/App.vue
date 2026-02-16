<script setup>
import { ref, computed } from 'vue';
import About from "./components/about.vue";
import Home from "./components/home.vue";
import Learn from "./components/learn.vue";
import TakeAction from "./components/takeAction.vue";

const routes = {
  '/': Home,
  '/about': About,
  '/learn': Learn,
  '/takeaction': TakeAction
};

const currPath = ref(window.location.hash);

window.addEventListener('hashchange', () => {
  currPath.value = window.location.hash;
});

const currView = computed(() => {
  return routes[currPath.value.slice(1) || '/' || NotFound]
})
</script>

<template>
  <div class="transition-opacity duration-700 ease-in-out">

  </div>
  <header>
    <nav id="navbar" class="w-full gap-4 fixed z-50 pointer-events-auto backdrop-blur-lg bg-[#030A17]/30 rounded-b-lg transition-all duration-200 ease-in-out text-white">
      <div class="w-5/6 md:w-3/4 mx-auto">

        <!-- big -->
        <div class="hidden lg:flex flex-row items-center justify-center lg:justify-between border-b border-[#f1f1f1]/50 py-5">
          <div class="h-full flex flex-row items-center gap-8 w-full">
            <h1 class="flex flex-row gap-3 shrink-0 items-center text-base xl:text-xl">CPI</h1>
            <a href="#/" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] relative transition-all duration-300 h-full flex items-center montserrat-light">Home</a>
            <a href="#/learn" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] transition-all duration-300 h-full items-center montserrat-light montserrat-light cursor-pointer">Learn</a>
            <a href="#/takeaction" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] transition-all duration-300 h-full items-center montserrat-light montserrat-light cursor-pointer">Take Action</a>
            <a href="#/about" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] transition-all duration-300 h-full items-center montserrat-light montserrat-light cursor-pointer">About Us</a>
          </div>
        </div>
        
        <!-- small -->
        <div class="lg:hidden flex flex-col items-center justify-between border-b border-[#f1f1f1]/50 py-3"">
          <div class="h-full w-full flex flex-row items-center justify-between gap-6">
            <h1 class="flex flex-row gap-3 shrink-0 items-center text-base xl:text-xl">Compassionate Paws Initiative</h1>
            
            <div class="flex items-center justify-between gap-6">
              <button id="navbarToggle" v-on:click="expandNav" class="text-white focus:outline-none hover:text-[#FF9F1C] transition-colors duration-300 cursor-pointer focus:text-[#FF9F1C]">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-auto" viewBox="0 0 21 21">
                  <path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" d="M4.5 6.5h12m-12.002 4h11.997M4.5 14.5h11.995"></path>
                </svg>
              </button>
            </div>
          </div>
          
          <div class="overflow-hidden flex flex-col w-full items-left justify-between gap-6 transition-all duration-300 max-h-0" id="mobileNavbar">
            <a href="#/" class="nav-link text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] relative transition-all duration-300 h-full flex items-center montserrat-light">Home</a>
            <a href="#/learn" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] transition-all duration-300 h-full items-center montserrat-light montserrat-light cursor-pointer">Learn</a>
            <a href="#/takeaction" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] transition-all duration-300 h-full items-center montserrat-light montserrat-light cursor-pointer">Take Action</a>
            <a href="#/about" class="text-xs xl:text-sm text-white/80 hover:text-[#FF9F1C] transition-all duration-300 h-full items-center montserrat-light montserrat-light cursor-pointer">About Us</a>
          </div>
        </div>
      </div>
    </nav>
  </header>
  <main class="relative w-full min-h-screen overflow-hidden">
    <component :is="currView" />
  </main>
</template>

<script>
export default {
  created() {
    let lstScrlTop = 0;
    window.addEventListener("scroll", function() {
      const scrlTop = this.pageYOffset || this.document.documentElement.scrollTop;
      const navbar = document.getElementById("navbar");
      
      if (scrlTop > lstScrlTop) {
        navbar.classList.add("-translate-y-full");
      } else {
        navbar.classList.remove("-translate-y-full");
      }

      lstScrlTop = scrlTop;
    })
  },
  methods: {
    expandNav() {
      const mobileNavbar = document.getElementById("mobileNavbar");
      mobileNavbar.classList.toggle("max-h-0");
      mobileNavbar.classList.toggle("max-h-120");
      mobileNavbar.classList.toggle("mt-4");
    }
  }
}
</script>