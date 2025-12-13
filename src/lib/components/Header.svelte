<script>
  import { onMount } from 'svelte';

  let isScrolled = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 10;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 px-6 py-4 flex items-center justify-between {isScrolled ? 'bg-white/95 backdrop-blur-md shadow-md border-b border-gray-100' : 'bg-white border-b border-gray-100'}">
  <div class="flex items-center">
    <!-- Logo -->
    <a href="/" class="flex items-center gap-2 group">
      <div class="relative w-5 h-5 flex items-center justify-center">
        <div class="absolute w-full h-[1.5px] bg-[#c98e4a] rotate-45"></div>
        <div class="absolute w-full h-[1.5px] bg-[#c98e4a] -rotate-45"></div>
        <div class="absolute w-[1.5px] h-full bg-[#c98e4a]"></div>
        <div class="absolute w-full h-[1.5px] bg-[#c98e4a]"></div>
      </div>
      <span class="font-bold text-xl tracking-widest text-gray-900">SPARTAN</span>
    </a>
  </div>

  <div class="flex items-center gap-8">
    <nav class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
      <a href="#products" class="hover:text-[#c98e4a] transition-colors">Products</a>
      <a href="#results" class="hover:text-[#c98e4a] transition-colors">Results</a>
      <a href="#faq" class="hover:text-[#c98e4a] transition-colors">FAQ</a>
    </nav>
    <a href="#shop" class="bg-[#c98e4a] text-white text-[13px] font-semibold px-6 py-2.5 rounded-md hover:bg-[#b57d3d] transition-colors">
      Shop Now
    </a>
  </div>
</header>