<script lang="ts">
  import { fade, fly } from 'svelte/transition';

  // Listing Projects
  const works = [
    { 
      id: 'roman-empire', 
      title: 'Roman Empire', 
      description: 'Visual novel with interactive puzzle and memory fixing game.',
      image: '/romanempire.png'
    },
    { 
      id: 'foryourpeace', 
      title: 'FYP', 
      description: 'Interactive puzzle horror game set in a Windows XP interface.', 
      image: '/fyp.png'
    },
    { 
      id: 'battle-city', 
      title: 'Battle City: War of Steel', 
      description: 'Top-down tank shooter game with 12 distinct levels.',
      image: '/battlecity.png'
    },
    {
      id: 'ronsho', 
      title: 'RONIN SHOWDOWN', 
      description: 'Competitive 2D fighting game focused on core combat fundamentals.',
      image: '/ronsho.png'
    }
  ];
</script>

<!-- Main Container -->
<main class="min-h-screen bg-gradient-to-b from-zinc-900 to-black text-white font-sans selection:bg-white selection:text-black">
  <div class="max-w-2xl mx-auto px-6 py-24 flex flex-col gap-24">
    
    <!-- Profile Section -->
    <section 
      in:fly={{ y: 30, duration: 800, delay: 200 }} 
      class="flex flex-col sm:flex-row items-center sm:items-start gap-8"
    >
      <!-- Profile Picture -->
      <div class="w-32 h-32 rounded-full bg-white/10 border border-white/20 flex-shrink-0 flex items-center justify-center overflow-hidden">
        <span class="text-white/40 text-sm tracking-widest uppercase">Photo</span>
      </div>

      <!-- Name & Contacts -->
      <div class="flex flex-col items-center sm:items-start text-center sm:text-left pt-2">
        <h1 class="text-4xl font-bold tracking-tight mb-2">Drew Jason T. Victoria</h1>
        <p class="text-white/60 text-lg mb-6">3rd Year Computer Science Student</p>
        
        <div class="flex gap-6 text-sm font-medium tracking-wide">
        
        <!-- Email box -->
        <a href="mailto:victoria.drewjason@gmail.com" class="flex items-center gap-2 hover:text-white/70 transition-colors border-b border-white/30 hover:border-white/70 pb-1">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect width="20" height="16" x="2" y="4" rx="2"></rect>
            <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path>
            </svg>
            Email
        </a>

        <!-- GitHub box -->
        <a href="https://github.com/djvictoria" target="_blank" class="flex items-center gap-2 hover:text-white/70 transition-colors border-b border-white/30 hover:border-white/70 pb-1">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
            <path d="M9 18c-4.51 2-5-2-7-2"></path>
            </svg>
            GitHub
        </a>

        <!-- LinkedIn box -->
        <a href="https://www.linkedin.com/in/drew-jason-victoria-106429381" target="_blank" class="flex items-center gap-2 hover:text-white/70 transition-colors border-b border-white/30 hover:border-white/70 pb-1">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
            <rect width="4" height="12" x="2" y="9"></rect>
            <circle cx="4" cy="4" r="2"></circle>
            </svg>
            LinkedIn
        </a>

        </div>
      </div>
    </section>

    <!-- Works Section -->
    <section 
      in:fly={{ y: 30, duration: 800, delay: 400 }} 
      class="flex flex-col gap-8"
    >
      <h2 class="text-xl font-medium border-b border-white/20 pb-4 uppercase tracking-widest text-white/80">
        Project Experience
      </h2>
      
      <div class="flex flex-col gap-4">
        {#each works as work, i (work.id)}
          <a 
            href="/works/{work.id}"
            class="group flex flex-col sm:flex-row justify-between sm:items-center gap-6 p-6 border border-white/20 hover:bg-white hover:text-black transition-all duration-500 ease-out"
            in:fade={{ duration: 600, delay: 600 + (i * 150) }}
          >
            <div class="w-full sm:w-40 h-32 flex-shrink-0 overflow-hidden border border-white/10 group-hover:border-black/20 transition-colors">
              <img 
                src={work.image} 
                alt="{work.title} thumbnail" 
                class="w-full h-full object-cover grayscale opacity-60 group-hover:grayscale-0 group-hover:opacity-100 transition-all duration-500"
              />
            </div>

            <div class="flex-1">
              <div class="flex items-center gap-4">
                <h3 class="text-2xl font-semibold tracking-tight">{work.title}</h3>
                <span class="opacity-0 group-hover:opacity-100 transition-all duration-300 transform -translate-x-4 group-hover:translate-x-0">
                  →
                </span>
              </div>
              <p class="mt-3 text-sm text-white/50 group-hover:text-black/70 transition-colors duration-500">
                {work.description}
              </p>
            </div>
          </a>
        {/each}
      </div>
    </section>

  </div>
</main>
<style>

/* Background */
  main {
    position: relative;
  }
  
  main::before {
    content: "";
    position: absolute;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    
    background-image: 
      linear-gradient(to right, rgba(255, 255, 255, 0.05) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
    background-size: 40px 40px;
    /* Add this line below to turn the boxes into plus signs: */
    mask-image: radial-gradient(circle, black 2px, transparent 2.5px);
  }

  main > div {
    position: relative;
    z-index: 10;
  }
</style>