<script lang="ts">
  import Navbar from '$lib/Navbar.svelte';
  import Footer from '$lib/Footer.svelte';

  let activeTab = $state('moscow');

  const pricing = [
    { sessions: 1, price: 1400, perSession: 1400, validity: '30 days' },
    { sessions: 5, price: 6500, perSession: 1300, validity: '45 days' },
    { sessions: 10, price: 12000, perSession: 1200, validity: '90 days' },
    { sessions: 20, price: 22000, perSession: 1100, validity: '180 days' }
  ];

  const instructors = [
    { name: 'Andrey', role: 'Lead Motivator' },
    { name: 'Anna', role: 'Rhythm Expert' },
    { name: 'Valentin', role: 'Energy Coach' },
    { name: 'Vova', role: 'Beat Master' },
    { name: 'Danil', role: 'Power Specialist' },
    { name: 'Darya', role: 'Flow Instructor' }
  ];
</script>

<div class="min-h-screen font-sans text-white bg-[#130b29] overflow-x-hidden relative">
  <Navbar />

  <!-- Hero Section (Recreated from Reference) -->
  <header class="relative min-h-screen flex flex-col items-center justify-center pt-16 pb-32 px-4 w-full max-w-7xl mx-auto overflow-hidden">
    <!-- Background Effects -->
    <div class="fixed inset-0 bg-stars opacity-40 pointer-events-none z-0"></div>
    <div class="fixed inset-0 bg-gradient-overlay pointer-events-none z-0"></div>

    <!-- Main Hero Content -->
    <div class="relative z-10 flex flex-col items-center justify-center w-full">
        <!-- Headline -->
        <h1 class="text-balance text-5xl md:text-6xl lg:text-7xl font-serif text-center text-white mb-6 leading-[1.1] tracking-tight max-w-5xl animate-fade-in-up delay-100">
            The Rhythm of Your City: Synchronized Cycling
        </h1>

        <!-- Subheadline -->
        <p class="text-pretty text-lg md:text-xl text-gray-300 text-center max-w-3xl mx-auto mb-10 leading-relaxed animate-fade-in-up delay-200">
            Experience high-intensity 45-minute cardio sessions driven by the music. Break the isolation of boring gyms with our boutique full-body workouts in Moscow and St. Petersburg.
        </p>

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row items-center gap-4 mb-20 animate-fade-in-up delay-300">
            <a href="#booking" class="bg-white text-black font-medium rounded-full px-8 py-3.5 hover:bg-gray-100 transition-colors shadow-[0_0_20px_rgba(255,255,255,0.3)]">
                Book a Class
            </a>
            <a href="#classes" class="group flex items-center gap-3 bg-[#1e1633] text-white border border-white/20 rounded-full px-6 py-3.5 hover:bg-[#2a1f45] transition-colors">
                <span>Explore Classes</span>
                <div class="w-5 h-5 rounded-full border border-white/30 flex items-center justify-center group-hover:border-white transition-colors">
                    <svg class="w-2.5 h-2.5 ml-0.5" fill="currentColor" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
                </div>
            </a>
        </div>

        <!-- UI Interface Visualization -->
        <div class="relative w-full max-w-[900px] mx-auto animate-scale-in delay-400">
            <!-- Floating Cards -->
            <div class="absolute -top-24 left-0 md:-left-4 z-0 transform -rotate-6 animate-float" style="--rotation: -6deg; animation-delay: 0s;">
                <div class="bg-white rounded-xl p-3 shadow-xl border border-gray-100 flex flex-col gap-1 w-48">
                    <div class="flex items-center gap-2">
                        <div class="w-4 h-4 rounded-full bg-green-100 flex items-center justify-center">
                            <svg class="w-2.5 h-2.5 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M5 13l4 4L19 7"></path></svg>
                        </div>
                        <span class="text-xs font-bold text-green-700">30 Bikes</span>
                    </div>
                    <div class="text-[10px] text-gray-500 pl-6">Max Capacity per Session</div>
                </div>
            </div>

            <div class="absolute -top-28 left-1/4 z-0 transform rotate-3 animate-float" style="--rotation: 3deg; animation-delay: 1s;">
                <div class="bg-white rounded-xl p-3 shadow-xl border border-gray-100 flex flex-col gap-1 w-52">
                    <div class="flex items-center gap-2">
                        <svg class="w-4 h-4 text-orange-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"></path></svg>
                        <span class="text-xs font-bold text-orange-600">Pro Instructors</span>
                    </div>
                    <div class="text-[10px] text-gray-500 pl-6">Music-Driven Methodology</div>
                </div>
            </div>

            <div class="absolute -top-24 right-1/4 z-0 transform -rotate-2 animate-float" style="--rotation: -2deg; animation-delay: 2s;">
                <div class="bg-white rounded-xl p-3 shadow-xl border border-gray-100 flex flex-col gap-1 w-52">
                    <div class="flex items-center gap-2">
                        <svg class="w-4 h-4 text-blue-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.111 16.404a5.5 5.5 0 017.778 0M12 20h.01m-7.08-7.071c3.904-3.905 10.236-3.905 14.141 0M1.394 9.393c5.857-5.857 15.355-5.857 21.213 0"></path></svg>
                        <span class="text-xs font-bold text-blue-600">45 Minutes</span>
                    </div>
                    <div class="text-[10px] text-gray-500 pl-6">Full-body cardio blast</div>
                </div>
            </div>

            <div class="absolute -top-20 right-0 md:-right-4 z-0 transform rotate-6 animate-float" style="--rotation: 6deg; animation-delay: 1.5s;">
                <div class="bg-white rounded-xl p-3 shadow-xl border border-gray-100 flex flex-col gap-1 w-48">
                    <div class="flex items-center gap-2">
                        <svg class="w-4 h-4 text-emerald-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z"></path></svg>
                        <span class="text-xs font-bold text-emerald-600">Fadeeva Studio</span>
                    </div>
                    <div class="text-[10px] text-gray-500 pl-6">HQ: Ulitsa Fadeeva, 4a</div>
                </div>
            </div>

            <!-- Main Input Box -->
            <div class="relative z-20 bg-[#f8f9fa] rounded-2xl p-6 border-[3px] border-[#6ee7b7] glow-border w-full shadow-2xl">
                <div class="flex flex-col gap-8">
                    <div class="text-xl text-gray-800 font-medium">Ready for your next session at Ulitsa Fadeeva?</div>
                    
                    <div class="flex items-center justify-between">
                        <div class="flex items-center gap-3">
                            <button class="text-gray-400 hover:text-[#475569] transition-colors">
                                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4"></path></svg>
                            </button>
                            <div class="px-3 py-1 bg-white border border-gray-200 rounded-lg text-sm text-gray-500 shadow-sm">
                                Choose Class
                            </div>
                        </div>
                        
                        <button class="w-10 h-10 bg-[#333] rounded-full flex items-center justify-center hover:bg-black transition-colors shadow-lg">
                            <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18"></path></svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Bottom Tabs -->
            <div class="flex justify-center gap-3 mt-6 relative z-10">
                <div class="bg-white/90 backdrop-blur-sm px-4 py-2 rounded-full flex items-center gap-2 text-sm text-gray-600 shadow-lg border border-white/20">
                    Pick Studio
                </div>
                <div class="relative bg-[#d1fae5] px-4 py-2 rounded-full flex items-center gap-2 text-sm text-green-800 font-medium shadow-lg border border-green-200 cursor-pointer">
                    Book Bike
                </div>
                <div class="bg-white/90 backdrop-blur-sm px-4 py-2 rounded-full flex items-center gap-2 text-sm text-gray-600 shadow-lg border border-white/20">
                    See Stats
                </div>
            </div>
        </div>
    </div>

    <!-- Character Glow Effect -->
    <div class="absolute bottom-0 right-0 z-20 w-[300px] md:w-[450px] pointer-events-none translate-y-10">
        <div class="absolute bottom-0 right-0 w-full h-full bg-gradient-to-tl from-primary-500/40 via-purple-500/20 to-transparent rounded-full blur-3xl transform translate-y-1/4 translate-x-1/4"></div>
    </div>
  </header>

  <!-- Atmosphere Section -->
  <section id="atmosphere" class="py-24 bg-white text-[#130b29]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <div>
          <h2 class="text-4xl md:text-5xl font-serif mb-8 leading-tight">A Dynamic Cardio Party on Stationary Bikes</h2>
          <p class="text-lg text-gray-600 mb-8 leading-relaxed">
            Forget everything you know about boring gym workouts. At Velobeat, we pedal to the rhythm of inspiring music in a dimmed studio. It's an emotional reset and an energy boost that transforms your body and mind.
          </p>
          <div class="space-y-4">
            <div class="flex items-start gap-4">
              <div class="w-10 h-10 rounded-full bg-primary-100 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-primary-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19V6l12-3v13M9 19c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zm12-3c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zM9 10l12-3"></path></svg>
              </div>
              <div>
                <h4 class="font-bold text-lg">Music-Driven</h4>
                <p class="text-gray-500 text-sm">Every pedal stroke is synchronized with the beat for maximum cohesion.</p>
              </div>
            </div>
            <div class="flex items-start gap-4">
              <div class="w-10 h-10 rounded-full bg-primary-100 flex items-center justify-center flex-shrink-0">
                <svg class="w-5 h-5 text-primary-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
              </div>
              <div>
                <h4 class="font-bold text-lg">Full-Body Workout</h4>
                <p class="text-gray-500 text-sm">High-intensity cardio that engages your core and upper body without joint stress.</p>
              </div>
            </div>
          </div>
        </div>
        <div class="relative">
          <img src="/generated/image-a-high-energy-indoor-cycling-class-in-a--1771353860439-0.webp" alt="Cycling Atmosphere" class="rounded-3xl shadow-2xl" />
          <div class="absolute -bottom-6 -left-6 bg-primary-500 text-white p-6 rounded-2xl shadow-xl hidden md:block">
            <div class="text-3xl font-bold">45</div>
            <div class="text-xs uppercase tracking-widest font-bold">Minutes to Reset</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Intro Offer -->
  <section class="py-20 bg-primary-500 text-white">
    <div class="max-w-4xl mx-auto px-6 text-center">
      <h2 class="text-3xl md:text-5xl font-serif mb-6">New to Velobeat?</h2>
      <p class="text-xl mb-10 opacity-90">Experience the rhythm with our introductory offer. No strings attached.</p>
      <div class="bg-white text-black p-8 rounded-3xl shadow-2xl inline-block">
        <div class="text-sm font-bold text-primary-600 uppercase tracking-widest mb-2">Introductory Offer</div>
        <div class="text-5xl font-serif mb-4">3 Sessions</div>
        <div class="text-2xl font-bold mb-6">1,400₽</div>
        <a href="#" class="bg-primary-600 text-white px-10 py-4 rounded-full font-bold hover:bg-primary-700 transition-colors inline-block">Claim Offer</a>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section id="pricing" class="py-24 bg-white text-[#130b29]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-4xl font-serif mb-4">Choose Your Rhythm</h2>
        <p class="text-gray-500">Flexible packages for every fitness journey.</p>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        {#each pricing as item}
          <div class="border border-gray-100 rounded-3xl p-8 hover:shadow-xl transition-all hover:-translate-y-1 bg-gray-50 flex flex-col">
            <div class="text-gray-500 text-sm font-bold uppercase mb-4">{item.sessions} Session{item.sessions > 1 ? 's' : ''}</div>
            <div class="text-4xl font-serif mb-2">{item.price}₽</div>
            <div class="text-xs text-gray-400 mb-8">{item.perSession}₽ per session • Valid {item.validity}</div>
            <button class="mt-auto w-full border-2 border-[#130b29] py-3 rounded-full font-bold hover:bg-[#130b29] hover:text-white transition-all">Buy Package</button>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Amenities Section -->
  <section class="py-24 bg-gray-50 text-[#130b29]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <div class="order-2 lg:order-1">
          <img src="/generated/image-interior-of-a-modern-boutique-fitness-st-1771353870412-1.webp" alt="Studio Amenities" class="rounded-3xl shadow-2xl" />
        </div>
        <div class="order-1 lg:order-2">
          <h2 class="text-4xl font-serif mb-8">Everything You Need is Here</h2>
          <p class="text-lg text-gray-600 mb-10">Just bring your workout clothes. We take care of the rest so you can focus on the ride.</p>
          <div class="grid grid-cols-2 gap-8">
            <div class="space-y-2">
              <h4 class="font-bold">Cycling Shoes</h4>
              <p class="text-sm text-gray-500">Professional shoes provided for every class.</p>
            </div>
            <div class="space-y-2">
              <h4 class="font-bold">Fresh Towels</h4>
              <p class="text-sm text-gray-500">Complimentary towels for your workout and shower.</p>
            </div>
            <div class="space-y-2">
              <h4 class="font-bold">Full Showers</h4>
              <p class="text-sm text-gray-500">Equipped with cosmetics and makeup removal products.</p>
            </div>
            <div class="space-y-2">
              <h4 class="font-bold">Healthy Snacks</h4>
              <p class="text-sm text-gray-500">Nutritious fuel available post-ride.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Instructors Section -->
  <section id="instructors" class="py-24 bg-white text-[#130b29]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-8">
        <div class="max-w-2xl">
          <h2 class="text-4xl md:text-5xl font-serif mb-6">Led by the City's Most Energetic Motivators</h2>
          <p class="text-lg text-gray-600">Our 15 instructors aren't just trainers; they're performers who drive you to push past your limits.</p>
        </div>
        <a href="#" class="bg-[#130b29] text-white px-8 py-4 rounded-full font-bold hover:bg-black transition-colors">Join the Team</a>
      </div>
      
      <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-6">
        {#each instructors as person, i}
          <div class="group cursor-pointer">
            <div class="aspect-[3/4] bg-gray-100 rounded-2xl overflow-hidden mb-4 relative">
              {#if i === 0}
                <img src="/generated/image-a-close-up-of-smiling-energetic-fitnes-1771353875137-2.webp" alt={person.name} class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
              {:else}
                <div class="w-full h-full bg-gray-200 flex items-center justify-center text-gray-400">
                  <svg class="w-12 h-12" fill="currentColor" viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>
                </div>
              {/if}
              <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity flex items-end p-4">
                <p class="text-white text-xs font-bold uppercase tracking-widest">View Profile</p>
              </div>
            </div>
            <h4 class="font-bold text-lg">{person.name}</h4>
            <p class="text-gray-500 text-sm">{person.role}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Community Section -->
  <section class="py-24 bg-[#130b29] text-white overflow-hidden">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <div>
          <h2 class="text-4xl md:text-5xl font-serif mb-8">A Sense of Unity</h2>
          <blockquote class="text-2xl font-serif italic mb-8 leading-relaxed text-primary-200">
            "The energy of 30 people pedaling in perfect sync is indescribable. It's not just a workout; it's a collective high that carries me through the week."
          </blockquote>
          <div class="flex items-center gap-4">
            <div class="w-12 h-12 rounded-full bg-primary-500 flex items-center justify-center font-bold">M</div>
            <div>
              <div class="font-bold">Maria K.</div>
              <div class="text-gray-400 text-sm">Moscow Professional</div>
            </div>
          </div>
        </div>
        <div class="relative">
          <img src="/generated/image-a-group-of-three-friends-in-their-30s-la-1771353878647-3.webp" alt="Velobeat Community" class="rounded-3xl shadow-2xl border border-white/10" />
          <div class="absolute -top-6 -right-6 bg-white text-black p-6 rounded-2xl shadow-xl hidden md:block">
            <div class="text-3xl font-bold">30</div>
            <div class="text-xs uppercase tracking-widest font-bold text-gray-500">Like-minded People</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Locations Section -->
  <section id="locations" class="py-24 bg-white text-[#130b29]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-4xl font-serif mb-4">Find Your Studio</h2>
        <div class="flex justify-center gap-4 mt-8">
          <button 
            onclick={() => activeTab = 'moscow'}
            class="px-8 py-3 rounded-full font-bold transition-all {activeTab === 'moscow' ? 'bg-[#130b29] text-white shadow-lg' : 'bg-gray-100 text-gray-500 hover:bg-gray-200'}">
            Moscow
          </button>
          <button 
            onclick={() => activeTab = 'spb'}
            class="px-8 py-3 rounded-full font-bold transition-all {activeTab === 'spb' ? 'bg-[#130b29] text-white shadow-lg' : 'bg-gray-100 text-gray-500 hover:bg-gray-200'}">
            St. Petersburg
          </button>
        </div>
      </div>

      <div class="bg-gray-50 rounded-3xl p-8 md:p-12 border border-gray-100">
        {#if activeTab === 'moscow'}
          <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div>
              <h3 class="text-3xl font-serif mb-4">Moscow Headquarters</h3>
              <p class="text-gray-600 mb-6">Located in the heart of the city, our Fadeeva studio is where the Velobeat journey began.</p>
              <ul class="space-y-4 mb-8">
                <li class="flex items-center gap-3">
                  <svg class="w-5 h-5 text-primary-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                  <span>Ulitsa Fadeeva, 4a</span>
                </li>
                <li class="flex items-center gap-3">
                  <svg class="w-5 h-5 text-primary-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
                  <span>+7 (495) 150-17-49</span>
                </li>
              </ul>
              <button class="bg-primary-500 text-white px-8 py-4 rounded-full font-bold hover:bg-primary-600 transition-colors">Book a Bike in Moscow</button>
            </div>
            <div class="h-64 bg-gray-200 rounded-2xl flex items-center justify-center text-gray-400 italic">
              Interactive Map Placeholder
            </div>
          </div>
        {:else}
          <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div>
              <h3 class="text-3xl font-serif mb-4">St. Petersburg Studio</h3>
              <p class="text-gray-600 mb-6">Bringing the rhythm to the Northern Capital. Experience our world-class facilities in a central location.</p>
              <ul class="space-y-4 mb-8">
                <li class="flex items-center gap-3">
                  <svg class="w-5 h-5 text-primary-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                  <span>Central St. Petersburg Location</span>
                </li>
              </ul>
              <button class="bg-primary-500 text-white px-8 py-4 rounded-full font-bold hover:bg-primary-600 transition-colors">Book a Bike in SPB</button>
            </div>
            <div class="h-64 bg-gray-200 rounded-2xl flex items-center justify-center text-gray-400 italic">
              Interactive Map Placeholder
            </div>
          </div>
        {/if}
      </div>
    </div>
  </section>

  <!-- FAQ Section -->
  <section class="py-24 bg-gray-50 text-[#130b29]">
    <div class="max-w-4xl mx-auto px-6">
      <h2 class="text-4xl font-serif mb-16 text-center">Common Questions</h2>
      <div class="space-y-4">
        {#each [
          { q: "Do I need prior cycling experience?", a: "Not at all! Our classes are designed for all fitness levels. Our instructors will guide you through the setup and the ride." },
          { q: "What should I bring?", a: "Just your workout clothes. We provide cycling shoes, towels, and all shower amenities." },
          { q: "How long is each session?", a: "Our standard sessions are 45 minutes of high-intensity cardio." },
          { q: "Can I cancel a booking?", a: "Yes, you can cancel up to 12 hours before the class starts without losing your credit." }
        ] as faq}
          <details class="group bg-white rounded-2xl border border-gray-100 overflow-hidden">
            <summary class="flex justify-between items-center p-6 cursor-pointer font-bold text-lg list-none">
              {faq.q}
              <span class="w-8 h-8 rounded-full bg-gray-100 flex items-center justify-center group-open:rotate-45 transition-transform">+</span>
            </summary>
            <div class="px-6 pb-6 text-gray-500 leading-relaxed">
              {faq.a}
            </div>
          </details>
        {/each}
      </div>
    </div>
  </section>

  <Footer />
</div>

<style>
  .mask-image-gradient {
      mask-image: linear-gradient(to bottom, black 80%, transparent 100%);
      -webkit-mask-image: linear-gradient(to bottom, black 80%, transparent 100%);
  }
  /* Animation keyframes */
  @keyframes fadeInUp {
      from {
          opacity: 0;
          transform: translateY(20px);
          filter: blur(4px);
      }
      to {
          opacity: 1;
          transform: translateY(0);
          filter: blur(0);
      }
  }

  @keyframes scaleIn {
      from {
          opacity: 0;
          transform: scale(0.95);
      }
      to {
          opacity: 1;
          transform: scale(1);
      }
  }

  @keyframes float {
      0%, 100% { transform: translateY(0px) rotate(var(--rotation)); }
      50% { transform: translateY(-10px) rotate(var(--rotation)); }
  }

  .animate-fade-in-up {
      opacity: 0;
      animation: fadeInUp 0.8s cubic-bezier(0.22, 0.61, 0.36, 1) forwards;
  }

  .animate-scale-in {
      opacity: 0;
      animation: scaleIn 0.8s cubic-bezier(0.22, 0.61, 0.36, 1) forwards;
  }

  .animate-float {
      animation: float 6s ease-in-out infinite;
  }

  .delay-100 { animation-delay: 100ms; }
  .delay-200 { animation-delay: 200ms; }
  .delay-300 { animation-delay: 300ms; }
  .delay-400 { animation-delay: 400ms; }

  .bg-stars {
      background-color: #1a0b2e;
      background-image: 
          radial-gradient(white, rgba(255,255,255,.2) 2px, transparent 3px),
          radial-gradient(white, rgba(255,255,255,.15) 1px, transparent 2px),
          radial-gradient(white, rgba(255,255,255,.1) 2px, transparent 3px);
      background-size: 550px 550px, 350px 350px, 250px 250px;
      background-position: 0 0, 40px 60px, 130px 270px;
  }

  .bg-gradient-overlay {
      background: radial-gradient(circle at 50% 0%, #2d1b4e 0%, #130b29 60%, #130b29 100%);
  }

  .glow-border {
      box-shadow: 0 0 40px -5px rgba(110, 231, 183, 0.3);
  }

  summary::-webkit-details-marker {
    display: none;
  }
</style>

