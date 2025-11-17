<script lang="ts">
	/**
	 * About Section Component
	 * Displays personal introduction and professional background
	 * Responsive layout with image and text content
	 */
</script>

<section id="about" class="py-20 px-4 sm:px-6 lg:px-8">
	<div class="max-w-6xl mx-auto">
		<!-- Section Header -->
		<div class="text-center mb-12">
			<h2 class="text-4xl font-bold text-gradient mb-4">About AppLiaison</h2>
			<div class="w-20 h-1 bg-neural-blue mx-auto rounded-full"></div>
		</div>

		<!-- About Content Grid -->
		<div class="grid md:grid-cols-2 gap-12 items-center">
			<!-- Brand Visual Element -->
			<div class="order-2 md:order-1">
				<div class="relative">
					<!-- Company visual representation -->
					<div class="aspect-square rounded-2xl bg-gradient-to-br from-neural-blue/20 via-neural-dark to-neural-blue-light/20 flex items-center justify-center shadow-2xl card-glow border border-neural-blue/30">
						<div class="text-center p-8">
							<div class="text-8xl mb-6">🚀</div>
							<h3 class="text-3xl font-bold text-gradient mb-2">AppLiaison</h3>
							<p class="text-neural-blue-light text-lg">Innovation at Scale</p>
						</div>
					</div>
					<!-- Decorative floating element -->
					<div class="absolute -top-4 -right-4 w-24 h-24 bg-neural-blue/10 rounded-full blur-xl"></div>
					<div class="absolute -bottom-4 -left-4 w-32 h-32 bg-neural-blue-light/10 rounded-full blur-xl"></div>
				</div>
			</div>

		<!-- About Text Content -->
		<div class="order-1 md:order-2 space-y-6">
			<p class="text-gray-300 text-lg leading-relaxed">
				AppLiaison Inc. is a full-stack app development agency specializing in mobile and web app
				infrastructure solutions. Our expertise spans SaaS, AI, Blockchain, Big Data ERP, Big Data CRM,
				Enterprise Logistics, on-demand services, Sentiment Analysis, Machine Learning integrations, and IoT.
			</p>

			<p class="text-gray-400 leading-relaxed">
				We offer a comprehensive suite of B2C applications that integrate on-demand service delivery and
				order-fulfillment services, as well as cloud-enterprise appointment-booking logistics automation.
				Our Whitelabel-Cloud-as-a-Service (WCaaS) platform enables businesses of all sizes to rapidly
				deploy scalable, customized solutions.
			</p>

			<p class="text-gray-400 leading-relaxed">
				Our mission is to empower businesses with state-of-the-art technology solutions that streamline
				operations, enhance user experiences, and drive growth. We stay at the forefront of emerging
				technologies, focusing on the intersection of cloud, mobile, blockchain, and artificial intelligence
				to deliver transformative products.
			</p>

			<!-- Key Highlights -->
			<div class="grid grid-cols-3 gap-4 pt-6">
				<div class="p-4 bg-neural-dark rounded-lg border border-neural-blue/20">
					<p class="text-3xl font-bold text-neural-blue mb-1">50+</p>
					<p class="text-gray-400 text-sm">Projects Delivered</p>
				</div>
				<div class="p-4 bg-neural-dark rounded-lg border border-neural-blue/20">
					<p class="text-3xl font-bold text-neural-blue mb-1">B2B/B2C</p>
					<p class="text-gray-400 text-sm">Solutions</p>
				</div>
				<div class="p-4 bg-neural-dark rounded-lg border border-neural-blue/20">
					<p class="text-3xl font-bold text-neural-blue mb-1">24/7</p>
					<p class="text-gray-400 text-sm">Support</p>
				</div>
			</div>
		</div>
		</div>
	</div>
</section>
