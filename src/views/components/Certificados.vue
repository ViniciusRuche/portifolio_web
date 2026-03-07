<script setup>
import { Dialog, DialogContent, DialogTrigger } from '@/components/ui/dialog'
import { Award, GraduationCap, Eye } from 'lucide-vue-next'

const certificates = [
  {
    title: 'Técnico em Informática',
    issuer: 'QI Faculdade e Escola Técnica',
    date: 'Março 2023',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Educação'
  },
  {
    title: 'A1 Básico de Inglês - 80 Horas',
    issuer: 'Skill Idiomas',
    date: 'Dezembro 2017',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Idioma'
  },
  {
    title: 'Inglês - 195 Horas',
    issuer: 'TopWay',
    date: 'Maio 2020',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Idioma'
  },
  {
    title: 'Formação Front-end - HTML, CSS, JavaScript, React e +',
    issuer: 'Udemy - Matheus Battisi, Hora de Codar',
    date: 'Janeiro 2025',
    image: 'https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=1000',
    category: 'Especialização'
  },
]
</script>
<template>
  <section id="certificados" class="py-24 bg-background transition-colors duration-500">
    <div class="container mx-auto px-6">
      <div class="mb-16">
        <h2 class="text-4xl md:text-5xl font-black tracking-tighter text-foreground italic uppercase">
          Certificações <span class="text-indigo-600 dark:text-indigo-500">&</span> Educação
        </h2>
        <div class="w-20 h-1 bg-indigo-600 dark:bg-indigo-500 mt-4 rounded-full"></div>
      </div>
      <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-2">
        <Dialog v-for="cert in certificates" :key="cert.title">
          <DialogTrigger as-child>
            <div class="group relative flex items-center justify-between p-6 
                        bg-muted/40 dark:bg-white/[0.02] border border-border rounded-2xl 
                        hover:bg-muted/60 dark:hover:bg-white/[0.04] hover:border-indigo-500/30 transition-all duration-300 cursor-pointer">
              <div class="flex items-center gap-5">
                <div class="p-4 bg-indigo-500/10 rounded-xl text-indigo-600 dark:text-indigo-400 
                            group-hover:bg-indigo-600 group-hover:text-white transition-all duration-500">
                  <GraduationCap v-if="cert.category === 'Educação'" :size="24" />
                  <Award v-else :size="24" />
                </div>
                <div>
                  <h3 class="text-foreground font-bold text-base md:text-lg leading-tight group-hover:text-indigo-600 dark:group-hover:text-indigo-400 transition-colors">
                    {{ cert.title }}
                  </h3>
                  <div class="flex items-center gap-3 mt-1 text-muted-foreground uppercase tracking-widest text-[10px] font-bold">
                    <p>{{ cert.issuer }}</p>
                    <span class="w-1 h-1 bg-border rounded-full"></span>
                    <p class="italic">{{ cert.date }}</p>
                  </div>
                </div>
              </div>
              <div class="flex items-center gap-2 opacity-0 group-hover:opacity-100 transition-all transform translate-x-2 group-hover:translate-x-0 hidden sm:flex">
                <span class="text-[10px] font-black text-indigo-600 dark:text-indigo-400 uppercase tracking-tighter">Detalhes</span>
                <Eye :size="16" class="text-indigo-600 dark:text-indigo-400" />
              </div>
            </div>
          </DialogTrigger>
          <DialogContent class="sm:max-w-[700px] bg-background border-border rounded-[2rem] overflow-hidden p-0 shadow-2xl transition-colors duration-500">
            <div class="p-8 bg-gradient-to-br from-indigo-600/10 dark:from-indigo-600/20 to-transparent border-b border-border">
              <div class="px-3 py-1 bg-indigo-500/10 border border-indigo-500/20 rounded-full w-fit mb-4 text-indigo-600 dark:text-indigo-400 text-[10px] font-bold uppercase tracking-widest">
                {{ cert.category }}
              </div>
              <h2 class="text-2xl font-black text-foreground italic uppercase tracking-tight leading-none">
                {{ cert.title }}
              </h2>
              <p class="text-muted-foreground text-xs mt-2 uppercase tracking-widest">
                {{ cert.issuer }} — {{ cert.date }}
              </p>
            </div>
            <div class="p-4 bg-muted/30 dark:bg-black/40 flex justify-center group/img relative">
              <img 
                :src="cert.image" 
                :alt="cert.title" 
                class="max-w-full h-auto rounded-xl shadow-2xl border border-border grayscale-[0.3] hover:grayscale-0 transition-all duration-700" 
              />
            </div>
            <div class="p-6 text-center bg-background">
              <p class="text-[10px] text-muted-foreground uppercase tracking-[0.3em] font-medium italic">Documento Digital Autenticado</p>
            </div>
          </DialogContent>
        </Dialog>
      </div>
    </div>
  </section>
</template>
<style scoped>
:deep(.fixed) {
  backdrop-filter: blur(8px);
}
</style>