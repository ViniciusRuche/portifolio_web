<script setup>
import { GraduationCap, MapPin, Code2, Rocket } from 'lucide-vue-next'
</script>
<template>
  <section id="sobre" class="py-24 bg-background text-foreground transition-colors duration-500">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
        
        <div class="lg:col-span-5 relative group">
          <div class="absolute -inset-1 bg-gradient-to-r from-indigo-500 to-purple-600 rounded-2xl blur opacity-20 group-hover:opacity-40 transition duration-1000"></div>
          
          <div class="relative bg-card rounded-2xl overflow-hidden border border-border shadow-2xl">
            <img 
              src="/images/perfil.jpeg" 
              alt="Vinícius Ruche" 
              class="w-full aspect-square object-cover grayscale hover:grayscale-0 transition-all duration-700"
            />
          </div>
          
          <div class="absolute -bottom-6 -right-6 p-4 bg-background/80 backdrop-blur-xl border border-border rounded-xl shadow-2xl hidden md:block transition-all">
            <div class="flex items-center gap-3">
              <div class="p-2 bg-indigo-500/10 rounded-lg text-indigo-500">
                <GraduationCap size="20" />
              </div>
              <div>
                <p class="text-[10px] uppercase tracking-widest font-bold text-muted-foreground">Graduação</p>
                <p class="text-xs font-semibold text-foreground">Eng. de Software @ UCS</p>
              </div>
            </div>
          </div>
        </div>

        <div class="lg:col-span-7 space-y-8">
          <div class="space-y-4">
            <h2 class="text-3xl md:text-4xl font-black tracking-tighter italic text-foreground">
              "A tecnologia é o meio, <br/>
              <span class="text-indigo-600 dark:text-indigo-400 text-4xl md:text-5xl">a solução é o fim.</span>"
            </h2>
            <div class="w-20 h-1 bg-indigo-600 dark:bg-indigo-500 rounded-full"></div>
          </div>

          <div class="space-y-6 text-muted-foreground text-lg leading-relaxed">
            <p>
              Sou acadêmico na <span class="text-foreground font-semibold">Universidade de Caxias do Sul</span>, 
              atualmente no 5º semestre, onde mergulho na arquitetura de sistemas e inteligência artificial.
            </p>
            
            <p>
              Meu foco é transformar problemas complexos em interfaces intuitivas e backends robustos. 
              Gosto de trabalhar na intersecção entre o <span class="text-foreground font-semibold">design moderno</span> e a <span class="text-foreground font-semibold">engenharia precisa</span>.
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 pt-4">
            <div class="p-4 rounded-xl border border-border bg-muted/30 flex gap-4 items-start transition-all hover:bg-muted/50">
              <Code2 class="text-indigo-600 dark:text-indigo-400 shrink-0" size="24" />
              <div>
                <h4 class="text-sm font-bold text-foreground uppercase tracking-wider">Atuação Atual</h4>
                <p class="text-sm text-muted-foreground mt-1">Sistemas para o Aeroclube de Caxias do Sul.</p>
              </div>
            </div>

            <div class="p-4 rounded-xl border border-border bg-muted/30 flex gap-4 items-start transition-all hover:bg-muted/50">
              <Rocket class="text-purple-600 dark:text-purple-400 shrink-0" size="24" />
              <div>
                <h4 class="text-sm font-bold text-foreground uppercase tracking-wider">Interesses</h4>
                <p class="text-sm text-muted-foreground mt-1">E2E Testing, IA Generativa e Performance Web.</p>
              </div>
            </div>
          </div>

          <div class="flex items-center gap-4 text-sm text-muted-foreground pt-4">
            <MapPin size="16" class="text-indigo-500" />
            <span>Caxias do Sul, RS - Brasil</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>