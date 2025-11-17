<script lang="ts">
	/**
	 * Contact Section Component
	 * Provides contact form and social media links
	 * Features form validation and submission handling
	 */



	// Form state using Svelte 5 runes
	let formData = $state({
		name: '',
		email: '',
		message: ''
	});

	let formStatus = $state<'idle' | 'submitting' | 'success' | 'error'>('idle');
	let errorMessage = $state('');

	/**
	 * Handle form submission via API
	 * @param event - Form submit event
	 */
	async function handleSubmit(event: Event) {
		event.preventDefault();
		formStatus = 'submitting';

		try {
			const response = await fetch('/api/contact', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify(formData)
			});

			const result = await response.json();

			if (!response.ok) {
				throw new Error(result.error || 'Failed to send message');
			}

			formStatus = 'success';

			// Reset form after 3 seconds
			setTimeout(() => {
				formData = { name: '', email: '', message: '' };
				formStatus = 'idle';
			}, 3000);
		} catch (error) {
			console.error('Error sending message:', error);
			formStatus = 'error';
			errorMessage = error instanceof Error
				? error.message
				: 'Failed to send message. Please try again or email us directly at info@appliaison.com';

			// Reset error after 5 seconds
			setTimeout(() => {
				formStatus = 'idle';
				errorMessage = '';
			}, 5000);
		}
	}

	// Social links
	const socialLinks = [
		{
			name: 'LinkedIn',
			url: 'https://www.linkedin.com/company/appliaison',
			icon: 'M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z'
		},
		{
			name: 'Twitter',
			url: 'https://twitter.com/appliaison',
			icon: 'M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z'
		},
		{
			name: 'Email',
			url: 'mailto:info@appliaison.com',
			icon: 'M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z'
		},
		{
			name: 'Website',
			url: 'https://appliaison.com',
			icon: 'M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z'
		}
	];
</script>

<section id="contact" class="py-20 px-4 sm:px-6 lg:px-8 bg-neural-dark/30">
	<div class="max-w-4xl mx-auto">
		<!-- Section Header -->
		<div class="text-center mb-12">
			<h2 class="text-4xl font-bold text-gradient mb-4">Let's Build Something Amazing</h2>
			<div class="w-20 h-1 bg-neural-blue mx-auto rounded-full"></div>
			<p class="mt-4 text-gray-400">
				Ready to transform your business with cutting-edge technology? Get in touch with our team!
			</p>
		</div>

		<div class="grid md:grid-cols-2 gap-12">
			<!-- Contact Form -->
			<div>
				<form on:submit={handleSubmit} class="space-y-6">
					<!-- Name Input -->
					<div>
						<label for="name" class="block text-gray-300 mb-2 font-medium">
							Name
						</label>
						<input
							type="text"
							id="name"
							bind:value={formData.name}
							required
							class="w-full px-4 py-3 bg-neural-dark border border-neural-blue/30 rounded-lg focus:outline-none focus:border-neural-blue text-gray-200 transition-colors"
							placeholder="Your name"
							disabled={formStatus === 'submitting'}
						/>
					</div>

					<!-- Email Input -->
					<div>
						<label for="email" class="block text-gray-300 mb-2 font-medium">
							Email
						</label>
						<input
							type="email"
							id="email"
							bind:value={formData.email}
							required
							class="w-full px-4 py-3 bg-neural-dark border border-neural-blue/30 rounded-lg focus:outline-none focus:border-neural-blue text-gray-200 transition-colors"
							placeholder="your.email@example.com"
							disabled={formStatus === 'submitting'}
						/>
					</div>

					<!-- Message Textarea -->
					<div>
						<label for="message" class="block text-gray-300 mb-2 font-medium">
							Message
						</label>
						<textarea
							id="message"
							bind:value={formData.message}
							required
							rows="5"
							class="w-full px-4 py-3 bg-neural-dark border border-neural-blue/30 rounded-lg focus:outline-none focus:border-neural-blue text-gray-200 transition-colors resize-none"
							placeholder="Your message..."
							disabled={formStatus === 'submitting'}
						></textarea>
					</div>

					<!-- Submit Button -->
					<button
						type="submit"
						disabled={formStatus === 'submitting' || formStatus === 'success'}
						class="w-full px-6 py-3 bg-neural-blue text-white rounded-lg hover:bg-neural-blue-light transition-colors duration-200 font-medium disabled:opacity-50 disabled:cursor-not-allowed card-glow"
					>
						{#if formStatus === 'submitting'}
							Sending...
						{:else if formStatus === 'success'}
							Message Sent!
						{:else}
							Send Message
						{/if}
					</button>

					<!-- Status Messages -->
					{#if formStatus === 'success'}
						<p class="text-green-400 text-center text-sm">
							Thank you for your message! I'll get back to you soon.
						</p>
					{/if}

					{#if formStatus === 'error'}
						<p class="text-red-400 text-center text-sm">
							{errorMessage}
						</p>
					{/if}
				</form>
			</div>

			<!-- Contact Info & Social Links -->
			<div class="space-y-8">
				<!-- Social Links -->
				<div>
					<h3 class="text-xl font-semibold text-gray-200 mb-4">Connect With Us</h3>
					<div class="space-y-3">
						{#each socialLinks as social}
							<a
								href={social.url}
								target="_blank"
								rel="noopener noreferrer"
								class="flex items-center gap-3 p-3 bg-neural-dark border border-neural-blue/20 rounded-lg hover:border-neural-blue hover:bg-neural-dark/50 transition-all duration-200 group"
							>
								<svg class="w-6 h-6 text-neural-blue group-hover:text-neural-blue-light transition-colors" fill="currentColor" viewBox="0 0 24 24">
									<path fill-rule="evenodd" d={social.icon} clip-rule="evenodd" />
								</svg>
								<span class="text-gray-300 group-hover:text-neural-blue-light transition-colors">
									{social.name}
								</span>
							</a>
						{/each}
					</div>
				</div>

				<!-- Additional Info -->
				<div class="p-6 bg-neural-dark border border-neural-blue/20 rounded-lg">
					<h3 class="text-xl font-semibold text-gray-200 mb-3">Let's Transform Together</h3>
					<p class="text-gray-400 mb-4">
						We're always excited to discuss new projects and opportunities.
						Whether you need mobile apps, cloud solutions, AI integration, or blockchain development,
						our team is ready to bring your vision to life!
					</p>
					<div class="space-y-2">
						<div class="flex items-center gap-2 text-neural-blue">
							<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
							</svg>
							<span class="text-gray-400">info@appliaison.com</span>
						</div>
						<div class="flex items-center gap-2 text-neural-blue">
							<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" />
							</svg>
							<span class="text-gray-400">Global Services</span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
