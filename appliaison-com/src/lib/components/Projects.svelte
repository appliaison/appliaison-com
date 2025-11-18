<script lang="ts">
	/**
	 * Projects Section Component
	 * Showcases portfolio projects with descriptions and links
	 * Features responsive card grid with hover effects
	 */

	// Project data structure
	interface Project {
		title: string;
		description: string;
		technologies: string[];
		github?: string;
		demo?: string;
		image?: string;
	}

	const projects: Project[] = [
		{
			title: 'RealSmart - AI Powered Real Estate',
			description: 'Platform enabling fractionalized ownership of real estate on the blockchain using smart contracts. Revolutionizing property investment with transparent, secure, and accessible real estate transactions.',
			technologies: ['Artificial Intelligence', 'Smart Contracts', 'React', 'AI/ML', 'Python'],
			demo: 'https://appliaison.com',
			image: '🏠'
		},
		{
			title: 'SmartStack - Smart Agents Platform',
			description: 'Smart Agents platform for smart contracts management and maintenance. Providing businesses with secure, auditable, and efficient contract deployment and monitoring solutions.',
			technologies: ['Artificial Intelligence', 'Ethereum', 'Node.js', 'Python', 'AI/ML'],
			demo: 'https://appliaison.com',
			image: '📜'
		},
		{
			title: 'SmartSuite - Agent Launchpad',
			description: 'End-to-end launchpad for initiating agents. Complete solution for agent creation, management and distribution built-in compliance and security features.',
			technologies: ['Artificial Intelligence', 'Smart Contracts', 'Crypto', 'React', 'Web3'],
			demo: 'https://appliaison.com',
			image: '🪙'
		},
		{
			title: 'Health+ - Fitness & Wellness',
			description: 'Comprehensive fitness tracking application that allows users to monitor nutrition, track workouts, and connect with trusted healthcare professionals for personalized guidance and support.',
			technologies: ['React Native', 'Node.js', 'MongoDB', 'Firebase', 'ML'],
			demo: 'https://appliaison.com',
			image: '💪'
		},
		{
			title: 'SureServ - Home Services Platform',
			description: 'AI-powered digital platform connecting households with reliable, on-demand home service providers. Simplifying renovations, cleaning, maintenance, and repairs with verified professionals.',
			technologies: ['React Native', 'AI/ML', 'AWS', 'PostgreSQL', 'Stripe'],
			demo: 'https://appliaison.com',
			image: '🏡'
		},
		{
			title: 'Vi Card - Virtual Business Cards',
			description: 'Digital business card application designed to revolutionize networking. Manage digital cards, connect with nearby professionals, and streamline professional, personal, and matrimonial connections.',
			technologies: ['Flutter', 'Firebase', 'NFC', 'Cloud Functions', 'Analytics'],
			demo: 'https://appliaison.com',
			image: '💳'
		},
		{
			title: 'Rapicue - Healthcare Platform',
			description: 'Healthcare application providing swift and comprehensive care including self-assessment tools, online doctor consultations, prescription management, and emergency ambulance services.',
			technologies: ['React Native', 'Node.js', 'WebRTC', 'MongoDB', 'Twilio'],
			demo: 'https://appliaison.com',
			image: '🏥'
		},
		{
			title: 'Propz.ai - AI Property Management',
			description: 'AI-powered property management platform streamlining real estate operations with intelligent automation, tenant management, maintenance scheduling, and financial analytics.',
			technologies: ['Next.js', 'AI/ML', 'Python', 'PostgreSQL', 'AWS'],
			demo: 'https://appliaison.com',
			image: '🏢'
		},
		{
			title: 'Enterprise ERP Solutions',
			description: 'Whitelabel ERP and CRM integrations connecting businesses with customers on mobile devices. Cloud-first solutions with real-time business intelligence powered by TensorFlow.',
			technologies: ['React', 'Node.js', 'TensorFlow', 'Kubernetes', 'PostgreSQL'],
			demo: 'https://appliaison.com',
			image: '📊'
		}
	];
</script>

<section id="projects" class="py-20 px-4 sm:px-6 lg:px-8">
	<div class="max-w-6xl mx-auto">
		<!-- Section Header -->
		<div class="text-center mb-12">
			<h2 class="text-4xl font-bold text-gradient mb-4">Our Portfolio</h2>
			<div class="w-20 h-1 bg-neural-blue mx-auto rounded-full"></div>
			<p class="mt-4 text-gray-400 max-w-2xl mx-auto">
				Transformative solutions delivered across mobile, cloud, AI, and blockchain domains
			</p>
		</div>

		<!-- Projects Grid -->
		<div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
			{#each projects as project, index}
				<div
					class="bg-neural-dark rounded-xl overflow-hidden border border-neural-blue/20 card-glow animate-slide-up"
					style="animation-delay: {index * 0.05}s;"
				>
			<!-- Project Image/Icon -->
			<div class="h-48 bg-gradient-to-br from-neural-blue/20 to-neural-blue-light/20 flex items-center justify-center">
				{#if project.image}
					<span class="text-8xl">{project.image}</span>
				{:else}
					<svg class="w-16 h-16 text-neural-blue/50" fill="currentColor" viewBox="0 0 20 20">
						<path fill-rule="evenodd" d="M4 3a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V5a2 2 0 00-2-2H4zm12 12H4l4-8 3 6 2-4 3 6z" clip-rule="evenodd" />
					</svg>
				{/if}
			</div>

					<!-- Project Content -->
					<div class="p-6">
						<!-- Project Title -->
						<h3 class="text-xl font-semibold text-gray-200 mb-2">
							{project.title}
						</h3>

						<!-- Project Description -->
						<p class="text-gray-400 text-sm mb-4 line-clamp-3">
							{project.description}
						</p>

						<!-- Technologies -->
						<div class="flex flex-wrap gap-2 mb-4">
							{#each project.technologies as tech}
								<span class="px-2 py-1 bg-neural-darker border border-neural-blue/30 rounded text-neural-blue-light text-xs">
									{tech}
								</span>
							{/each}
						</div>

						<!-- Project Links -->
						<div class="flex gap-3">
							{#if project.github}
								<a
									href={project.github}
									target="_blank"
									rel="noopener noreferrer"
									class="flex items-center gap-1 text-gray-400 hover:text-neural-blue transition-colors text-sm"
								>
									<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
										<path fill-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" clip-rule="evenodd" />
									</svg>
									Code
								</a>
							{/if}

							{#if project.demo}
								<a
									href={project.demo}
									target="_blank"
									rel="noopener noreferrer"
									class="flex items-center gap-1 text-gray-400 hover:text-neural-blue transition-colors text-sm"
								>
									<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
										<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
									</svg>
									Demo
								</a>
							{/if}
						</div>
					</div>
				</div>
			{/each}
		</div>

	<!-- View More Buttons -->
	<div class="text-center mt-12 flex flex-col sm:flex-row gap-4 justify-center">
		<a
			href="/gallery/propzai"
			class="inline-flex items-center gap-2 px-6 py-3 bg-neural-blue text-white rounded-lg hover:shadow-lg hover:shadow-neural-blue/40 transition-all duration-200 font-medium"
		>
			<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
			</svg>
			View PropzAI Gallery
		</a>
		<a
			href="#contact"
			class="inline-flex items-center gap-2 px-6 py-3 bg-neural-dark border-2 border-neural-blue text-neural-blue rounded-lg hover:bg-neural-blue hover:text-white transition-all duration-200 font-medium"
		>
			<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
			</svg>
			Discuss Your Project
		</a>
	</div>
	</div>
</section>
