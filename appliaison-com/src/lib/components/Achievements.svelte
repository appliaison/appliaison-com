<script lang="ts">
	/**
	 * Key Achievements Section
	 * Highlights major accomplishments and career milestones
	 */

	const achievements = [
		{
			icon: '🏠',
			title: 'Blockchain Real Estate Innovation',
			description: 'Pioneered fractionalized real estate ownership on blockchain with RealSmart platform, enabling transparent and accessible property investment through smart contracts.',
			impact: 'Industry Innovation',
			link: 'https://appliaison.com'
		},
		{
			icon: '🤖',
			title: 'AI-Powered Service Platforms',
			description: 'Deployed multiple AI-powered platforms including SureServ for on-demand home services, leveraging machine learning for optimal service provider matching and customer satisfaction.',
			impact: '1M+ Users Served',
			link: 'https://appliaison.com'
		},
		{
			icon: '📱',
			title: 'Cross-Platform Mobile Excellence',
			description: 'Delivered 50+ production-ready mobile applications across iOS and Android platforms, serving millions of users with enterprise-grade performance and reliability.',
			impact: '50+ Apps Deployed',
			link: 'https://appliaison.com'
		},
		{
			icon: '☁️',
			title: 'Whitelabel Cloud Platform (WCaaS)',
			description: 'Built comprehensive Whitelabel-Cloud-as-a-Service platform enabling rapid deployment of B2B and B2C applications with enterprise logistics and on-demand service delivery.',
			impact: 'Enterprise Scale',
			link: 'https://appliaison.com'
		},
		{
			icon: '⛓️',
			title: 'Blockchain Ecosystem Development',
			description: 'Created comprehensive blockchain ecosystem including SmartStack for contract management and SmartSuite for token crowd-sales, driving DeFi innovation.',
			impact: 'DeFi Leadership',
			link: 'https://appliaison.com'
		},
		{
			icon: '🏥',
			title: 'Healthcare Digital Transformation',
			description: 'Revolutionized healthcare delivery with Rapicue platform featuring telemedicine, self-assessment tools, and emergency services integration, improving patient care accessibility.',
			impact: 'Healthcare Innovation',
			link: 'https://appliaison.com'
		}
	];
</script>

<section class="py-20 px-4 sm:px-6 lg:px-8">
	<div class="max-w-6xl mx-auto">
		<!-- Section Header -->
		<div class="text-center mb-12">
			<h2 class="text-4xl font-bold text-gradient mb-4">Our Impact</h2>
			<div class="w-20 h-1 bg-neural-blue mx-auto rounded-full"></div>
			<p class="mt-4 text-gray-400 max-w-2xl mx-auto">
				Transforming industries through innovative technology solutions
			</p>
		</div>

		<!-- Achievements Grid -->
		<div class="grid md:grid-cols-2 gap-6">
			{#each achievements as achievement, index}
				<div
					class="bg-neural-dark rounded-xl p-6 border border-neural-blue/20 card-glow animate-slide-up"
					style="animation-delay: {index * 0.1}s;"
				>
					<div class="flex items-start gap-4">
						<!-- Icon -->
						<div class="text-5xl flex-shrink-0">
							{achievement.icon}
						</div>

						<!-- Content -->
						<div class="flex-1">
							<h3 class="text-xl font-semibold text-gray-200 mb-2">
								{achievement.title}
							</h3>
							<p class="text-gray-400 text-sm mb-3 leading-relaxed">
								{achievement.description}
							</p>

							<!-- Impact Badge -->
							<div class="flex items-center gap-3">
								<span class="px-3 py-1 bg-neural-blue/20 border border-neural-blue/40 rounded-full text-neural-blue-light text-xs font-medium">
									{achievement.impact}
								</span>
								{#if achievement.link}
									<a
										href={achievement.link}
										target="_blank"
										rel="noopener noreferrer"
										class="text-neural-blue hover:text-neural-blue-light transition-colors text-sm flex items-center gap-1"
									>
										View Project
										<svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
											<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
										</svg>
									</a>
								{/if}
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>

		<!-- Bottom CTA -->
		<div class="mt-12 text-center">
			<p class="text-gray-400 mb-6">
				Ready to transform your business with innovative technology?
			</p>
			<a
				href="#contact"
				class="inline-flex items-center gap-2 px-6 py-3 bg-neural-blue text-white rounded-lg hover:bg-neural-blue-light transition-colors duration-200 font-medium"
			>
				Start Your Project
				<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6" />
				</svg>
			</a>
		</div>
	</div>
</section>

