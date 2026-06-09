<script lang="ts">
  // Import Svelte navigation function
  import { afterNavigate } from '$app/navigation';

  // Autoscroll logic
  afterNavigate(() => {
    // Check if there's a hash in the URL
    const hash = window.location.hash;
    if (hash) {
      // Locate the element with the corresponding ID
      const element = document.querySelector(hash);
      if (element) {
        // Scroll the element into view smoothly
        element.scrollIntoView({ behavior: 'smooth' });
      }
    }
  });

  // All Projects Data
  const works = [
    { 
      id: 'roman-empire', 
      title: 'Roman Empire', 
      description: 'Visual novel with interactive puzzle and memory fixing game.',
      details: 'This game focuses on deep narrative choices and memory reconstruction mechanics...',
      image: '/romanempire.png'
    },
    { 
      id: 'foryourpeace', 
      title: 'FYP', 
      description: 'Interactive puzzle horror game set in a Windows XP interface.', 
      details: 'A unique atmospheric horror experience that uses a retro OS interface to build tension...',
      image: '/fyp.png'
    },
    { 
      id: 'battle-city', 
      title: 'Battle City: War of Steel', 
      description: 'Top-down tank shooter game with 12 distinct levels.',
      details: 'An action-packed arcade shooter featuring custom level design and intense boss battles...',
      image: '/battlecity.png'
    },
    {
      id: 'ronsho', 
      title: 'RONIN SHOWDOWN', 
      description: 'Competitive 2D fighting game focused on core combat fundamentals.',
      details: 'Built to test player reflexes with a focus on spacing, timing, and punishing mistakes...',
      image: '/ronsho.png'
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
    
    <h1 class="text-5xl font-bold tracking-tight text-center mb-12">All Projects</h1>

    {#each works as work}
      <section id={work.id} class="min-h-[70vh] flex flex-col justify-center gap-8 pt-24">
        
        <div class="border-b border-white/20 pb-4">
          <h2 class="text-4xl font-bold tracking-tight">{work.title}</h2>
          <p class="text-white/50 text-xl mt-2">{work.description}</p>
        </div>

        <div class="w-full aspect-video border border-white/20 bg-white/5 overflow-hidden">
          <img src={work.image} alt={work.title} class="w-full h-full object-cover opacity-80" />
        </div>

        <p class="text-white/80 text-lg leading-relaxed max-w-2xl">
          {work.details}
        </p>

      </section>
    {/each}

  </div>
</main>