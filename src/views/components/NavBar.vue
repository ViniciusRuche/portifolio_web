<script setup>
import { ref, computed } from 'vue';
import { useColorMode } from '@vueuse/core'

const isMobileMenuOpen = ref(false);
const mode = useColorMode()
const isDark = computed(() => mode.value === 'dark')

const navLinks = [
  { text: 'SOBRE', url: '#sobre' },
  { text: 'PROJETOS', url: '#projetos' },
  { text: 'HABILIDADES', url: '#habilidades' },
  { text: 'CERTIFICAÇÕES', url: '#certificados' }
];

const toggleMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
const toggleTheme = () => {
  mode.value = isDark.value ? 'light' : 'dark'
}
</script>
<template>
  <nav class="fixed top-0 left-0 w-full flex justify-center p-4 z-[1000]">
    <div class="w-full max-w-[1200px] flex items-center justify-between px-5 py-3 
                bg-black/60 backdrop-blur-xl border border-white/10 rounded-full shadow-2xl transition-all duration-500">
      
      <a href="#" class="flex items-center shrink-0">
        <img src="/images/logo.gif" alt="Logo" class="w-[90px] md:w-[110px] h-10 object-contain rounded-lg" />
      </a>

      <ul :class="[
        'flex gap-8 list-none transition-all duration-300',
        isMobileMenuOpen 
          ? 'absolute top-[4.5rem] left-0 right-0 flex-col bg-black/95 p-8 rounded-[2rem] border border-white/10 flex items-center shadow-2xl mx-4 animate-in fade-in slide-in-from-top-5' 
          : 'hidden md:flex'
      ]">
        <li v-for="link in navLinks" :key="link.text" class="w-full text-center">
          <a :href="link.url" 
             @click="isMobileMenuOpen = false"
             class="text-[0.8rem] tracking-[0.2em] font-bold text-[#c1c1c9] hover:text-white transition-colors duration-200 block py-2">
            {{ link.text }}
          </a>
        </li>
        <li class="md:hidden w-full pt-4">
          <a href="#contato" 
             @click="isMobileMenuOpen = false"
             class="block w-full text-center bg-gradient-to-r from-indigo-600 to-purple-600 text-white py-4 rounded-xl text-[0.8rem] font-bold tracking-widest">
            CONTATO
          </a>
        </li>
      </ul>

      <div class="flex items-center gap-3 md:gap-6">
        <a href="#contato" 
           class="hidden md:flex bg-gradient-to-r from-indigo-600 to-purple-600 text-white hover:scale-105 transition-all px-6 py-2.5 rounded-full text-[0.75rem] font-bold tracking-wider">
          CONTATO
        </a>

        <label class="theme-switch">
          <input type="checkbox"  @change="toggleTheme" :checked="isDark" class="checkbox">
          <div class="container">
            <div class="circle-container">
                <div class="sun-moon-container">
                <div class="moon">
                  <div class="spot"></div>
                  <div class="spot"></div>
                  <div class="spot"></div>
                </div>
              </div>
            </div>
          </div>
        </label>

        <button class="flex md:hidden flex-col gap-[6px] p-2 z-[1001]" @click="toggleMenu" aria-label="Abrir Menu">
          <span :class="['w-6 h-[2px] bg-white transition-all duration-300', isMobileMenuOpen ? 'rotate-45 translate-y-[8px]' : '']"></span>
          <span :class="['w-6 h-[2px] bg-white transition-all duration-300', isMobileMenuOpen ? 'opacity-0' : '']"></span>
          <span :class="['w-6 h-[2px] bg-white transition-all duration-300', isMobileMenuOpen ? '-rotate-45 -translate-y-[8px]' : '']"></span>
        </button>
      </div>
    </div>
  </nav>
