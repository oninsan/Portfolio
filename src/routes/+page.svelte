<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import About from '$lib/components/pages/About.svelte';
	import Skills from '$lib/components/Skills.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import Contact from '$lib/components/Contact.svelte';
	import Footer from '$lib/components/Footer.svelte';
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