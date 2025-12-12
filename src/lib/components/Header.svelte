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

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 px-6 py-5 flex items-center justify-between {isScrolled ? 'bg-[#F9F8F6]/90 backdrop-blur-md shadow-sm' : 'bg-transparent'}">
  <div class="flex items-center">
    <!-- Logo -->
    <a href="/" class="flex items-center gap-2 group">
      <div class="relative w-5 h-5 flex items-center justify-center">
        <div class="absolute w-full h-[1.5px] bg-black rotate-45"></div>
        <div class="absolute w-full h-[1.5px] bg-black -rotate-45"></div>
        <div class="absolute w-[1.5px] h-full bg-black"></div>
        <div class="absolute w-full h-[1.5px] bg-black"></div>
      </div>
      <span class="font-bold text-xl tracking-widest text-[#1A1A1A]">SPARTAN</span>
    </a>
  </div>

  <div class="flex items-center gap-8">
    <nav class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
      <a href="#products" class="hover:text-black transition-colors">Products</a>
      <a href="#results" class="hover:text-black transition-colors">Results</a>
      <a href="#faq" class="hover:text-black transition-colors">FAQ</a>
    </nav>
    <a href="#shop" class="bg-[#1A1A1A] text-white text-[13px] font-medium px-5 py-2.5 rounded-sm hover:bg-black transition-colors">
      Shop Now
    </a>
  </div>
</header>