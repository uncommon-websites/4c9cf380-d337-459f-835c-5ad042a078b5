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
		{ question: "How is CORTEX LIFE different from fitness wearables?", open: false },
		{ question: "What can breath gas analysis tell me that wearables can't?", open: false },
		{ question: "Is CORTEX LIFE covered by insurance?", open: false },
		{ question: "Do I need to go to a clinic for testing?", open: false },
		{ question: "How does the AI interpretation work?", open: false }
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
		Clinically accurate metabolic insights. Now available through insurance reimbursement.
	</div>

	<!-- Navigation -->
	<nav class="flex items-center justify-between px-6 md:px-12 py-5 bg-[#FAFAFA]">
		<div class="flex items-center gap-2">
			<!-- Logo -->
			<div class="flex items-center gap-3">
				<div class="w-7 h-7 text-black">
					<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
						<mask
							id="mask0_161_7365"
							style="mask-type:luminance"
							maskUnits="userSpaceOnUse"
							x="3"
							y="1"
							width="18"
							height="22"
						>
							<path d="M3 1H20.7794V22.3353H3V1Z" fill="white" />
						</mask>
						<g mask="url(#mask0_161_7365)">
							<path
								d="M14.1516 3.24638L12.4034 2.77795L10.9302 8.27606L9.60014 3.31233L7.85194 3.78076L9.28896 9.14369L5.70969 5.56443L4.42993 6.84419L8.35594 10.7702L3.46671 9.46017L2.99829 11.2083L8.34038 12.6397C8.27922 12.3759 8.24687 12.1011 8.24687 11.8187C8.24687 9.81953 9.86746 8.19894 11.8666 8.19894C13.8657 8.19894 15.4863 9.81953 15.4863 11.8187C15.4863 12.0993 15.4544 12.3724 15.394 12.6347L20.2489 13.9356L20.7173 12.1874L15.354 10.7503L20.2436 9.44012L19.7751 7.69196L14.412 9.12898L17.9913 5.54972L16.7115 4.26998L12.84 8.14156L14.1516 3.24638Z"
								fill="currentColor"
							/>
							<path
								d="M15.3888 12.655C15.2389 13.2887 14.9225 13.8579 14.4883 14.314L18.0056 17.8313L19.2853 16.5515L15.3888 12.655Z"
								fill="currentColor"
							/>
							<path
								d="M14.4529 14.3508C14.0135 14.7996 13.4582 15.1345 12.8354 15.3071L14.1153 20.0836L15.8635 19.6151L14.4529 14.3508Z"
								fill="currentColor"
							/>
							<path
								d="M12.7701 15.3246C12.4812 15.3989 12.1784 15.4384 11.8663 15.4384C11.5319 15.4384 11.2082 15.393 10.9008 15.3082L9.61981 20.089L11.368 20.5574L12.7701 15.3246Z"
								fill="currentColor"
							/>
							<path
								d="M10.839 15.2905C10.2258 15.1093 9.68038 14.7702 9.24994 14.3201L5.72406 17.8459L7.00382 19.1257L10.839 15.2905Z"
								fill="currentColor"
							/>
							<path
								d="M9.22084 14.2889C8.79778 13.836 8.48962 13.2743 8.34294 12.6505L3.47211 13.9556L3.94053 15.7038L9.22084 14.2889Z"
								fill="currentColor"
							/>
						</g>
					</svg>
				</div>
				<span class="text-xl font-bold tracking-tight">CORTEX LIFE</span>
			</div>
		</div>
		<div class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
			<a href="#" class="hover:text-black transition-colors">Technology</a>
			<a href="#" class="hover:text-black transition-colors">For Athletes</a>
			<a href="#" class="hover:text-black transition-colors">For Clinics</a>
			<a href="#" class="hover:text-black transition-colors">FAQ</a>
			<a href="#" class="bg-black text-white px-5 py-2 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors">Get Started</a>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="flex flex-col items-center pt-16 pb-20 px-4 text-center">
		<h1 class="text-4xl md:text-[56px] leading-[1.1] font-medium tracking-tight max-w-3xl mb-6">
			Clinical-grade metabolic insights.<br>Mobile. AI-powered. Precise.
		</h1>
		<p class="text-gray-500 text-[15px] max-w-xl mb-8 leading-relaxed">
			True breath-by-breath gas exchange measurement (O₂/CO₂) that delivers training zones, recovery signals, and metabolic flexibility insights—not rough estimates.
		</p>
		<button class="bg-black text-white px-6 py-3 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors mb-20">
			Start Your Analysis
		</button>

		<!-- Horizontal Scroll Images -->
		<div class="w-full max-w-[1400px] overflow-hidden relative mt-12">
			<div class="flex gap-6 justify-center items-center h-[320px]">
				<!-- Image 1 -->
				<div class="w-[200px] h-[260px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-2deg] translate-y-4">
					<img src="/generated/image-athletic-person-using-a-portable-breath--1767713568945-0.webp" alt="Athlete using breath analysis" class="w-full h-full object-cover" />
				</div>
				<!-- Image 2 -->
				<div class="w-[260px] h-[180px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[1deg] -translate-y-2">
					<img src="/generated/image-person-using-portable-breath-device-whil-1767713592199-8.webp" alt="Checking training zones" class="w-full h-full object-cover" />
				</div>
				<!-- Image 3 -->
				<div class="w-[220px] h-[220px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-1deg] translate-y-2">
					<img src="/generated/image-cyclist-using-breath-measurement-device--1767713575283-2.webp" alt="Cyclist metabolic testing" class="w-full h-full object-cover" />
				</div>
				<!-- Image 4 -->
				<div class="w-[200px] h-[200px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[2deg] -translate-y-4">
					<img src="/generated/image-runner-checking-metabolic-data-on-mobile-1767713572197-1.webp" alt="Runner with mobile app" class="w-full h-full object-cover" />
				</div>
				<!-- Image 5 -->
				<div class="w-[180px] h-[260px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[-2deg] translate-y-6">
					<img src="/generated/image-professional-athlete-in-recovery-using-b-1767713580939-4.webp" alt="Recovery monitoring" class="w-full h-full object-cover" />
				</div>
				<!-- Image 6 -->
				<div class="w-[200px] h-[160px] rounded-[24px] overflow-hidden flex-shrink-0 relative group shadow-lg rotate-[1deg] -translate-y-2">
					<img src="/generated/image-health-conscious-person-analyzing-metabo-1767713578179-3.webp" alt="Health insights" class="w-full h-full object-cover" />
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
					Your metabolic profile at a glance.<br>
					Real-time VO₂ and VCO₂ measurements translated by AI into training zones, recovery status, and metabolic flexibility scores. Track your progress and optimize performance with clinical precision.
				</h2>
				<div class="flex items-center justify-between mt-12">
					<a href="#" class="flex items-center gap-2 text-primary-600 text-sm font-medium hover:underline">
						{@html PlayCircle}
						Watch demo
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
				Beyond wearables. Beyond estimates.
			</h2>
			<p class="text-gray-500 text-[15px] max-w-md leading-relaxed">
				CORTEX LIFE bridges the gap between inaccurate consumer wearables and expensive clinic-bound diagnostics. Get clinical-grade metabolic insights anywhere, enhanced by AI that translates complex data into actionable guidance for performance, recovery, and longevity.
			</p>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
			<!-- Card 1 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-fitness-trainer-demonstrating-breath-gas-1767713583774-5.webp" alt="Clinical validation" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Clinical lineage.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Technology derived from validated spiroergometry, not consumer sensors. Trusted by medical professionals.</p>
				</div>
			</div>
			<!-- Card 2 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-elite-endurance-athlete-during-metabolic-1767713589502-7.webp" alt="Athlete performance" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Precision performance.</h3>
					<p class="text-sm text-white/80 leading-relaxed">True breath-by-breath O₂/CO₂ measurement delivers accurate training zones and recovery signals.</p>
				</div>
			</div>
			<!-- Card 3 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-health-conscious-person-analyzing-metabo-1767713578179-3.webp" alt="Longevity insights" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Metabolic longevity.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Track metabolic flexibility and longevity indicators with longitudinal breath-data insights.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Testimonial -->
	<section class="py-24 px-6 text-center bg-[#F5F5F3]">
		<div class="max-w-3xl mx-auto">
			<blockquote class="text-2xl md:text-3xl font-medium leading-tight mb-10">
				"CORTEX LIFE delivers the clinical accuracy we need in metabolic diagnostics, but with the accessibility athletes demand. The AI interpretation layer transforms complex gas exchange data into actionable insights that actually improve training outcomes."
			</blockquote>
			<div class="flex flex-col items-center gap-3">
				<img src="/generated/image-confident-sports-medicine-doctor-with-br-1767713586632-6.webp" alt="Sports Medicine Doctor" class="w-12 h-12 rounded-full object-cover" />
				<div class="text-sm">
					<div class="font-bold">Dr. Sarah Mitchell</div>
					<div class="text-gray-500">Sports Medicine Physician</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Process Steps -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full border-b border-gray-200">
		<div class="grid grid-cols-1 md:grid-cols-3 gap-12">
			<div>
				<h3 class="text-xl font-medium mb-2">Breath-by-breath accuracy.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">True gas exchange measurement (O₂/CO₂), not inferred estimates. Clinical precision in a mobile device.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Instant AI interpretation.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Complex metabolic data translated into training zones, recovery signals, and actionable insights.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Insurance reimbursement.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Start with clinically validated diagnostics covered by insurance, expand into performance optimization.</p>
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
					From initial clinical assessment through ongoing performance optimization, CORTEX LIFE delivers precise metabolic insights enhanced by AI interpretation—accessible anywhere, anytime.
				</p>
			</div>

			<!-- Steps List -->
			<div class="lg:w-2/3 flex flex-col gap-8">
				<!-- Step 1 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">1</div>
						<h3 class="text-2xl font-medium mb-3">Choose your pathway.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Start with insurance-reimbursed clinical diagnostics, or jump directly to athlete performance optimization. Both paths deliver the same clinical-grade accuracy.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
						<div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col">
                            <!-- Mock UI -->
                            <div class="bg-gray-50 p-4 border-b">
                                <div class="h-4 w-32 bg-gray-200 rounded mb-2"></div>
                            </div>
                            <div class="p-4 space-y-3">
                                <div class="h-12 bg-primary-50 rounded-lg border border-primary-100 p-2">
                                    <div class="h-2 w-16 bg-primary-200 rounded mb-1"></div>
                                    <div class="h-4 w-28 bg-primary-300 rounded"></div>
                                </div>
                                <div class="h-12 bg-white rounded-lg border border-gray-100 p-2">
                                    <div class="h-2 w-16 bg-gray-200 rounded mb-1"></div>
                                    <div class="h-4 w-28 bg-gray-300 rounded"></div>
                                </div>
                                <div class="h-12 bg-white rounded-lg border border-gray-100 p-2">
                                    <div class="h-2 w-16 bg-gray-200 rounded mb-1"></div>
                                    <div class="h-4 w-28 bg-gray-300 rounded"></div>
                                </div>
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 2 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">2</div>
						<h3 class="text-2xl font-medium mb-3">Receive your device.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Get your CORTEX LIFE mobile breath analyzer. Pair it with the app and complete the simple calibration process.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col items-center pt-8">
                            <div class="text-sm font-bold mb-4">Setup</div>
                            <div class="w-16 h-16 bg-primary-100 rounded-full mb-4 flex items-center justify-center">
								<div class="w-8 h-8 text-primary-600">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
										<circle cx="12" cy="12" r="10"/>
										<path d="M8 12h8"/>
										<path d="M12 8v8"/>
									</svg>
								</div>
							</div>
                            <div class="text-xs text-gray-500 px-8 text-center">Connect your device and start your first breath test.</div>
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
						<h3 class="text-2xl font-medium mb-3">Perform breath analysis.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Take breath measurements during rest, training, or recovery. Real-time O₂ and CO₂ data captured with clinical precision.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-gray-900 rounded-[28px] overflow-hidden relative text-white p-6 pt-10">
                             <div class="flex items-center gap-3 mb-6">
                                 <div class="w-10 h-10 rounded-full bg-primary-900"></div>
                                 <div>
                                     <div class="text-sm font-bold">Live Analysis</div>
                                     <div class="text-[10px] text-gray-400">VO₂: 42.3 ml/kg/min</div>
                                 </div>
                             </div>
                             <div class="space-y-2">
                                 <div class="h-20 bg-gray-800 rounded-xl p-3">
									<div class="text-[10px] text-gray-400 mb-1">O₂ Uptake</div>
									<div class="h-2 bg-primary-600 rounded w-3/4"></div>
								 </div>
                                 <div class="h-20 bg-gray-800 rounded-xl p-3">
									<div class="text-[10px] text-gray-400 mb-1">CO₂ Output</div>
									<div class="h-2 bg-primary-500 rounded w-2/3"></div>
								 </div>
                             </div>
                        </div>
					</div>
				</div>

				<!-- Step 4 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">4</div>
						<h3 class="text-2xl font-medium mb-3">Get AI-powered insights.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Complex gas exchange data instantly translated into training zones, recovery status, and metabolic flexibility scores.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col pt-8 px-4">
                            <div class="text-center text-sm font-bold mb-4">AI Insights</div>
                            <div class="text-[10px] text-gray-500 leading-relaxed text-justify">
                                Your metabolic data shows excellent fat oxidation capacity at lower intensities, indicating strong metabolic flexibility.
                                <br><br>
                                Recommended training zones:<br>
                                Zone 2: 125-145 bpm<br>
                                Threshold: 165-175 bpm<br><br>
                                Current recovery status: Optimal for high-intensity work.
                            </div>
                        </div>
					</div>
				</div>

				<!-- Step 5 -->
				<div class="bg-white rounded-[32px] p-10 md:p-16 flex flex-col items-center text-center shadow-sm">
					<div class="w-full max-w-md mb-10 text-left self-start">
						<div class="w-8 h-8 rounded border border-gray-200 flex items-center justify-center text-xs font-medium mb-6">5</div>
						<h3 class="text-2xl font-medium mb-3">Track and optimize.</h3>
						<p class="text-sm text-gray-500 leading-relaxed">Build longitudinal breath-data insights. Monitor metabolic changes over time and optimize training, recovery, and longevity strategies.</p>
					</div>
					<div class="w-[240px] h-[480px] bg-black rounded-[36px] p-2 shadow-xl border-4 border-gray-100">
                        <div class="w-full h-full bg-white rounded-[28px] overflow-hidden relative flex flex-col pt-8 px-4">
                             <div class="bg-primary-50 p-3 rounded-lg text-[10px] mb-2 border border-primary-100">
                                 How has my metabolic flexibility improved?
                             </div>
                             <div class="text-[10px] text-gray-500 leading-relaxed mt-2">
                                 Your fat oxidation rate at Zone 2 intensity has increased 18% over the past 8 weeks, indicating improved metabolic flexibility and endurance capacity...
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
					<div class="text-xs text-gray-400 mb-2">Clinical validation.</div>
					<h3 class="text-2xl font-medium max-w-xs">Technology derived from validated spiroergometry.</h3>
				</div>
				<!-- Abstract breath visualization -->
				<div class="absolute bottom-0 right-0 w-full h-64 opacity-20">
                    <svg viewBox="0 0 200 100" class="w-full h-full">
                        <path d="M 0 50 Q 25 30, 50 50 T 100 50 T 150 50 T 200 50" stroke="white" fill="none" stroke-width="2"/>
                        <path d="M 0 60 Q 25 40, 50 60 T 100 60 T 150 60 T 200 60" stroke="white" fill="none" stroke-width="1.5" opacity="0.7"/>
                        <path d="M 0 70 Q 25 50, 50 70 T 100 70 T 150 70 T 200 70" stroke="white" fill="none" stroke-width="1" opacity="0.5"/>
                    </svg>
				</div>
			</div>
			<!-- Right Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">Privacy & security.</div>
					<h3 class="text-2xl font-medium max-w-xs">Your metabolic data stays secure and private.</h3>
				</div>
				<!-- Encrypted data visualization -->
				<div class="absolute bottom-8 right-8 text-right font-mono text-3xl opacity-30 blur-[2px] select-none pointer-events-none">
					<div>VO₂|%x$9yT</div>
					<div>VCO₂|I7m/@</div>
					<div>RER|&5a!</div>
					<div>Zone|?Pm_Lw</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Pricing Section -->
	<section class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full text-center">
		<h2 class="text-3xl md:text-4xl font-medium mb-4">Clinical precision meets accessibility.</h2>
		<p class="text-gray-500 text-sm max-w-lg mx-auto mb-16">
			Start with insurance-reimbursed clinical diagnostics, or choose direct athlete performance optimization. Both deliver the same clinical-grade accuracy.
		</p>

		<div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto">
			<!-- Clinical Plan -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm">
				<div class="w-10 h-10 bg-gray-100 rounded-lg mb-6 flex items-center justify-center">
					<svg class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
						<path d="M9 12l2 2 4-4"/>
						<circle cx="12" cy="12" r="10"/>
					</svg>
				</div>
				<h3 class="text-xl font-bold mb-1">Clinical</h3>
				<p class="text-xs text-gray-500 mb-6">Insurance-reimbursed diagnostics.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">Covered</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">Through medical partners and insurance billing.</div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Clinically validated metabolic diagnostics via medical partners.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						True breath-by-breath O₂/CO₂ gas exchange measurement.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						AI-powered interpretation and clinical reporting.
					</li>
				</ul>

				<button class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors">Find a Partner</button>
			</div>

			<!-- Performance Plan -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm border-2 border-primary-100 relative overflow-hidden">
                <div class="absolute top-0 right-0 bg-primary-100 text-primary-700 text-[10px] font-bold px-3 py-1 rounded-bl-xl">FOR ATHLETES</div>
				<div class="w-10 h-10 bg-primary-50 rounded-lg mb-6 flex items-center justify-center">
					<svg class="w-6 h-6 text-primary-600" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
						<path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>
					</svg>
				</div>
				<h3 class="text-xl font-bold mb-1">Performance</h3>
				<p class="text-xs text-gray-500 mb-6">Direct athlete optimization platform.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">€499</span>
					<span class="text-xs text-gray-500">/yr</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">Includes device and unlimited breath analysis.</div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Personal CORTEX LIFE mobile breath analyzer device.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Unlimited metabolic testing with real-time training zones.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Advanced AI insights: recovery signals, metabolic flexibility, longevity indicators.
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-green-500 shrink-0">{@html Check}</span>
						Longitudinal breath-data tracking and performance optimization.
					</li>
				</ul>

				<button class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors">Get Started</button>
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
                    <div class="px-4 pb-4 text-xs text-gray-500 leading-relaxed">
                        {#if i === 0}
                            CORTEX LIFE measures true breath-by-breath gas exchange (O₂ and CO₂), not inferred estimates. While wearables use heart rate and motion sensors to guess metabolic activity, we deliver clinical-grade spiroergometry data—the same technology used in medical diagnostics and elite sports science.
                        {:else if i === 1}
                            Breath gas analysis reveals your actual metabolic state: fat vs. carb oxidation rates, aerobic capacity (VO₂max), training zones based on real gas exchange, recovery status, and metabolic flexibility. This data can't be inferred from heart rate or motion alone.
                        {:else if i === 2}
                            Yes. CORTEX LIFE starts with reimbursed, clinically validated metabolic diagnostics through medical partners. We work with clinics and physicians who can bill insurance for diagnostic testing, making clinical-grade metabolic insights accessible.
                        {:else if i === 3}
                            No. CORTEX LIFE is a mobile breath gas analyzer. After initial setup, you can perform metabolic testing anywhere—during training, at home, or on the go. The device pairs with your smartphone for real-time analysis.
                        {:else if i === 4}
                            Our AI layer translates complex gas exchange data (VO₂, VCO₂, RER) into actionable insights: personalized training zones, recovery recommendations, metabolic flexibility scores, and longevity indicators. It learns from your longitudinal breath data to provide increasingly personalized guidance.
                        {/if}
                    </div>
                {/if}
			{/each}
		</div>
		<div class="text-center mt-12">
			<button class="bg-white border border-gray-200 px-6 py-3 rounded text-xs font-medium hover:bg-gray-50 transition-colors">
				View All FAQs
			</button>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-[#F5F5F3] py-16 px-6 md:px-12 text-[11px] text-gray-500">
		<div class="max-w-[1400px] mx-auto">
			<div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-12 gap-8">
				<div class="flex items-center gap-3">
					<div class="w-7 h-7 text-black">
						<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
							<mask
								id="mask0_footer"
								style="mask-type:luminance"
								maskUnits="userSpaceOnUse"
								x="3"
								y="1"
								width="18"
								height="22"
							>
								<path d="M3 1H20.7794V22.3353H3V1Z" fill="white" />
							</mask>
							<g mask="url(#mask0_footer)">
								<path
									d="M14.1516 3.24638L12.4034 2.77795L10.9302 8.27606L9.60014 3.31233L7.85194 3.78076L9.28896 9.14369L5.70969 5.56443L4.42993 6.84419L8.35594 10.7702L3.46671 9.46017L2.99829 11.2083L8.34038 12.6397C8.27922 12.3759 8.24687 12.1011 8.24687 11.8187C8.24687 9.81953 9.86746 8.19894 11.8666 8.19894C13.8657 8.19894 15.4863 9.81953 15.4863 11.8187C15.4863 12.0993 15.4544 12.3724 15.394 12.6347L20.2489 13.9356L20.7173 12.1874L15.354 10.7503L20.2436 9.44012L19.7751 7.69196L14.412 9.12898L17.9913 5.54972L16.7115 4.26998L12.84 8.14156L14.1516 3.24638Z"
									fill="currentColor"
								/>
								<path
									d="M15.3888 12.655C15.2389 13.2887 14.9225 13.8579 14.4883 14.314L18.0056 17.8313L19.2853 16.5515L15.3888 12.655Z"
									fill="currentColor"
								/>
								<path
									d="M14.4529 14.3508C14.0135 14.7996 13.4582 15.1345 12.8354 15.3071L14.1153 20.0836L15.8635 19.6151L14.4529 14.3508Z"
									fill="currentColor"
								/>
								<path
									d="M12.7701 15.3246C12.4812 15.3989 12.1784 15.4384 11.8663 15.4384C11.5319 15.4384 11.2082 15.393 10.9008 15.3082L9.61981 20.089L11.368 20.5574L12.7701 15.3246Z"
									fill="currentColor"
								/>
								<path
									d="M10.839 15.2905C10.2258 15.1093 9.68038 14.7702 9.24994 14.3201L5.72406 17.8459L7.00382 19.1257L10.839 15.2905Z"
									fill="currentColor"
								/>
								<path
									d="M9.22084 14.2889C8.79778 13.836 8.48962 13.2743 8.34294 12.6505L3.47211 13.9556L3.94053 15.7038L9.22084 14.2889Z"
									fill="currentColor"
								/>
							</g>
						</svg>
					</div>
					<span class="text-lg font-bold tracking-tight text-black">CORTEX LIFE</span>
				</div>
				<div class="flex flex-wrap gap-6 font-medium text-gray-600">
					<a href="#" class="hover:text-black">Technology</a>
					<a href="#" class="hover:text-black">For Athletes</a>
					<a href="#" class="hover:text-black">For Clinics</a>
					<a href="#" class="hover:text-black">FAQ</a>
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
				<p>CORTEX LIFE is a technology company providing mobile breath gas analysis devices and AI-powered metabolic interpretation software. Medical diagnostic services are provided by independent licensed healthcare providers and medical partners. CORTEX LIFE does not provide medical advice, diagnosis, or treatment. The device and software are intended to support clinical decision-making and performance optimization, not replace professional medical consultation.</p>
				<p>Insurance reimbursement availability varies by provider and region. Clinical pathway pricing is determined by medical partners according to local insurance billing practices. Performance pathway pricing includes device hardware and unlimited software access. For complete details, see our Terms & Conditions.</p>
				<p>By using CORTEX LIFE services, you agree to our data collection and privacy practices. All breath analysis data is encrypted and stored securely. Message and data rates may apply for mobile app usage.</p>
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

