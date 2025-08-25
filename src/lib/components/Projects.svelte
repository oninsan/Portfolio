<script lang="ts">
	import { onMount } from 'svelte';
	import Card from './ui/Card.svelte';
	import Badge from './ui/Badge.svelte';
	import { ExternalLink, Github, Eye } from 'lucide-svelte';
	
	let projectsElement:Element;
	let activeFilter = 'All';
	
	const filters = ['All', 'React', 'Vue.js', 'Svelte', 'Full Stack'];
	
	const projects = [
		{
			id: 1,
			title: 'E-Commerce Platform',
			description: 'A full-featured e-commerce platform with payment integration, inventory management, and admin dashboard.',
			image: 'https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=400&h=300&fit=crop',
			technologies: ['React', 'Node.js', 'MongoDB', 'Stripe'],
			category: 'Full Stack',
			liveUrl: 'https://example.com',
			githubUrl: 'https://github.com/example'
		},
		{
			id: 2,
			title: 'Task Management App',
			description: 'A collaborative task management application with real-time updates and team collaboration features.',
			image: 'https://images.unsplash.com/photo-1611224923853-80b023f02d71?w=400&h=300&fit=crop',
			technologies: ['Vue.js', 'Firebase', 'Vuetify'],
			category: 'Vue.js',
			liveUrl: 'https://example.com',
			githubUrl: 'https://github.com/example'
		},
		{
			id: 3,
			title: 'Weather Dashboard',
			description: 'A beautiful weather dashboard with detailed forecasts, maps, and customizable widgets.',
			image: 'https://images.unsplash.com/photo-1504608524841-42fe6f032b4b?w=400&h=300&fit=crop',
			technologies: ['Svelte', 'API Integration', 'Chart.js'],
			category: 'Svelte',
			liveUrl: 'https://example.com',
			githubUrl: 'https://github.com/example'
		},
		{
			id: 4,
			title: 'Portfolio Website',
			description: 'A responsive portfolio website with smooth animations and modern design principles.',
			image: 'https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?w=400&h=300&fit=crop',
			technologies: ['React', 'Tailwind CSS', 'Framer Motion'],
			category: 'React',
			liveUrl: 'https://example.com',
			githubUrl: 'https://github.com/example'
		},
		{
			id: 5,
			title: 'Blog Platform',
			description: 'A full-stack blog platform with CMS capabilities, user authentication, and comment system.',
			image: 'https://images.unsplash.com/photo-1486312338219-ce68d2c6f44d?w=400&h=300&fit=crop',
			technologies: ['Next.js', 'PostgreSQL', 'Prisma', 'NextAuth'],
			category: 'Full Stack',
			liveUrl: 'https://example.com',
			githubUrl: 'https://github.com/example'
		},
		{
			id: 6,
			title: 'Fitness Tracker',
			description: 'A mobile-first fitness tracking application with workout plans and progress monitoring.',
			image: 'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=400&h=300&fit=crop',
			technologies: ['React Native', 'Firebase', 'Charts'],
			category: 'React',
			liveUrl: 'https://example.com',
			githubUrl: 'https://github.com/example'
		}
	];
	
	$: filteredProjects = activeFilter === 'All' 
		? projects 
		: projects.filter(project => project.category === activeFilter);
	
	onMount(() => {
		const observer = new IntersectionObserver((entries) => {
			entries.forEach((entry) => {
				if (entry.isIntersecting) {
					entry.target.classList.add('animate-projects');
          window.location.hash = '#projects'  
				}
			});
		});
		
		if (projectsElement) observer.observe(projectsElement);
		
		return () => observer.disconnect();
	});
</script>

