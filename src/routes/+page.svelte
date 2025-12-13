<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
	const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
	const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
	const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
	const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>`;
	const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
	const Linkedin = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
	const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 18"/></svg>`;

	let faqs = [
		{ question: "What does a Holo membership include?", open: false },
		{ question: "Is Holo for you?", open: false },
		{ question: "What more does Holo offer than my regular doctor or insurance?", open: false },
		{ question: "I recently got tested. Should I wait to join Holo?", open: false },
		{ question: "Which biomarkers are included in the Holo membership?", open: false }
	];

	function toggleFaq(index: number) {
		faqs = faqs.map((faq, i) => {
			if (i === index) return { ...faq, open: !faq.open };
			return faq;
		});
	}
</script>

<div class="min-h-screen flex flex-col font-sans text-gray-900 bg-[#FAFAFA]">
	<!-- Top Banner -->
	<div class="bg-black text-white text-[11px] font-medium py-3 text-center tracking-wide px-4">
		15% off for yourself or for someone you care about with the code GIFT15 until December 31.
	</div>

	<!-- Navigation -->
	<nav class="flex items-center justify-between px-6 md:px-12 py-5 bg-[#FAFAFA]">
		<div class="flex items-center gap-2">
			<!-- Logo -->
			<div class="flex items-center gap-2">
				<div class="grid grid-cols-2 gap-[2px]">
					<div class="w-1 h-1 bg-black rounded-full"></div>
					<div class="w-1 h-1 bg-black rounded-full"></div>
					<div class="w-1 h-1 bg-black rounded-full"></div>
					<div class="w-1 h-1 bg-black rounded-full"></div>
				</div>
				<span class="text-xl font-bold tracking-tight">HOLO</span>
			</div>
		</div>
		<div class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
			<a href="#" class="hover:text-black transition-colors">Biomarkers</a>
			<a href="#" class="hover:text-black transition-colors">FAQ</a>
			<a href="#" class="hover:text-black transition-colors">Blog</a>
			<a href="#" class="hover:text-black transition-colors">Gift Holo</a>
			<a href="#" class="bg-black text-white px-5 py-2 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors">Join now</a>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="flex flex-col items-center pt-16 pb-20 px-4 text-center">
		<h1 class="text-4xl md:text-[56px] leading-[1.1] font-medium tracking-tight max-w-3xl mb-6">
			Your companion<br>for lifelong vitality.
		</h1>
		<p class="text-gray-500 text-[15px] max-w-xl mb-8 leading-relaxed">
			Test 60+ biomarkers every year, track all your health in a single place, and get insights from top doctors. All starting at just €199.
		</p>
		<button class="bg-black text-white px-6 py-3 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors mb-20">
			Start testing
		</button>

		<!-- Horizontal Scroll Images -->
		<div class="w-full max-w-[1400px] overflow-hidden relative mt-12">
			<div class="flex gap-6 justify-center items-center h-[320px]">
				<!-- Image 1 -->
				<div class="w-[200px] h-[260px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-2deg] translate-y-4">
					<img src="https://images.unsplash.com/photo-1522163182402-834f871fd851?w=400&h=600&fit=crop" alt="Climbing" class="w-full h-full object-cover" />
				</div>
				<!-- Image 2 -->
				<div class="w-[260px] h-[180px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[1deg] -translate-y-2">
					<img src="https://images.unsplash.com/photo-1502086223501-681a5812147d?w=400&h=300&fit=crop" alt="Bench" class="w-full h-full object-cover" />
				</div>
				<!-- Image 3 -->
				<div class="w-[220px] h-[220px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-1deg] translate-y-2">
					<img src="https://images.unsplash.com/photo-1551632811-561732d1e306?w=400&h=400&fit=crop" alt="Hiking" class="w-full h-full object-cover" />
				</div>
				<!-- Image 4 -->
				<div class="w-[200px] h-[200px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[2deg] -translate-y-4">
					<img src="https://images.unsplash.com/photo-1476480862126-209bfaa8edc8?w=400&h=400&fit=crop" alt="Running" class="w-full h-full object-cover" />
				</div>
				<!-- Image 5 -->
				<div class="w-[180px] h-[260px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-2deg] translate-y-6">
					<img src="https://images.unsplash.com/photo-1551524164-687a55dd1126?w=400&h=600&fit=crop" alt="Snow" class="w-full h-full object-cover" />
				</div>
				<!-- Image 6 -->
				<div class="w-[200px] h-[160px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[1deg] -translate-y-2">
					<img src="https://images.unsplash.com/photo-1596328616956-619f70d748d6?w=400&h=300&fit=crop" alt="Park" class="w-full h-full object-cover" />
				</div>
			</div>
		</div>
	</section>

	<!-- App Showcase -->
	<section class="py-24 px-6 md:px-12 flex justify-center">
		<div class="bg-white rounded-[32px] p-12 md:p-20 flex flex-col md:flex-row items-center gap-16 max-w-[1200px] w-full shadow-sm">
			<!-- Phone Mockup -->
			<div class="relative w-[280px] h-[580px] bg-black rounded-[40px] p-3 shadow-2xl flex-shrink-0 border-4 border-gray-100">
				<div class="w-full h-full bg-white rounded-[32px] overflow-hidden relative">
					<!-- Fake App UI -->
					<div class="p-6 pt-10">
						<div class="flex justify-between items-center mb-6">
							<div class="text-xs font-bold">Good morning, Sarah</div>
							<div class="w-6 h-6 bg-gray-200 rounded-full"></div>
						</div>
						<div class="flex justify-between gap-2 mb-8">
							<div class="w-16 h-16 rounded-full border-4 border-red-400 flex items-center justify-center text-xs font-bold">25</div>
							<div class="w-16 h-16 rounded-full border-4 border-green-400 flex items-center justify-center text-xs font-bold">53</div>
							<div class="w-16 h-16 rounded-full border-4 border-blue-400 flex items-center justify-center text-xs font-bold">66</div>
						</div>
						<div class="bg-gray-50 p-4 rounded-xl mb-4">
							<div class="text-[10px] text-gray-500 uppercase mb-1">Biological Age</div>
							<div class="text-2xl font-bold">30 <span class="text-sm font-normal text-gray-500">years</span></div>
						</div>
						<div class="space-y-3">
							<div class="h-2 bg-gray-100 rounded full w-3/4"></div>
							<div class="h-2 bg-gray-100 rounded full w-1/2"></div>
							<div class="h-2 bg-gray-100 rounded full w-5/6"></div>
						</div>
					</div>
					<!-- Bottom Nav -->
					<div class="absolute bottom-0 left-0 w-full h-16 bg-white border-t border-gray-100 flex justify-around items-center px-4">
						<div class="w-6 h-6 bg-black rounded-full"></div>
						<div class="w-6 h-6 bg-gray-200 rounded-full"></div>
						<div class="w-6 h-6 bg-gray-200 rounded-full"></div>
						<div class="w-6 h-6 bg-gray-200 rounded-full"></div>
					</div>
				</div>
			</div>

			<!-- Content -->
			<div class="flex-1 max-w-lg">
				<h2 class="text-3xl font-medium mb-6 leading-tight">
					Your health at a glance.<br>
					See your daily Strain, Recovery and Sleep goals.
					Explore your biomarkers, understand what
					they mean, and access your Clinician Notes,
					including your Action Plan created after your test.
				</h2>
				<div class="flex items-center justify-between mt-12">
					<a href="#" class="flex items-center gap-2 text-blue-600 text-sm font-medium hover:underline">
						{@html PlayCircle}
						Watch video
					</a>
					<div class="flex gap-4">
						<button class="w-8 h-8 flex items-center justify-center rounded-full border border-gray-200 hover:bg-gray-50 transition-colors">
							{@html ChevronLeft}
						</button>
						<button class="w-8 h-8 flex items-center justify-center rounded-full border border-gray-200 hover:bg-gray-50 transition-colors">
							{@html ChevronRight}
						</button>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Lifestyle Grid -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="flex flex-col md:flex-row justify-between items-start mb-16 gap-10">
			<h2 class="text-4xl md:text-5xl font-medium tracking-tight max-w-md leading-[1.1]">
				You deserve to live fully, longer, and better.
			</h2>
			<p class="text-gray-500 text-[15px] max-w-md leading-relaxed">
				Your health is more than numbers, it's your story, your future. Taking care of it today means giving yourself the chance to enjoy more years with strength, clarity, and vitality. We're here to help you protect what truly matters: a healthier, longer life.
			</p>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
			<!-- Card 1 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?w=600&h=800&fit=crop" alt="Woman smiling" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">All your data. One place.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Holo takes into account your lifestyle and habits, your past results, and connects your wearables data.</p>
				</div>
			</div>
			<!-- Card 2 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?w=600&h=800&fit=crop" alt="Man running" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Better control over your performance.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Start thriving by tracking your daily strain, recovery and sleep.</p>
				</div>
			</div>
			<!-- Card 3 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="https://images.unsplash.com/photo-1529113247322-132d7844a497?w=600&h=800&fit=crop" alt="Family" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Proactive care.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Health is not only the absence of illness but having strength and vitality everyday.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Testimonial -->
	<section class="py-24 px-6 text-center bg-[#F5F5F3]">
		<div class="max-w-3xl mx-auto">
			<blockquote class="text-2xl md:text-3xl font-medium leading-tight mb-10">
				"I've always wanted a tool like Holo. It gives people real power over their health in a way that's simple and intuitive. I love how deeply personalized it is, making it easier than ever to understand your body and make smart choices"
			</blockquote>
			<div class="flex flex-col items-center gap-3">
				<img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=100&h=100&fit=crop" alt="Doctor" class="w-12 h-12 rounded-full object-cover" />
				<div class="text-sm">
					<div class="font-bold">Dra. Cocco Meradi</div>
					<div class="text-gray-500">Functional Doctor</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Process Steps -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full border-b border-gray-200">
		<div class="grid grid-cols-1 md:grid-cols-3 gap-12">
			<div>
				<h3 class="text-xl font-medium mb-2">15 minutes lab visit.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">In and out. Take your blood and urine test. One minute with the nurse. Quick and simple.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">24 hours first results.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Your lab test data, fast. Complete results in five business days.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Clinician Notes in 1 week.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">From data to a clear Action Plan to guide you along your health path.</p>
			</div>
		</div>
	</section>

	<!-- How it works -->
	<section class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="flex flex-col lg:flex-row gap-20">
			<!-- Sticky Title -->
			<div class="lg:w-1/3 lg:sticky lg:top-24 h-fit">
				<h2 class="text-4xl font-medium mb-6">How it works.</h2>
				<p class="text-gray-500 text-[15px] leading-relaxed max-w-xs">
					With two lab tests a year, daily tracking from your phone and wearables, and guidance from real doctors, Holo helps you understand what's going on inside so you can make smarter, healthier choices.
				</p>
			</div>

			<!-- Steps List -->
			<div class="lg:w-2/3 flex flex-col gap-8">
				<!-- Step 1 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">1</div>
						<h3 class="text-2xl font-medium mb-3">Chose the plan that fits you better.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Two options available. Set the Core plan with 60+ biomarkers to access the most advance lab test or choose the Starter plan to test 40+ essential biomarkers.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
						<div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col">
                            <!-- Mock UI -->
                            <div class="bg-gray-50 p-4 border-b">
                                <div class="h-4 w-20 bg-gray-200 rounded mb-2"></div>
                            </div>
                            <div class="p-4 space-y-3">
                                <div class="h-12 bg-green-50 rounded-lg border border-green-100 p-2">
                                    <div class="h-2 w-12 bg-green-200 rounded mb-1"></div>
                                    <div class="h-4 w-24 bg-green-300 rounded"></div>
                                </div>
                                <div class="h-12 bg-white rounded-lg border border-gray-100 p-2">
                                    <div class="h-2 w-12 bg-gray-200 rounded mb-1"></div>
                                    <div class="h-4 w-24 bg-gray-300 rounded"></div>
                                </div>
                                <div class="h-12 bg-white rounded-lg border border-gray-100 p-2">
                                    <div class="h-2 w-12 bg-gray-200 rounded mb-1"></div>
                                    <div class="h-4 w-24 bg-gray-300 rounded"></div>
                                </div>
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 2 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">2</div>
						<h3 class="text-2xl font-medium mb-3">Schedule your appointment.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Choose the most convenient lab location for you and follow the instructions before the test.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col items-center pt-8">
                            <div class="text-sm font-bold mb-4">Appointment</div>
                            <div class="w-16 h-16 bg-gray-100 rounded-full mb-4"></div>
                            <div class="text-xs text-gray-500 px-8 text-center">Schedule your visit at a nearby lab.</div>
                            <div class="mt-auto w-full p-4">
                                <div class="w-full h-10 bg-black rounded-lg"></div>
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 3 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">3</div>
						<h3 class="text-2xl font-medium mb-3">Receive first results.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Within 24 hours directly on your app. When all your results are available, our medical team will start working on your Clinician Notes.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-gray-900 rounded-[28px] overflow-hidden relative text-white p-6 pt-10">
                             <div class="flex items-center gap-3 mb-6">
                                 <div class="w-10 h-10 rounded-full bg-gray-700"></div>
                                 <div>
                                     <div class="text-sm font-bold">Grace Parker</div>
                                     <div class="text-[10px] text-gray-400">Bio Age: 28</div>
                                 </div>
                             </div>
                             <div class="space-y-2">
                                 <div class="h-20 bg-gray-800 rounded-xl"></div>
                                 <div class="h-20 bg-gray-800 rounded-xl"></div>
                             </div>
                        </div>
					</div>
				</div>

				<!-- Step 4 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">4</div>
						<h3 class="text-2xl font-medium mb-3">Your Clinician Notes are ready.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Receive your Clinician Notes and personalized Action Plan within 7 days from your results.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col pt-8 px-4">
                            <div class="text-center text-sm font-bold mb-4">Clinician Notes</div>
                            <div class="text-[10px] text-gray-500 leading-relaxed text-justify">
                                You already make smart choices for your health through regular exercise, reduced unhealthy fats and sugars, and limiting sleep disruptors.
                                <br><br>
                                Since your diet lacks enough fruits and vegetables, adding more could strengthen long-term health...
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 5 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">5</div>
						<h3 class="text-2xl font-medium mb-3">Start improving.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Continue your health journey together with Holo AI and your Action Plan. Recheck in 6 months with the follow-up test.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col pt-8 px-4">
                             <div class="bg-gray-100 p-3 rounded-lg text-[10px] mb-2">
                                 What benefit do I get by keeping ApoB down in the optimal range?
                             </div>
                             <div class="text-[10px] text-gray-500 leading-relaxed mt-2">
                                 By lowering ApoB, you've reduced the number of cholesterol-carrying particles in your bloodstream...
                             </div>
                        </div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Dark Cards Section -->
	<section class="py-10 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
			<!-- Left Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">A five star experience.</div>
					<h3 class="text-2xl font-medium max-w-xs">We partner exclusively with renowned labs.</h3>
				</div>
				<!-- Map Graphic Placeholder -->
				<div class="absolute bottom-0 right-0 w-full h-64 opacity-20">
                    <!-- Simple dot map simulation with SVG -->
                    <svg viewBox="0 0 200 100" class="w-full h-full">
                        {#each Array(100) as _, i}
                            <circle cx={Math.random() * 200} cy={Math.random() * 100} r="1" fill="white" />
                        {/each}
                    </svg>
				</div>
			</div>
			<!-- Right Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">Your data is safe with us.</div>
					<h3 class="text-2xl font-medium max-w-xs">We're built to protect your privacy by default.</h3>
				</div>
				<!-- Blurred Text Graphic -->
				<div class="absolute bottom-8 right-8 text-right font-mono text-3xl opacity-30 blur-[2px] select-none pointer-events-none">
					<div>Elizab|%b$9yT</div>
					<div>Willi|I7m/@</div>
					<div>Magn|&5a!</div>
					<div>Trigly|?Pm_Lw</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Pricing Section -->
	<section class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full text-center">
		<h2 class="text-3xl md:text-4xl font-medium mb-4">Preventive healthcare for everyone.</h2>
		<p class="text-gray-500 text-sm max-w-lg mx-auto mb-16">
			Top-tier testing, real-time tracking, and dedicated clinician guidance—made affordable. Because investing in prevention is the most important investing of your life.
		</p>

		<div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto">
			<!-- Starter Plan -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm">
				<div class="w-10 h-10 bg-gray-100 rounded-lg mb-6"></div>
				<h3 class="text-xl font-bold mb-1">Starter</h3>
				<p class="text-xs text-gray-500 mb-6">Begin your health journey.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">€199</span>
					<span class="text-xs text-gray-500">/yr</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">Pay in installments with Klarna. <span class="bg-pink-100 text-pink-600 px-1 rounded">Klarna.</span></div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Two tests a year covering 40+ essential biomarkers.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Measure your Biological Age and Aging Rate with every test.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Clinician Notes and personalized Action Plan to guide your health.
					</li>
				</ul>

				<button class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors">Join now</button>
			</div>

			<!-- Core Plan -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm border-2 border-orange-100 relative overflow-hidden">
                <div class="absolute top-0 right-0 bg-orange-100 text-orange-600 text-[10px] font-bold px-3 py-1 rounded-bl-xl">POPULAR</div>
				<div class="w-10 h-10 bg-orange-50 rounded-lg mb-6"></div>
				<h3 class="text-xl font-bold mb-1">Core</h3>
				<p class="text-xs text-gray-500 mb-6">The most advanced longevity membership.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">€399</span>
					<span class="text-xs text-gray-500">/yr</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">Pay in installments with Klarna. <span class="bg-pink-100 text-pink-600 px-1 rounded">Klarna.</span></div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Full Core Test of 60+ Biomarkers plus a follow-up with 40+ biomarkers to track change.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						First test includes an extended hormonal and Vitamin panel for deeper insights.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Clinician Notes and a personalized Action Plan built on your most complete lab testing profile.
					</li>
				</ul>

				<button class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors">Join now</button>
			</div>
		</div>
	</section>

	<!-- FAQ Section -->
	<section class="py-20 px-6 md:px-12 max-w-3xl mx-auto w-full">
		<h2 class="text-3xl font-medium text-center mb-16">Your questions answered.</h2>
		<div class="space-y-4">
			{#each faqs as faq, i}
				<button 
					class="w-full flex items-center justify-between p-4 text-left hover:bg-gray-100 rounded-lg transition-colors group"
					onclick={() => toggleFaq(i)}
				>
					<span class="text-sm font-medium text-gray-800">{faq.question}</span>
					<span class="text-gray-400 transition-transform duration-200 {faq.open ? 'rotate-45' : ''}">{@html Plus}</span>
				</button>
                {#if faq.open}
                    <div class="px-4 pb-4 text-xs text-gray-500">
                        Placeholder answer for "{faq.question}". This would contain detailed information about the service.
                    </div>
                {/if}
			{/each}
		</div>
		<div class="text-center mt-12">
			<button class="bg-white border border-gray-200 px-6 py-3 rounded text-xs font-medium hover:bg-gray-50 transition-colors">
				View all Frequently Asked Questions
			</button>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-[#F5F5F3] py-16 px-6 md:px-12 text-[11px] text-gray-500">
		<div class="max-w-[1400px] mx-auto">
			<div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-12 gap-8">
				<div class="flex items-center gap-2">
					<div class="grid grid-cols-2 gap-[2px]">
						<div class="w-1 h-1 bg-black rounded-full"></div>
						<div class="w-1 h-1 bg-black rounded-full"></div>
						<div class="w-1 h-1 bg-black rounded-full"></div>
						<div class="w-1 h-1 bg-black rounded-full"></div>
					</div>
					<span class="text-lg font-bold tracking-tight text-black">HOLO</span>
				</div>
				<div class="flex flex-wrap gap-6 font-medium text-gray-600">
					<a href="#" class="hover:text-black">Biomarkers</a>
					<a href="#" class="hover:text-black">FAQ</a>
					<a href="#" class="hover:text-black">Blog</a>
					<a href="#" class="hover:text-black">Terms & Conditions</a>
					<a href="#" class="hover:text-black">Privacy Policy</a>
				</div>
				<div class="flex gap-4">
					<a href="#" class="text-black hover:text-gray-600">{@html XIcon}</a>
					<a href="#" class="text-black hover:text-gray-600">{@html Instagram}</a>
					<a href="#" class="text-black hover:text-gray-600">{@html Linkedin}</a>
				</div>
			</div>
			
			<div class="space-y-4 leading-relaxed opacity-60">
				<p>Holo is a technology company, not a laboratory or medical provider. All lab and medical services are provided by independent third parties, who set their own pricing, terms and conditions. Access to certain providers, if does not recommend or refer healthcare providers. Holo does not offer medical advice, lab services, diagnosis, treatment, or medical opinions. Its services do not replace medical care or consultations with a licensed provider. If you have questions about lab results, consult a primary care physician or other licensed provider. All information provided by Holo is for general informational purposes only.</p>
				<p>Holo's membership pricing includes prepaid access to certain third-party lab services. Some items and services require additional payments beyond standard membership pricing. For more details, see our Terms & Conditions.</p>
				<p>By providing your phone number, you agree to receive text messages from Holo. Message and data rates may apply. Message frequency varies.</p>
			</div>
		</div>
	</footer>
</div>

<style>
    /* Hide scrollbar for horizontal scroll */
    .overflow-hidden::-webkit-scrollbar {
        display: none;
    }
</style>

