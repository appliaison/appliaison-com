<svelte:head>
    <title>PropzAI Gallery | AppLiaison</title>
    <meta
        name="description"
        content="PropzAI is AppLiaison's AI-powered property operations platform delivering predictive maintenance, tenant intelligence, and automated financial reporting."
    />
    <meta property="og:title" content="PropzAI Gallery | AppLiaison" />
    <meta
        property="og:description"
        content="Explore how AppLiaison elevated PropzAI with AI-driven automation, predictive analytics, and a modern property intelligence portal."
    />
    <meta property="og:image" content="https://appliaison.com/propz-ai/propz-ai-1.png" />
    <meta property="og:url" content="https://appliaison.com/gallery/propzai" />
</svelte:head>

<script lang="ts">
    import Header from '$lib/components/Header.svelte';

    const highlights = [
        { label: 'Properties automated', value: '3,400+' },
        { label: 'Ops costs reduced', value: '38%' },
        { label: 'Predictive accuracy', value: '94%' }
    ];

    const features = [
        {
            title: 'Predictive Maintenance',
            description: 'IoT and work-order signals feed real-time anomaly detection that forecasts service tickets before failures.'
        },
        {
            title: 'Tenant Intelligence Hub',
            description: 'Unified tenant health scoring blends payments, sentiment, and engagement to surface risk in minutes.'
        },
        {
            title: 'AI Financial Copilot',
            description: 'Automates rent rolls, reconciliations, and KPI dashboards with structured guardrails and audit-ready logs.'
        },
        {
            title: 'Portfolio Command Center',
            description: 'Role-based insights, alerts, and workflows built for asset managers, leasing teams, and field operators.'
        }
    ];

    const techStack = [
        'Next.js + SvelteKit frontend shells',
        'Python FastAPI orchestration',
        'LangChain agentic workflows',
        'PostgreSQL + Timescale analytics',
        'Airflow pipelines',
        'AWS S3 + Bedrock',
        'Auth0 Enterprise',
        'Segment + Metabase telemetry'
    ];

    const milestones = [
        {
            phase: 'Discovery & Architecture',
            duration: 'Weeks 1-3',
            details: 'Shadowed leasing teams, defined service blueprints, and mapped telemetry to high-value automation targets.'
        },
        {
            phase: 'MVP & Data Backbone',
            duration: 'Weeks 4-9',
            details: 'Delivered core ingestion, cleaning, and AI scoring pipelines plus the first operator console.'
        },
        {
            phase: 'Scale & Enterprise Hardening',
            duration: 'Weeks 10-16',
            details: 'Added multi-market rollouts, SOC2-ready audit trails, role-based access, and multi-tenant billing.'
        }
    ];
</script>

<Header />

