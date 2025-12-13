<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  
  // Icons
  const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
  const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
  const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
  const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
  const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
  const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
  const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
  const LinkedIn = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
  const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 12"/></svg>`;

  // Data
  const heroImages = [
    "/generated/image-confident-man-in-his-30s-with-thick-heal-1765523199208-0.webp",
    "/generated/image-man-massaging-hair-product-into-scalp-in-1765523426535-0.webp",
    "/generated/image-close-up-of-healthy-scalp-and-hair-folli-1765523202597-2.webp",
    "/generated/image-professional-man-in-business-casual-atti-1765523206263-3.webp",
    "/generated/image-mans-hands-holding-premium-hair-care-pro-1765523208798-4.webp",
    "/generated/image-athletic-man-with-thick-dark-hair-in-cas-1765523429273-1.webp"
  ];

  const benefitCards = [
    {
      title: "Medical-Grade Exfoliation",
      desc: "Our patented silicone bristles remove toxins and buildup from your scalp, allowing nutrients to reach hair follicles where they're needed most.",
      image: "/generated/image-medical-grade-silicone-scalp-brush-on-cl-1765523211282-6.webp"
    },
    {
      title: "Plant-Powered Formula",
      desc: "100% natural botanical ingredients stimulate follicles and nourish your scalp. No harsh chemicals, just pure science-backed results.",
      image: "/generated/image-natural-botanical-ingredients-like-saw-p-1765523213612-7.webp"
    },
    {
      title: "Doctor Trusted",
      desc: "Endorsed by 7+ board-certified dermatologists and urologists. The brand health experts recommend for real hair regrowth.",
      image: "/generated/image-professional-male-dermatologist-in-white-1765523216556-8.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Exfoliate Your Scalp",
      desc: "Use the Premium Scalp Brush with medical-grade silicone bristles to remove toxins, buildup, and dead skin cells. Just one use reveals a healthier scalp.",
      image: "plan"
    },
    {
      step: 2,
      title: "Apply Root Activator Shampoo",
      desc: "Massage our plant-powered formula into your clean scalp 3-4 times per week. Natural ingredients penetrate deep to nourish follicles.",
      image: "schedule"
    },
    {
      step: 3,
      title: "See First Results",
      desc: "Week 1: Healthier scalp and more vibrant hair. Week 6: Hair roots growing back with visible results. Week 12: Thicker, stronger new growth.",
      image: "results"
    },
    {
      step: 4,
      title: "Enjoy Fuller Hair",
      desc: "By week 18, experience fuller, thicker hair with complete coverage. Continue the routine to maintain your transformation and confidence.",
      image: "notes"
    }
  ];

  const faqs = [
    "How long until I see results with SPARTAN?",
    "Is SPARTAN safe for all hair types?",
    "What makes SPARTAN different from other hair loss solutions?",
    "Do I need to use both the brush and shampoo?",
    "What's included in the 90-day money-back guarantee?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden bg-white">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <div class="inline-block px-4 py-1.5 bg-primary-50 border border-primary-200 rounded-full text-xs font-semibold text-primary-700 mb-6 uppercase tracking-wide">
      Medical-Grade Hair Restoration
    </div>
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-semibold tracking-tight text-gray-900 mb-6 leading-[1.1]">
      Reverse Hair Thinning.<br />Reclaim Your Confidence.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed">
      Revolutionary solutions for the modern man. Medical-grade exfoliation meets botanical follicle stimulation. Trusted by 50,000+ men and endorsed by doctors.
    </p>
    <button class="bg-[#c98e4a] text-white px-8 py-3.5 rounded-md font-semibold hover:bg-[#b57d3d] transition-all hover:shadow-lg">
      Shop Hair Growth System
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar bg-gray-50 py-8">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-lg overflow-hidden flex-shrink-0 border border-gray-200">
          <img src={img} alt="SPARTAN Hair Growth Results" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- Product Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="products">
    <div class="bg-gray-50 rounded-xl p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 border border-gray-200">
      <!-- Product Visual -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-full max-w-md aspect-square flex items-center justify-center">
          <div class="absolute inset-0 bg-gradient-to-br from-primary-50 to-primary-100 rounded-full opacity-40"></div>
          <img src="/generated/image-medical-grade-silicone-scalp-brush-on-cl-1765523211282-6.webp" alt="SPARTAN Scalp Brush" class="relative z-10 w-4/5 h-4/5 object-contain" />
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-semibold leading-tight text-gray-900">
          The Complete Hair Growth System.<br />
          <span class="text-gray-600 text-xl font-normal mt-2 block">Medical-grade silicone exfoliation removes toxins. Plant-powered formula stimulates follicles. Results you can see in 6 weeks.</span>
        </h2>
        <div class="space-y-4">
          <div class="flex items-start gap-3 p-3 bg-white rounded-lg border border-gray-200">
            <span class="text-[#c98e4a] mt-1">{@html Check}</span>
            <div>
              <div class="font-semibold text-gray-900">Premium Scalp Brush</div>
              <div class="text-sm text-gray-600">Medical-grade silicone bristles</div>
            </div>
          </div>
          <div class="flex items-start gap-3 p-3 bg-white rounded-lg border border-gray-200">
            <span class="text-[#c98e4a] mt-1">{@html Check}</span>
            <div>
              <div class="font-semibold text-gray-900">Root Activator Shampoo</div>
              <div class="text-sm text-gray-600">100% natural botanical formula</div>
            </div>
          </div>
          <div class="flex items-start gap-3 p-3 bg-white rounded-lg border border-gray-200">
            <span class="text-[#c98e4a] mt-1">{@html Check}</span>
            <div>
              <div class="font-semibold text-gray-900">90-Day Guarantee</div>
              <div class="text-sm text-gray-600">Risk-free money-back promise</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto bg-white">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-semibold tracking-tight text-gray-900 leading-tight">
        Your hair. Your confidence. Your transformation.
      </h2>
      <p class="text-gray-600 text-lg leading-relaxed">
        Hair loss isn't just about appearance—it's about how you feel every day. We identified the root cause: scalp blocked by toxins preventing nutrient absorption. Our dual-action solution removes toxins while nourishing your scalp and hair. No harsh chemicals. Just science-backed results that restore your confidence.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto bg-white">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-lg overflow-hidden group border border-gray-200">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <div class="w-10 h-1 bg-[#c98e4a] mb-4"></div>
            <h3 class="text-2xl font-semibold mb-3">{card.title}</h3>
            <p class="text-white/90 text-sm leading-relaxed">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center bg-gray-50 rounded-xl border border-gray-200" id="results">
    <div class="w-12 h-12 bg-[#c98e4a] rounded-full mx-auto mb-6 flex items-center justify-center">
      <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
        <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z"/>
      </svg>
    </div>
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-gray-900 mb-8">
      "After just 8 weeks, I noticed real regrowth in my thinning areas. The scalp brush feels amazing and the shampoo doesn't have that chemical smell. My confidence is back and people are noticing. Best investment I've made in myself."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-happy-male-customer-in-his-30s-with-heal-1765523219365-9.webp" alt="Customer" class="w-14 h-14 rounded-full object-cover border-2 border-[#c98e4a]" />
      <div class="text-center">
        <div class="font-semibold text-sm text-gray-900">Marcus T.</div>
        <div class="text-gray-600 text-xs">SPARTAN Customer</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200 bg-white">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div class="p-6 bg-gray-50 rounded-lg border border-gray-200">
        <div class="text-3xl font-bold text-[#c98e4a] mb-2">50,000+</div>
        <h3 class="text-lg font-semibold mb-2 text-gray-900">Happy Customers</h3>
        <p class="text-gray-600 text-sm">Join thousands of men who've reversed hair thinning and reclaimed their confidence with SPARTAN.</p>
      </div>
      <div class="p-6 bg-gray-50 rounded-lg border border-gray-200">
        <div class="text-3xl font-bold text-[#c98e4a] mb-2">6 Weeks</div>
        <h3 class="text-lg font-semibold mb-2 text-gray-900">Visible Results</h3>
        <p class="text-gray-600 text-sm">See visible hair regrowth in thinning areas. Fuller, thicker coverage by week 18 with consistent use.</p>
      </div>
      <div class="p-6 bg-gray-50 rounded-lg border border-gray-200">
        <div class="text-3xl font-bold text-[#c98e4a] mb-2">90 Days</div>
        <h3 class="text-lg font-semibold mb-2 text-gray-900">Money-Back Guarantee</h3>
        <p class="text-gray-600 text-sm">Try SPARTAN risk-free. If you're not satisfied, get a full refund. No questions asked.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto bg-white">
    <div class="mb-16 max-w-md">
      <div class="w-12 h-1 bg-[#c98e4a] mb-4"></div>
      <h2 class="text-4xl font-semibold mb-6 text-gray-900">How it works.</h2>
      <p class="text-gray-600">Our dual-action system removes toxins blocking your scalp while delivering botanical nutrients directly to hair follicles. Simple routine, powerful results.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-gray-50 rounded-lg p-8 md:p-12 flex flex-col md:flex-row items-center gap-8 max-w-4xl mx-auto border border-gray-200">
          <div class="w-full md:w-2/3 text-left">
            <span class="inline-block w-10 h-10 rounded-lg bg-[#c98e4a] text-white text-center leading-10 text-sm font-bold mb-4">{step.step}</span>
            <h3 class="text-2xl font-semibold mb-3 text-gray-900">{step.title}</h3>
            <p class="text-gray-600 text-base">{step.desc}</p>
          </div>
          
          <!-- Simple Icon Visual -->
          <div class="w-full md:w-1/3 flex justify-center">
            <div class="w-32 h-32 rounded-lg bg-white border-2 border-[#c98e4a] flex items-center justify-center">
              {#if step.image === 'plan'}
                <svg class="w-16 h-16 text-[#c98e4a]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/>
                </svg>
              {:else if step.image === 'schedule'}
                <svg class="w-16 h-16 text-[#c98e4a]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z"/>
                </svg>
              {:else if step.image === 'results'}
                <svg class="w-16 h-16 text-[#c98e4a]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
                </svg>
              {:else}
                <svg class="w-16 h-16 text-[#c98e4a]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5"/>
                </svg>
              {/if}
            </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto bg-white">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Media Coverage Card -->
      <div class="bg-gray-900 rounded-lg p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden border border-gray-800">
        <div class="relative z-10">
          <div class="w-10 h-1 bg-[#c98e4a] mb-4"></div>
          <h3 class="text-sm font-semibold text-gray-400 mb-2 uppercase tracking-wide">Featured In</h3>
          <h2 class="text-2xl md:text-3xl font-semibold max-w-xs mb-8">Trusted by leading media outlets.</h2>
          <div class="grid grid-cols-2 gap-6 mt-12">
            <div class="text-gray-300 font-bold text-lg">LA WEEKLY</div>
            <div class="text-gray-300 font-bold text-lg">USA TODAY</div>
            <div class="text-gray-300 font-bold text-lg">GQ</div>
            <div class="text-gray-300 font-bold text-lg">ROLLING STONE</div>
          </div>
        </div>
      </div>

      <!-- Doctor Endorsements Card -->
      <div class="bg-gray-900 rounded-lg p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden border border-gray-800">
        <div class="relative z-10">
          <div class="w-10 h-1 bg-[#c98e4a] mb-4"></div>
          <h3 class="text-sm font-semibold text-gray-400 mb-2 uppercase tracking-wide">Medical Backing</h3>
          <h2 class="text-2xl md:text-3xl font-semibold max-w-xs mb-8">Endorsed by 7+ board-certified doctors.</h2>
          <div class="space-y-4 mt-8">
            <div class="border-l-2 border-[#c98e4a] pl-4 py-2">
              <div class="text-sm font-semibold">Dr. Jessica Burgy</div>
              <div class="text-xs text-gray-400">Board Certified Dermatologist</div>
            </div>
            <div class="border-l-2 border-[#c98e4a] pl-4 py-2">
              <div class="text-sm font-semibold">Dr. Omer Ibrahim</div>
              <div class="text-xs text-gray-400">Dermatologist & Cosmetic Laser Specialist</div>
            </div>
            <div class="border-l-2 border-[#c98e4a] pl-4 py-2">
              <div class="text-sm font-semibold">Dr. Stephen Lewellis</div>
              <div class="text-xs text-gray-400">Board Certified Dermatologist</div>
            </div>
            <div class="text-xs text-gray-400 mt-6 pl-4">+ 4 more medical professionals</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto bg-gray-50" id="shop">
    <div class="text-center mb-16">
      <div class="w-12 h-1 bg-[#c98e4a] mx-auto mb-4"></div>
      <h2 class="text-3xl md:text-4xl font-semibold mb-4 text-gray-900">Choose your transformation.</h2>
      <p class="text-gray-600 max-w-2xl mx-auto">Premium hair growth solutions backed by science. All products come with our 90-day money-back guarantee and free shipping over $70.</p>
    </div>

    <div class="grid md:grid-cols-3 gap-6 max-w-6xl mx-auto">
      <!-- Scalp Brush -->
      <div class="bg-white rounded-lg p-8 flex flex-col border border-gray-200">
        <div class="w-12 h-12 bg-primary-50 rounded-lg mb-6 flex items-center justify-center border border-primary-200">
          <svg class="w-6 h-6 text-[#c98e4a]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/>
          </svg>
        </div>
        <h3 class="text-2xl font-semibold mb-1 text-gray-900">Scalp Brush</h3>
        <p class="text-sm text-gray-600 mb-6">Medical-grade exfoliation tool.</p>
        <div class="mb-8">
          <span class="text-3xl font-bold text-gray-900">$19.90</span>
          <div class="text-xs text-gray-400 line-through mt-1">Regular $49.95</div>
          <div class="text-xs text-[#c98e4a] font-semibold mt-1">Save up to 66%</div>
        </div>
        <ul class="space-y-3 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Medical-grade silicone bristles
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Removes toxins & buildup
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Results after one use
          </li>
        </ul>
        <button class="w-full bg-gray-900 text-white py-3 rounded-md font-semibold hover:bg-gray-800 transition-colors">Add to Cart</button>
      </div>

      <!-- Root Activator Shampoo -->
      <div class="bg-white rounded-lg p-8 flex flex-col border border-gray-200">
        <div class="w-12 h-12 bg-primary-50 rounded-lg mb-6 flex items-center justify-center border border-primary-200">
          <svg class="w-6 h-6 text-[#c98e4a]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z"/>
          </svg>
        </div>
        <h3 class="text-2xl font-semibold mb-1 text-gray-900">Root Activator</h3>
        <p class="text-sm text-gray-600 mb-6">Plant-powered shampoo.</p>
        <div class="mb-8">
          <span class="text-3xl font-bold text-gray-900">$59.95</span>
          <div class="text-xs text-gray-400 line-through mt-1">Regular $129.95</div>
          <div class="text-xs text-[#c98e4a] font-semibold mt-1">Subscribe & Save 10%</div>
        </div>
        <ul class="space-y-3 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            100% natural ingredients
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Stimulates follicles
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Results in 4-8 weeks
          </li>
        </ul>
        <button class="w-full bg-gray-900 text-white py-3 rounded-md font-semibold hover:bg-gray-800 transition-colors">Add to Cart</button>
      </div>

      <!-- Full System -->
      <div class="bg-white rounded-lg p-8 flex flex-col relative overflow-hidden border-2 border-[#c98e4a]">
        <div class="absolute top-0 right-0 bg-[#c98e4a] text-white px-4 py-1.5 rounded-bl-lg text-xs font-bold uppercase tracking-wide">Best Value</div>
        <div class="w-12 h-12 bg-[#c98e4a] rounded-lg mb-6 flex items-center justify-center">
          <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"/>
          </svg>
        </div>
        <h3 class="text-2xl font-semibold mb-1 text-gray-900">Full System</h3>
        <p class="text-sm text-gray-600 mb-6">Complete hair growth solution.</p>
        <div class="mb-8">
          <span class="text-3xl font-bold text-gray-900">$179.95</span>
          <div class="text-xs text-gray-400 line-through mt-1">Regular $409.60</div>
          <div class="text-xs text-[#c98e4a] font-semibold mt-1">Save $229.65</div>
        </div>
        <ul class="space-y-3 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Premium Scalp Brush included
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Root Activator Shampoo
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            90-day money-back guarantee
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600">
            <span class="mt-0.5 text-[#c98e4a]">{@html Check}</span>
            Free shipping
          </li>
        </ul>
        <button class="w-full bg-[#c98e4a] text-white py-3 rounded-md font-semibold hover:bg-[#b57d3d] transition-all hover:shadow-lg">Get Started</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto bg-white" id="faq">
    <div class="text-center mb-12">
      <div class="w-12 h-1 bg-[#c98e4a] mx-auto mb-4"></div>
      <h2 class="text-3xl font-semibold text-gray-900">Your questions answered.</h2>
    </div>
    <div class="space-y-3">
      {#each faqs as question}
        <div class="border border-gray-200 rounded-lg py-4 px-5 flex justify-between items-center cursor-pointer group hover:border-[#c98e4a] transition-colors bg-gray-50 hover:bg-white">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-[#c98e4a] transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border-2 border-[#c98e4a] text-[#c98e4a] px-6 py-3 rounded-md text-sm font-semibold hover:bg-[#c98e4a] hover:text-white transition-colors">
        View All FAQs
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-gray-50">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <div class="relative w-5 h-5 flex items-center justify-center">
              <div class="absolute w-full h-[1.5px] bg-[#c98e4a] rotate-45"></div>
              <div class="absolute w-full h-[1.5px] bg-[#c98e4a] -rotate-45"></div>
              <div class="absolute w-[1.5px] h-full bg-[#c98e4a]"></div>
              <div class="absolute w-full h-[1.5px] bg-[#c98e4a]"></div>
           </div>
           <span class="font-bold text-lg tracking-widest text-gray-900">SPARTAN</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-semibold text-gray-600">
          <a href="#products" class="hover:text-[#c98e4a] transition-colors">Products</a>
          <a href="#results" class="hover:text-[#c98e4a] transition-colors">Results</a>
          <a href="#faq" class="hover:text-[#c98e4a] transition-colors">FAQ</a>
          <a href="#" class="hover:text-[#c98e4a] transition-colors">Terms & Conditions</a>
          <a href="#" class="hover:text-[#c98e4a] transition-colors">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-600">
          <a href="https://instagram.com/tryspartan_us" target="_blank" rel="noopener" class="hover:text-[#c98e4a] transition-colors">{@html Instagram}</a>
          <a href="#" class="hover:text-[#c98e4a] transition-colors">{@html XIcon}</a>
          <a href="#" class="hover:text-[#c98e4a] transition-colors">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-500 leading-relaxed max-w-5xl">
        <p class="mb-2">SPARTAN provides hair growth and grooming products for informational and cosmetic purposes. These statements have not been evaluated by the Food and Drug Administration. These products are not intended to diagnose, treat, cure, or prevent any disease. Results may vary by individual. All testimonials are from real customers but individual results may differ. For medical concerns about hair loss, please consult with a licensed healthcare provider.</p>
        <p>All SPARTAN products come with a 90-day money-back guarantee. If you're not satisfied with your results, contact us for a full refund. Free shipping applies to orders over $70 within the continental United States. For full details, see our Terms & Conditions.</p>
        <p class="mt-2">By providing your contact information, you agree to receive promotional messages from SPARTAN. Message and data rates may apply. You can unsubscribe at any time.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #ffffff;
    font-family: 'Inter', sans-serif;
  }
  
  .hide-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .hide-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>