</template>
<style scoped>
body {
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.theme-switch {
  --container-width: 5.625em;
  --container-height: 2.5em;
  --container-light-bg: #3D7EAE;
  --circle-container-diameter: 3.375em;
  --sun-moon-diameter: 2.125em;
  --sun-bg: #ECCA2F;
  --moon-bg: #C4C9D1;
  --spot-color: #959DB1;
  --circle-container-offset: calc((var(--circle-container-diameter) - var(--container-height)) / 2 * -1);
}

.theme-switch,
.theme-switch *,
.theme-switch *::before,
.theme-switch *::after {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.container {
  width: 5.625em;
  height: var(--container-height);
  background-color: var(--container-light-bg);
  border-radius: 6.25em;
  overflow: hidden;
  cursor: pointer;
  -webkit-box-shadow: 0em -0.062em 0.062em rgba(0, 0, 0, 0.25), 0em 0.062em 0.125em rgba(255, 255, 255, 0.94);
  box-shadow: 0em -0.062em 0.062em rgba(0, 0, 0, 0.25), 0em 0.062em 0.125em rgba(255, 255, 255, 0.94);
  -webkit-transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  -o-transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  position: relative;
}

.container::before {
  content: "";
  position: absolute;
  z-index: 1;
  inset: 0;
  -webkit-box-shadow: 0em 0.05em 0.187em rgba(0, 0, 0, 0.25) inset, 0em 0.05em 0.187em rgba(0, 0, 0, 0.25) inset;
  box-shadow: 0em 0.05em 0.187em rgba(0, 0, 0, 0.25) inset, 0em 0.05em 0.187em rgba(0, 0, 0, 0.25) inset;
}

.checkbox {
  display: none;
}

.circle-container {
  width: 3.375em;
  height: 3.375em;
  background-color: rgba(255, 255, 255, 0.1);
  position: absolute;
  left: var(--circle-container-offset);
  top: var(--circle-container-offset);
  border-radius: 6.25em;
  -webkit-box-shadow: inset 0 0 0 3.375em rgba(255, 255, 255, 0.1), inset 0 0 0 3.375em rgba(255, 255, 255, 0.1), 0 0 0 0.625em rgba(255, 255, 255, 0.1), 0 0 0 1.25em rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 0 0 3.375em rgba(255, 255, 255, 0.1), inset 0 0 0 3.375em rgba(255, 255, 255, 0.1), 0 0 0 0.625em rgba(255, 255, 255, 0.1), 0 0 0 1.25em rgba(255, 255, 255, 0.1);
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-transition: .3s cubic-bezier(0, -0.02, 0.35, 1.17);
  -o-transition: .3s cubic-bezier(0, -0.02, 0.35, 1.17);
  transition: .3s cubic-bezier(0, -0.02, 0.35, 1.17);
  pointer-events: none;
}

.sun-moon-container {
  pointer-events: auto;
  position: relative;
  z-index: 2;
  width: var(--sun-moon-diameter);
  height: var(--sun-moon-diameter);
  margin: auto;
  border-radius: 6.25em;
  background-color: var(--sun-bg);
  -webkit-box-shadow: 0.062em 0.062em 0.062em 0em rgba(254, 255, 239, 0.61) inset, 0em -0.062em 0.062em 0em #a1872a inset;
  box-shadow: 0.062em 0.062em 0.062em 0em rgba(254, 255, 239, 0.61) inset, 0em -0.062em 0.062em 0em #a1872a inset;
  -webkit-filter: drop-shadow(0.062em 0.125em 0.125em rgba(0, 0, 0, 0.25)) drop-shadow(0em 0.062em 0.125em rgba(0, 0, 0, 0.25));
  filter: drop-shadow(0.062em 0.125em 0.125em rgba(0, 0, 0, 0.25)) drop-shadow(0em 0.062em 0.125em rgba(0, 0, 0, 0.25));
  overflow: hidden;
  -webkit-transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  -o-transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
}

.moon {
  -webkit-transform: translateX(100%);
  -ms-transform: translateX(100%);
  transform: translateX(100%);
  width: 100%;
  height: 100%;
  background-color: var(--moon-bg);
  border-radius: inherit;
  -webkit-box-shadow: 0.062em 0.062em 0.062em 0em rgba(254, 255, 239, 0.61) inset, 0em -0.062em 0.062em 0em #969696 inset;
  box-shadow: 0.062em 0.062em 0.062em 0em rgba(254, 255, 239, 0.61) inset, 0em -0.062em 0.062em 0em #969696 inset;
  -webkit-transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  -o-transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  transition: .5s cubic-bezier(0, -0.02, 0.4, 1.25);
  ;
  position: relative;
}

.spot {
  position: absolute;
  top: 0.75em;
  left: 0.312em;
  width: 0.75em;
  height: 0.75em;
  border-radius: 6.25em;
  background-color: var(--spot-color);
  -webkit-box-shadow: 0em 0.0312em 0.062em rgba(0, 0, 0, 0.25) inset;
  box-shadow: 0em 0.0312em 0.062em rgba(0, 0, 0, 0.25) inset;
}

.spot:nth-of-type(2) {
  width: 0.375em;
  height: 0.375em;
  top: 0.937em;
  left: 1.375em;
}

.spot:nth-last-of-type(3) {
  width: 0.25em;
  height: 0.25em;
  top: 0.312em;
  left: 0.812em;
}


.checkbox:checked+.container {
  background-color: #1D1F2C;
}

.checkbox:checked+.container .circle-container {
  left: calc(100% - var(--circle-container-offset) - var(--circle-container-diameter));
}

.checkbox:checked+.container .circle-container:hover {
  left: calc(100% - var(--circle-container-offset) - var(--circle-container-diameter) - 0.187em)
}

.circle-container:hover {
  left: calc(var(--circle-container-offset) + 0.187em);
}

.checkbox:checked+.container .moon {
  -webkit-transform: translate(0);
  -ms-transform: translate(0);
  transform: translate(0);
}
</style>