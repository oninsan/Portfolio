<script>
	export let placeholder = '';
	export let value = '';
	export let id = '';
	export let className = '';
	export let rows = 3;
	export let required = false;

	$: classes = [
		'flex min-h-[80px] w-full rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50',
		className
	].filter(Boolean).join(' ');
</script>

<textarea {placeholder} {id} {rows} {required} bind:value class={classes} {...$$restProps}></textarea>