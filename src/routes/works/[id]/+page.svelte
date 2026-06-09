<script lang="ts">
  // All Projects Data
  const works = [
    { 
      id: 'roman-empire', 
      title: 'Roman Empire (Grand Champion)', 
      contribution: 'SFX & Music',
      description: 'Visual novel with interactive puzzle and memory fixing game.',
      details: 'A visual novel puzzle game that was developed as an entry for the SIKAPTala 2026 Game Jam with the theme "We Don\'t See Things as They Are", earning the title of Grand Champion along with 6 group members.',
      image: '/romanempire.png'
    },
    { 
      id: 'foryourpeace', 
      title: 'FYP (Champion)', 
      contribution: 'Game Programmer & Game Artist',
      description: 'Interactive puzzle horror game set in a Windows XP interface.', 
      details: 'A narrative puzzle game developed in partial fulfillment of requirements for four academic subjects and as a winning entry in the Game On! Game Jam Manila 2025 ("Break the Loop; Rewrite the Pattern") alongside 4 group members.',
      image: '/fyp.png'
    },
    { 
      id: 'battle-city', 
      title: 'Battle City: War of Steel', 
      contribution: 'UI/UX Developer',
      description: 'Top-down tank shooter game with 12 distinct levels.',
      details: 'A top-down shooter game inspired by Battle City that was developed in partial fulfillment of requirements for the Introduction to Game Programming course in collaboration with two other developers.',
      image: '/battlecity.png'
    },
    {
      id: 'ronsho', 
      title: 'RONIN SHOWDOWN', 
      contribution: 'Lead Artist & Animator',
      description: 'Competitive 2D fighting game focused on core combat fundamentals.',
      details: 'A competitive 2D fighting game focused on core combat fundamentals that was developed in partial fulfillment of requirements for the Application Development course in collaboration with the lead developer.',
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
          
          <p class="mt-3 text-sm font-semibold tracking-widest uppercase text-white/70">
            Role: {work.contribution}
          </p>

          <p class="text-white/50 text-xl mt-3">{work.description}</p>
        </div>

        <div class="w-full aspect-video border border-white/20 bg-white/5 overflow-hidden">
          <img src={work.image} alt={work.title} class="w-full h-full object-cover opacity-80" />
        </div>

        <p class="text-white/80 text-lg leading-relaxed">
          {work.details}
        </p>

      </section>
    {/each}

  </div>
</main>