<script setup>
import { ChevronRight, Github, Linkedin } from 'lucide-vue-next'

const techIcons = [
  "https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original.svg",
  "https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg",
  "https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg",
  "https://raw.githubusercontent.com/devicons/devicon/master/icons/tailwindcss/tailwindcss-original.svg",
  "https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg"
]
</script>
<template>
  <section class="relative pt-40 pb-20 md:pt-56 md:pb-32 overflow-hidden bg-background transition-colors duration-500">
    
    <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-full -z-10">
      <div class="glow-element absolute top-[-10%] left-1/2 -translate-x-1/2 w-[800px] h-[400px] bg-indigo-600/10 dark:bg-indigo-600/20 blur-[140px] rounded-full"></div>
    </div>

    <div class="container mx-auto px-6">
      <div class="flex flex-col items-center text-center space-y-8">
        
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-muted border border-border text-[10px] uppercase tracking-widest font-bold text-indigo-600 dark:text-indigo-300 backdrop-blur-sm animate-in fade-in slide-in-from-top-4 duration-1000">
          <span class="relative flex h-2 w-2">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-indigo-400 opacity-75"></span>
            <span class="relative inline-flex rounded-full h-2 w-2 bg-indigo-500"></span>
          </span>
          Disponível para novos projetos
        </div>

        <h1 class="text-6xl md:text-8xl lg:text-9xl font-black tracking-tighter text-foreground animate-in fade-in slide-in-from-bottom-8 duration-700 leading-[0.9]">
          Software <br />
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500">
            Engineer
          </span>
        </h1>

        <p class="max-w-[550px] text-base md:text-lg text-muted-foreground font-medium leading-relaxed animate-in fade-in slide-in-from-bottom-10 duration-1000">
          Desenvolvedor Full Stack especializado em 
          <span class="text-foreground font-bold">Vue.js</span> e 
          <span class="text-foreground font-bold">Python</span>. 
          Unindo design moderno e arquitetura sólida.
        </p>

        <div class="flex flex-wrap justify-center gap-4 pt-4 animate-in fade-in slide-in-from-bottom-12 duration-1000">
          <a href="#projetos" class="h-12 px-8 rounded-full bg-indigo-600 text-white font-bold hover:bg-indigo-500 hover:scale-105 transition-all flex items-center gap-2">
            Projetos <ChevronRight class="w-4 h-4" />
          </a>
          
          <div class="flex gap-2">
            <a href="https://github.com/ViniciusRuche" target="_blank" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-border bg-card hover:bg-muted transition-colors group">
              <Github class="w-5 h-5 text-foreground group-hover:text-primary transition-colors" />
            </a>
            <a href="https://www.linkedin.com/in/vinicius-ruche-5ab7a0267/" target="_blank" rel="noopener noreferrer"
              class="w-12 h-12 flex items-center justify-center rounded-full border border-border bg-card hover:bg-muted transition-colors group">
              <Linkedin class="w-5 h-5 text-foreground group-hover:text-primary transition-colors" />
            </a>
          </div>
        </div>

        <div class="pt-16 flex flex-wrap justify-center gap-8 items-center opacity-50 dark:opacity-30 grayscale hover:grayscale-0 transition-all duration-700">
           <img v-for="icon in techIcons" :key="icon" :src="icon" class="h-7 w-auto dark:brightness-110" />
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
@keyframes float {
  0%, 100% { transform: translate(-50%, -15px); }
  50% { transform: translate(-50%, 15px); }
}
.glow-element {
  animation: float 8s ease-in-out infinite;
}
</style>