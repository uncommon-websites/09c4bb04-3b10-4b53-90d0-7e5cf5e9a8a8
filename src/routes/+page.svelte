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
    "https://images.unsplash.com/photo-1522163182402-834f871fd851?q=80&w=600&auto=format&fit=crop", // Climbing
    "https://images.unsplash.com/photo-1544967082-d9d25d867d66?q=80&w=600&auto=format&fit=crop", // Bench/View
    "https://images.unsplash.com/photo-1469854523086-cc02fe5d8800?q=80&w=600&auto=format&fit=crop", // Hiking/Mountain
    "https://images.unsplash.com/photo-1476480862126-209bfaa8edc8?q=80&w=600&auto=format&fit=crop", // Running
    "https://images.unsplash.com/photo-1551698618-1dfe5d97d256?q=80&w=600&auto=format&fit=crop", // Snow
    "https://images.unsplash.com/photo-1596329606822-790d946d9e29?q=80&w=600&auto=format&fit=crop"  // Park
  ];

  const benefitCards = [
    {
      title: "All your data. One place.",
      desc: "Holo takes into account your lifestyle and habits, your past results, and connects your wearable data.",
      image: "https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=800&auto=format&fit=crop"
    },
    {
      title: "Better control over your performance.",
      desc: "Start thriving by tracking your daily strain, recovery and sleep.",
      image: "https://images.unsplash.com/photo-1506126613408-eca07ce68773?q=80&w=800&auto=format&fit=crop"
    },
    {
      title: "Proactive care.",
      desc: "Health is not just the absence of illness but the engagement with vitality everyday.",
      image: "https://images.unsplash.com/photo-1544717305-2782549b5136?q=80&w=800&auto=format&fit=crop"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Chose the plan that fits you better.",
      desc: "Two options available. Get the Core plan with 110+ biomarkers to access the most advance lab test or choose the Starter plan to test 60+ essential biomarkers.",
      image: "plan"
    },
    {
      step: 2,
      title: "Schedule your appointment.",
      desc: "Choose the most convenient lab location for you and follow the instructions before the test.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Receive first results.",
      desc: "Within 24 hours directly on your app. When all your results are available, our medical team will start working on your Clinician Notes.",
      image: "results"
    },
    {
      step: 4,
      title: "Your Clinician Notes are ready.",
      desc: "Receive your Clinician Notes and personalized Action Plan within 7 days from your results.",
      image: "notes"
    },
    {
      step: 5,
      title: "Start improving.",
      desc: "Continue your health journey together with Holo AI and your Action Plan. Recheck in 6 months with the Follow-up test.",
      image: "improve"
    }
  ];

  const faqs = [
    "What does a Holo membership include?",
    "Is Holo for you?",
    "What more does Holo offer than my regular doctor or insurance?",
    "I recently got tested. Should I wait to join Holo?",
    "Which biomarkers are included in the Holo membership?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Your companion<br />for lifelong vitality.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Test 110+ biomarkers every year, track all your health in a single place, and get insights from top doctors. All starting at just €199.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Start testing
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Lifestyle" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- App Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Phone Mockup -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-[280px] h-[580px] bg-black rounded-[40px] border-[8px] border-black shadow-2xl overflow-hidden">
          <div class="absolute top-0 left-0 right-0 h-6 bg-black z-20 flex justify-center">
            <div class="w-20 h-4 bg-black rounded-b-xl"></div>
          </div>
          <div class="w-full h-full bg-white pt-10 px-4 overflow-hidden flex flex-col">
            <!-- Mock UI -->
            <div class="flex justify-between items-center mb-6">
              <div class="w-8 h-8 rounded-full bg-gray-200"></div>
              <div class="w-8 h-8 rounded-full bg-gray-100"></div>
            </div>
            <div class="mb-6">
              <div class="text-xs text-gray-500 mb-1">30 June</div>
              <div class="text-2xl font-bold">1</div>
            </div>
            <div class="space-y-3">
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="w-1/2 h-2 bg-gray-200 rounded mb-2"></div>
                <div class="w-full h-1 bg-green-400 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="w-1/2 h-2 bg-gray-200 rounded mb-2"></div>
                <div class="w-full h-1 bg-orange-400 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="w-1/2 h-2 bg-gray-200 rounded mb-2"></div>
                <div class="w-full h-1 bg-blue-400 rounded"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Your health at a glance.<br />
          See your daily Strain, Recovery and Sleep goals. Explore your biomarkers, understand what they mean, and access your Personalized Report, including your Action Plan created after your test.
        </h2>
        <div class="flex items-center justify-between pt-4">
          <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
            {@html PlayCircle}
            Watch video
          </button>
          <div class="flex gap-2">
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronLeft}
            </button>
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronRight}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        You deserve to live fully, longer, and better.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        Your health is more than numbers, it's your story, your future. Taking care of it today means giving yourself the chance to enjoy more years with strength, clarity, and vitality. We're here to help you protect what truly matters: a healthier, longer life.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-3xl overflow-hidden group">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/20 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h3 class="text-2xl font-medium mb-3">{card.title}</h3>
            <p class="text-white/80 text-sm leading-relaxed font-light">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center">
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-[#1A1A1A] mb-8">
      "I've always wanted a tool like Holo. It gives people real power over their health in a way that's simple and intuitive. I love how deeply personalized it is, making it easier than ever to understand your body and make smart choices"
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=100&auto=format&fit=crop" alt="Doctor" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Dra. Cécile Merad</div>
        <div class="text-gray-500 text-xs">Functional Doctor</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">15 minutes lab visit.</h3>
        <p class="text-gray-500 text-sm font-light">In and out. Take your blood and urine test. One minute with the nurse. Quick and simple.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">24 hours first results.</h3>
        <p class="text-gray-500 text-sm font-light">Your lab test data, fast. Complete results in five business days.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Clinician Notes in 1 week.</h3>
        <p class="text-gray-500 text-sm font-light">From data to a clear Action Plan to guide you along your health path.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">With two lab tests a year, daily tracking from your phone and wearables, and guidance from real doctors, Holo helps you understand what's going on inside so you can make smarter, healthier choices.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col items-center text-center max-w-2xl mx-auto shadow-sm">
          <div class="w-full text-left mb-8">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light text-sm max-w-lg">{step.desc}</p>
          </div>
          
          <!-- Phone Mockup for Step -->
          <div class="relative w-[240px] h-[480px] bg-black rounded-[35px] border-[6px] border-black shadow-xl overflow-hidden mt-4">
             <div class="absolute top-0 left-0 right-0 h-5 bg-black z-20 flex justify-center">
                <div class="w-16 h-3 bg-black rounded-b-lg"></div>
             </div>
             <div class="w-full h-full bg-white pt-8 px-3 overflow-hidden">
                <!-- Dynamic Content based on step -->
                {#if step.image === 'plan'}
                  <div class="space-y-3 mt-4">
                    <div class="p-3 border rounded-xl border-black bg-gray-50">
                      <div class="font-bold text-xs mb-1">Optimal ID</div>
                      <div class="h-1 w-full bg-gray-200 rounded"></div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-400">Essential</div>
                       <div class="h-1 w-full bg-gray-100 rounded"></div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold mb-4">Appointment</div>
                     <div class="bg-gray-100 h-32 rounded-xl mb-3 flex items-center justify-center text-xs text-gray-400">Map View</div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Confirm</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-black h-full -mx-3 -mt-8 pt-10 px-3 text-white">
                      <div class="text-center mb-6">
                        <div class="w-12 h-12 bg-gray-700 rounded-full mx-auto mb-2"></div>
                        <div class="text-sm font-bold">Grace Parker</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                      </div>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Health Status</div>
                      <div class="text-[10px] text-gray-500 leading-relaxed">
                        You usually make smart choices for your health through regular exercise...
                      </div>
                      <div class="bg-gray-50 p-2 rounded text-[10px] text-gray-600">
                        Since your diet lacks enough fruits and vegetables...
                      </div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1">
                        <div class="bg-gray-100 p-2 rounded-lg rounded-tl-none text-[10px] mb-2 max-w-[80%]">
                          What benefits can I get by bringing ApoB closer to the optimal range?
                        </div>
                        <div class="bg-blue-50 p-2 rounded-lg rounded-tr-none text-[10px] ml-auto max-w-[80%]">
                          By lowering ApoB, you reduce the number of cholesterol-carrying particles...
                        </div>
                      </div>
                      <div class="h-10 border-t mt-2"></div>
                   </div>
                {/if}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Map Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">A five star experience.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">We partner exclusively with renowned labs.</h2>
        </div>
        <!-- Abstract Map Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-30 mt-20">
           <svg viewBox="0 0 200 100" class="w-full h-full text-gray-500 fill-current">
              <!-- Simplified dot map representation -->
              {#each Array(100) as _, i}
                <circle cx={Math.random() * 200} cy={Math.random() * 100} r={Math.random() * 1.5} />
              {/each}
           </svg>
        </div>
      </div>

      <!-- Privacy Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Your data is safe with us.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">We're built to protect your privacy by default.</h2>
        </div>
        <!-- Blurred Text Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-4xl font-mono text-gray-600 opacity-20 blur-sm select-none break-all p-8">
             Elizab|%b$9yT Willi|I7m/e Magn|&5a! Trigly|?Pm_Lw
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="join">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Preventive healthcare for everyone.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">Top-tier testing, real-time tracking, and dedicated clinician guidance—made affordable. Because investing in prevention is the most important investing of your life.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Starter Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-gray-100 rounded-full mb-6"></div>
        <h3 class="text-2xl font-medium mb-1">Starter</h3>
        <p class="text-sm text-gray-500 mb-6">Begin your health journey.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">€199</span>
          <span class="text-gray-400 text-sm">/yr</span>
          <div class="text-[10px] text-pink-500 mt-1 font-medium">Pay in installments with Klarna.</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Two tests a year covering 60+ essential biomarkers.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Measure your Biological Age and Aging Rate with every test.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Clinician Notes and personalized Action Plan to guide your health.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Join now</button>
      </div>

      <!-- Core Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-[#FFF8E1] px-4 py-1 rounded-bl-xl text-xs font-medium text-orange-800">Most Popular</div>
        <div class="w-12 h-12 bg-orange-100 rounded-full mb-6"></div>
        <h3 class="text-2xl font-medium mb-1">Core</h3>
        <p class="text-sm text-gray-500 mb-6">The most advanced longevity membership.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">€399</span>
          <span class="text-gray-400 text-sm">/yr</span>
          <div class="text-[10px] text-pink-500 mt-1 font-medium">Pay in installments with Klarna.</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Full Core test of 110+ biomarkers plus a Follow-up with 60+ biomarkers to track change.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            First test includes an extended Hormonal and Vitamins panel for deeper insights.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Clinician Notes and a personalized Action Plan built on your most complete lab testing profile.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Join now</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Your questions answered.</h2>
    <div class="space-y-4">
      {#each faqs as question}
        <div class="border-b border-gray-200 py-4 flex justify-between items-center cursor-pointer group hover:bg-gray-50/50 transition-colors px-2">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-black transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View all Frequently Asked Questions
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <div class="relative w-5 h-5 flex items-center justify-center">
              <div class="absolute w-full h-[1.5px] bg-black rotate-45"></div>
              <div class="absolute w-full h-[1.5px] bg-black -rotate-45"></div>
              <div class="absolute w-[1.5px] h-full bg-black"></div>
              <div class="absolute w-full h-[1.5px] bg-black"></div>
           </div>
           <span class="font-bold text-lg tracking-widest">HOLO</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#" class="hover:text-black">Biomarkers</a>
          <a href="#" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Blog</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black">{@html XIcon}</a>
          <a href="#" class="hover:text-black">{@html Instagram}</a>
          <a href="#" class="hover:text-black">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">Holo is a technology company, not a laboratory or medical provider. All lab and medical services are provided by independent third parties, who set their own pricing. While Holo facilitates access to certain providers, it does not recommend or refer healthcare providers. Holo does not offer medical advice, lab services, diagnosis, treatment, or medical opinions. All services do not replace medical care or consultations with a licensed provider. If you have questions about lab results, consult a primary care physician or other licensed provider. All information provided by Holo is for general informational purposes only.</p>
        <p>Holo's membership pricing includes prepaid access to certain third-party lab services. Some home and lab draw fees may apply. Additional payments beyond standard membership pricing. For more details, see our Terms & Conditions.</p>
        <p class="mt-2">By providing your phone number, you agree to receive text messages from Holo. Message and data rates may apply. Message frequency varies.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #F9F8F6;
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

