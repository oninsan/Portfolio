<script lang="ts">
	import Hero from '$lib/components/pages/Hero.svelte';
	import About from '$lib/components/pages/About.svelte';
	import Skills from '$lib/components/pages/Skills.svelte';
	import Projects from '$lib/components/pages/Projects.svelte';
	import Contact from '$lib/components/pages/Contact.svelte';
	import Footer from '$lib/components/pages/Footer.svelte';
</script>

<svelte:head>
	<title>Portfolio - Web Developer</title>
	<meta name="description" content="Professional web developer portfolio showcasing skills, projects, and experience in modern web development." />
</svelte:head>

<div class="min-h-screen">
	<!-- <Header /> -->
	<main>
		<Hero />
		<About />
		<Skills />
		<Projects />
		<Contact />
	</main>
	<!-- <Footer /> -->
</div>