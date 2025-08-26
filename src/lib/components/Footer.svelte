<script lang="ts">
	import { Heart } from 'lucide-svelte';
  const scrollToSection = (href:string)=> {
		const element = document.getElementById(href);
		if (element) {
			element.scrollIntoView({ behavior: 'smooth' });
			setTimeout(() => {
				window.location.hash = `${href}`;
			}, 500);
		}
	}
</script>

<footer class="bg-gray-900 text-white py-12">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="grid md:grid-cols-3 gap-8">
			<!-- About -->
			<div class="space-y-4">
				<h3 class="text-2xl font-bold">Niño Abao</h3>
				<p class="text-gray-300 leading-relaxed">
					A passionate web developer dedicated to creating amazing digital experiences 
					and bringing innovative ideas to life through code.
				</p>
				<div class="flex space-x-4">
					<a aria-label="svg" href="https://github.com/oninsan" target="_blank" rel="noopener noreferrer" 
						class="text-gray-400 hover:text-primary transition-colors duration-200">
						<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
							<path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/>
						</svg>
					</a>
					<a aria-label="svg" href="https://www.linkedin.com/in/ni%C3%B1o-abao-415124185/" target="_blank" rel="noopener noreferrer" 
						class="text-gray-400 hover:text-primary transition-colors duration-200">
						<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
							<path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
						</svg>
					</a>
					<a aria-label="svg" href="https://x.com/abao_nino47037" target="_blank" rel="noopener noreferrer" 
						class="text-gray-400 hover:text-primary transition-colors duration-200">
						<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
							<path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
						</svg>
					</a>
				</div>
			</div>

			<!-- Quick Links -->
			<div class="space-y-4">
				<h3 class="text-xl font-bold">Quick Links</h3>
				<ul class="space-y-2">
					<li>
						<button 
							onclick={() => scrollToSection('home')}
							class="text-gray-300 hover:text-primary transition-colors duration-200"
						>
							Home
						</button>
					</li>
					<li>
						<button 
							onclick={() => scrollToSection('about')}
							class="text-gray-300 hover:text-primary transition-colors duration-200"
						>
							About
						</button>
					</li>
					<li>
						<button 
							onclick={() => scrollToSection('skills')}
							class="text-gray-300 hover:text-primary transition-colors duration-200"
						>
							Skills
						</button>
					</li>
					<li>
						<button 
							onclick={() => scrollToSection('projects')}
							class="text-gray-300 hover:text-primary transition-colors duration-200"
						>
							Projects
						</button>
					</li>
					<li>
						<button 
							onclick={() => scrollToSection('contact')}
							class="text-gray-300 hover:text-primary transition-colors duration-200"
						>
							Contact
						</button>
					</li>
				</ul>
			</div>

			<!-- Contact Info -->
			<div class="space-y-4">
				<h3 class="text-xl font-bold">Contact Info</h3>
				<div class="space-y-2 text-gray-300">
					<p>📧 kokoybaldofordawin@gmail.com</p>
					<p>📱 +1 (555) 123-4567</p>
					<p>📍 Bogo City, Cebu, Philippines</p>
				</div>
			</div>
		</div>

		<!-- Bottom Bar -->
		<div class="border-t border-gray-800 mt-8 pt-8 text-center">
			<p class="text-gray-400 flex items-center justify-center space-x-1">
				<span>© {new Date().getFullYear()} Niño Abao. Made with</span>
				<Heart class="h-4 w-4 text-red-500 fill-current" />
				<span>and lots of milk</span>
			</p>
		</div>
	</div>
</footer>