<section id="projects" class="py-20 bg-gray-50" bind:this={projectsElement}>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="text-center mb-16">
			<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">Featured Projects</h2>
			<div class="w-24 h-1 bg-primary mx-auto mb-6"></div>
			<p class="text-gray-600 max-w-3xl mx-auto text-lg">
				Here are some of my recent projects that showcase my skills and experience
			</p>
		</div>

		<!-- Filter Buttons -->
		<div class="flex flex-wrap justify-center gap-4 mb-12">
			{#each filters as filter}
				<button
					on:click={() => activeFilter = filter}
					class="px-6 py-2 rounded-full font-medium transition-all duration-300
						{activeFilter === filter 
							? 'bg-primary text-white shadow-lg' 
							: 'bg-white text-gray-600 hover:bg-primary hover:text-white shadow-md'}"
				>
					{filter}
				</button>
			{/each}
		</div>

		<!-- Projects Grid -->
		<div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
			{#each filteredProjects as project, index (project.id)}
				<Card className="group overflow-hidden hover:shadow-2xl transition-all duration-500 hover:-translate-y-2 project-card">
					<!-- Project Image -->
					<div class="relative overflow-hidden">
						<img 
							src={project.image} 
							alt={project.title}
							class="w-full h-48 object-cover group-hover:scale-110 transition-transform duration-500"
						/>
						<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
							<div class="absolute bottom-4 left-4 right-4 flex justify-between">
								<a 
									href={project.liveUrl} 
									target="_blank" 
									rel="noopener noreferrer"
									class="bg-white text-gray-900 p-2 rounded-full hover:bg-primary hover:text-white transition-colors duration-200"
								>
									<Eye class="h-4 w-4" />
								</a>
								<a 
									href={project.githubUrl} 
									target="_blank" 
									rel="noopener noreferrer"
									class="bg-white text-gray-900 p-2 rounded-full hover:bg-primary hover:text-white transition-colors duration-200"
								>
									<Github class="h-4 w-4" />
								</a>
								<a 
									href={project.liveUrl} 
									target="_blank" 
									rel="noopener noreferrer"
									class="bg-white text-gray-900 p-2 rounded-full hover:bg-primary hover:text-white transition-colors duration-200"
								>
									<ExternalLink class="h-4 w-4" />
								</a>
							</div>
						</div>
					</div>

					<!-- Project Details -->
					<div class="p-6">
						<h3 class="text-xl font-bold text-gray-900 mb-2 group-hover:text-primary transition-colors duration-200">
							{project.title}
						</h3>
						<p class="text-gray-600 text-sm mb-4 leading-relaxed">
							{project.description}
						</p>

						<!-- Technologies -->
						<div class="flex flex-wrap gap-2 mb-4">
							{#each project.technologies as tech}
								<Badge variant="secondary" className="text-xs">
									{tech}
								</Badge>
							{/each}
						</div>

						<!-- Links -->
						<div class="flex space-x-4">
							<a 
								href={project.liveUrl} 
								target="_blank" 
								rel="noopener noreferrer"
								class="flex-1 bg-primary hover:bg-primary/90 text-white text-center py-2 px-4 rounded-lg font-medium transition-colors duration-200 text-sm"
							>
								Live Demo
							</a>
							<a 
								href={project.githubUrl} 
								target="_blank" 
								rel="noopener noreferrer"
								class="bg-gray-200 hover:bg-gray-300 text-gray-700 py-2 px-4 rounded-lg font-medium transition-colors duration-200 text-sm"
							>
								Code
							</a>
						</div>
					</div>
				</Card>
			{/each}
		</div>

		{#if filteredProjects.length === 0}
			<div class="text-center py-16">
				<p class="text-gray-500 text-lg">No projects found for the selected filter.</p>
			</div>
		{/if}
	</div>
</section>

<style>
	@keyframes fade-in-scale {
		from { 
			opacity: 0; 
			transform: translateY(30px) scale(0.95); 
		}
		to { 
			opacity: 1; 
			transform: translateY(0) scale(1); 
		}
	}
	
	.animate-projects .project-card {
		animation: fade-in-scale 0.6s ease-out both;
	}
</style>