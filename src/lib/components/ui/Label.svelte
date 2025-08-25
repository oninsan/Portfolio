<script>
	export let htmlFor = '';
	export let className = '';

	$: classes = [
		'text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70',
		className
	].filter(Boolean).join(' ');
</script>

<label for={htmlFor} class={classes}>
	<slot />
</label>