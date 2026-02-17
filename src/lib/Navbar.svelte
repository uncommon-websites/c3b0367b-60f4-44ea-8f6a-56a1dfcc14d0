<script lang="ts">
  import { onMount } from 'svelte';
  
  let isMenuOpen = $state(false);
  let isScrolled = $state(false);

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 20;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<nav class="fixed top-0 left-0 right-0 z-[100] transition-all duration-300 {isScrolled ? 'bg-[#130b29]/90 backdrop-blur-md border-b border-white/10 py-3' : 'bg-transparent py-5'}">
  <div class="max-w-7xl mx-auto px-6 flex items-center justify-between">
    <div class="flex items-center gap-6">
      <!-- Logo -->
      <a href="/" class="font-bold text-xl tracking-tight text-white">Velobeat</a>
      
      <!-- Vertical Divider -->
      <div class="h-5 w-px bg-white/20 hidden md:block"></div>
      
      <!-- Left Links -->
      <div class="hidden md:flex items-center gap-6 text-sm font-medium text-gray-300">
        <div class="relative group">
          <button class="flex items-center gap-1 hover:text-white transition-colors">
            Moscow Studio
            <svg class="w-3 h-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
          </button>
          <div class="absolute top-full left-0 mt-2 w-48 bg-[#1e1633] border border-white/10 rounded-xl p-2 opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all">
            <a href="#moscow" class="block px-4 py-2 text-xs text-gray-300 hover:text-white hover:bg-white/5 rounded-lg">Ulitsa Fadeeva, 4a</a>
          </div>
        </div>
        <div class="relative group">
          <button class="flex items-center gap-1 hover:text-white transition-colors">
            St. Petersburg Studio
            <svg class="w-3 h-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
          </button>
          <div class="absolute top-full left-0 mt-2 w-48 bg-[#1e1633] border border-white/10 rounded-xl p-2 opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all">
            <a href="#spb" class="block px-4 py-2 text-xs text-gray-300 hover:text-white hover:bg-white/5 rounded-lg">Central Studio</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Right Links -->
    <div class="flex items-center gap-6 text-sm font-medium">
      <div class="hidden md:flex items-center gap-6 text-gray-300">
        <a href="#about" class="hover:text-white transition-colors">About</a>
        <a href="#careers" class="hover:text-white transition-colors">Careers</a>
        <div class="h-5 w-px bg-white/20"></div>
        <button class="flex items-center gap-1 hover:text-white transition-colors">
          Login
          <svg class="w-3 h-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
        </button>
      </div>
      <a href="#pricing" class="bg-white/10 hover:bg-white/20 border border-white/10 rounded-full px-4 py-2 text-white transition-all flex items-center gap-2 group">
        Buy Package
        <svg class="w-3 h-3 group-hover:translate-x-0.5 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
      </a>

      <!-- Mobile menu button -->
      <div class="md:hidden flex items-center">
        <button on:click={() => isMenuOpen = !isMenuOpen} class="text-white focus:outline-none">
          <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d={isMenuOpen ? "M6 18L18 6M6 6l12 12" : "M4 6h16M4 12h16M4 18h16"} />
          </svg>
        </button>
      </div>
    </div>
  </div>

  <!-- Mobile Menu -->
  {#if isMenuOpen}
    <div class="md:hidden bg-[#130b29] border-b border-white/10 px-6 py-8 space-y-6">
      <div class="space-y-4">
        <a href="#moscow" class="block text-lg font-medium text-white">Moscow Studio</a>
        <a href="#spb" class="block text-lg font-medium text-white">St. Petersburg Studio</a>
        <a href="#about" class="block text-lg font-medium text-white">About</a>
        <a href="#careers" class="block text-lg font-medium text-white">Careers</a>
      </div>
      <div class="pt-6 border-t border-white/10 space-y-4">
        <a href="#" class="block text-lg font-medium text-white">Login</a>
        <a href="#pricing" class="block w-full text-center bg-white text-black font-bold py-4 rounded-full">Buy Package</a>
      </div>
    </div>
  {/if}
</nav>
