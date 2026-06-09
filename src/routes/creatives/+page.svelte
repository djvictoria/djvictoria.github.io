<script lang="ts">
  // Creative Works Data
  const creatives = [
    {
      id: 'art-gallery',
      title: 'Digital Art',
      description: 'Character Art, Background Art, and concept sketches.',
      image: '/art.png'
    },
    {
      id: 'music-production',
      title: 'Audio & Music',
      description: 'Original compositions, beat-making, and sound design.',
      image: '/music.png'
    }
  ];
</script>

<main class="min-h-screen bg-zinc-950 text-white font-sans scroll-smooth">
  
  <nav class="sticky top-0 bg-black/80 backdrop-blur-md p-6 border-b border-white/10 z-50">
    <a href="/" class="text-white/60 hover:text-white transition-colors">
      ← Back to Homepage
    </a>
  </nav>

  <div class="max-w-4xl mx-auto px-6 py-24 flex flex-col gap-32">
    
    <h1 class="text-5xl font-bold tracking-tight text-center mb-12">Creative Works</h1>

    {#each creatives as item}
      <section id={item.id} class="min-h-[70vh] flex flex-col justify-center gap-8 pt-24">
        
        <div class="border-b border-white/20 pb-4">
          <h2 class="text-4xl font-bold tracking-tight">{item.title}</h2>
          <p class="text-white/50 text-xl mt-2">{item.description}</p>
        </div>

        <div class="w-full aspect-video border border-white/20 bg-white/5 overflow-hidden">
          <img src={item.image} alt={item.title} class="w-full h-full object-cover opacity-80" />
        </div>

        <p class="text-white/80 text-lg leading-relaxed">
          Detailed gallery or audio tracks {item.title}
        </p>

      </section>
    {/each}

  </div>
</main>