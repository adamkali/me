<script lang="ts">
	export let href: string;
	export let twColor: string;
	export let icon: any | null;
	export let show: boolean;
	export let title: string;
</script>

<li class="flex flex-row justify-center">
	{#if icon}
		<a class="grid w-1/4 grid-cols-1" {href} target="_blank" rel="noreferrer">
			<span class={`${twColor} hover:animate-spin`}>
				<svelte:component this={icon} />
			</span>
		</a>
	{/if}
	{#if show}
		<div class="flex w-1/3 flex-col">
			<b>{title}</b>
		</div>
		<div class="text-lg"><slot /></div>
	{/if}
</li>