<section id="gallery-hero" class="relative bg-gradient-to-b from-black via-neural-dark to-black">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <div class="flex flex-col lg:flex-row gap-12 items-center">
            <div class="flex-1">
                <p class="text-sm uppercase tracking-[0.5rem] text-neural-blue mb-4">Gallery</p>
                <h1 class="text-4xl sm:text-5xl font-bold text-white mb-6">PropzAI · Intelligent Property Operations</h1>
                <p class="text-gray-300 leading-relaxed mb-8">
                    AppLiaison partnered with PropzAI to fuse AI agents, maintenance telemetry, and predictive finance into a unified operations cloud.
                    The result: faster service cycles, happier tenants, and CFO-grade reporting with one connected stack.
                </p>
                <div class="flex flex-wrap gap-4">
                    <a
                        href="/#projects"
                        class="inline-flex items-center gap-2 px-6 py-3 border border-white/20 rounded-lg text-white hover:bg-white/10 transition"
                    >
                        <span>← Back to Projects</span>
                    </a>
                    <a
                        href="/#contact"
                        class="inline-flex items-center gap-2 px-6 py-3 bg-neural-blue text-white rounded-lg hover:opacity-90 transition"
                    >
                        <span>Discuss A Similar Build</span>
                    </a>
                </div>
                <div class="flex flex-wrap gap-3 mt-4">
                    <a
                        href="#technical-blueprint"
                        class="inline-flex items-center gap-2 px-5 py-2.5 border border-white/20 rounded-full text-sm uppercase tracking-wide text-gray-200 hover:bg-white/10 transition"
                    >
                        Next
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                        </svg>
                    </a>
                    <a
                        href="#impact-timeline"
                        class="inline-flex items-center gap-2 px-5 py-2.5 border border-neural-blue/40 rounded-full text-sm uppercase tracking-wide text-neural-blue-light hover:bg-neural-blue/10 transition"
                    >
                        Forward
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                        </svg>
                    </a>
                </div>
            </div>
            <div class="flex-1">
                <div class="rounded-3xl overflow-hidden border border-white/10 shadow-2xl shadow-neural-blue/20">
                    <img src="/propz-ai/propz-ai-1.png" alt="PropzAI platform overview" class="w-full h-full object-cover" />
                </div>
            </div>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 mt-12">
            {#each highlights as item}
                <div class="bg-white/5 border border-white/10 rounded-2xl p-6 text-center">
                    <p class="text-3xl font-semibold text-white mb-2">{item.value}</p>
                    <p class="text-sm uppercase tracking-wide text-gray-400">{item.label}</p>
                </div>
            {/each}
        </div>
    </div>
</section>

<section class="py-20 bg-black px-4 sm:px-6 lg:px-8">
    <div class="max-w-6xl mx-auto">
        <div class="grid lg:grid-cols-2 gap-12">
            <div>
                <h2 class="text-3xl font-bold text-white mb-4">Why PropzAI Needed A Lift</h2>
                <p class="text-gray-300 leading-relaxed mb-6">
                    Disparate maintenance systems, spreadsheets, and siloed accounting workflows slowed growth for PropzAI's property clients.
                    AppLiaison architected an intelligent command center that blends telemetry, financial data, and AI copilot experiences to run modern portfolios.
                </p>
                <div class="space-y-4">
                    <div class="p-5 border border-neural-blue/30 rounded-2xl bg-neural-dark/40">
                        <p class="text-white font-semibold mb-2">Unified Data Mesh</p>
                        <p class="text-gray-300 text-sm">
                            Streaming ingestion from BMS, IoT, ticketing, and ERP feeds normalized models for analytics-grade decisions.
                        </p>
                    </div>
                    <div class="p-5 border border-neural-blue/30 rounded-2xl bg-neural-dark/40">
                        <p class="text-white font-semibold mb-2">Operator-Centric UX</p>
                        <p class="text-gray-300 text-sm">
                            Role-based journeys focused on daily tasks: asset triage, tenant outreach, budget insights, and approvals.
                        </p>
                    </div>
                </div>
            </div>
            <div>
                <h2 class="text-3xl font-bold text-white mb-6">Signature Capabilities</h2>
                <div class="grid gap-6">
                    {#each features as feature}
                        <div class="bg-gradient-to-br from-neural-dark to-black border border-white/10 rounded-2xl p-6">
                            <p class="text-lg font-semibold text-white mb-2">{feature.title}</p>
                            <p class="text-gray-300 text-sm leading-relaxed">{feature.description}</p>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>
</section>

<section id="technical-blueprint" class="py-20 bg-neural-dark px-4 sm:px-6 lg:px-8">
    <div class="max-w-6xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-10">Technical Blueprint</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            {#each techStack as tech}
                <div class="border border-white/10 rounded-2xl p-4 bg-black/40">
                    <p class="text-gray-200 text-sm">{tech}</p>
                </div>
            {/each}
        </div>
    </div>
</section>

<section id="impact-timeline" class="py-20 bg-black px-4 sm:px-6 lg:px-8">
    <div class="max-w-6xl mx-auto">
        <div class="grid lg:grid-cols-3 gap-8">
            {#each milestones as milestone}
                <div class="border border-neural-blue/30 rounded-2xl p-6 bg-neural-dark/40">
                    <p class="text-neural-blue text-sm font-semibold mb-2">{milestone.duration}</p>
                    <h3 class="text-xl text-white font-semibold mb-3">{milestone.phase}</h3>
                    <p class="text-gray-300 text-sm leading-relaxed">{milestone.details}</p>
                </div>
            {/each}
        </div>

        <div class="mt-16 bg-gradient-to-br from-neural-blue/20 to-transparent border border-neural-blue/40 rounded-3xl p-10">
            <p class="text-gray-200 text-lg italic mb-6">
                "AppLiaison engineered the AI nervous system we always wanted. Our operators open PropzAI every morning to see which assets need attention, why, and which lever to pull next."
            </p>
            <div>
                <p class="text-white font-semibold">Priya Solanki</p>
                <p class="text-gray-400 text-sm">COO, PropzAI</p>
            </div>
        </div>

        <div class="mt-12 flex flex-wrap gap-4">
            <a
                href="/#contact"
                class="inline-flex items-center gap-2 px-6 py-3 bg-neural-blue text-white rounded-xl hover:opacity-90 transition"
            >
                Start Your AI Deployment
            </a>
            <a
                href="/"
                class="inline-flex items-center gap-2 px-6 py-3 border border-white/20 text-white rounded-xl hover:bg-white/10 transition"
            >
                Return Home
            </a>
        </div>
    </div>
</section>
