<script lang="ts">
    import type { Snippet } from "svelte";
    const { data , children } : { data : { title? : string }, children : Snippet } = $props();
</script>
<header class="manage-header flex items-center gap-x-2 px-7 pt-10 pb-8">
    <nav class="prev px-2">
	<a href=".." class="prev-button text-2xl text-yellow-600 hover:text-yellow-900 hover:underline underline-offset-2">↩ Home</a>
    </nav>
    <h1 class="text-4xl font-semibold ml-4 tracking-tight">{data?.title ?? ""}</h1>
</header>
<section class="manage-section flex flex-row flex-wrap gap-[2vmin] px-8 pt-4">
    {@render children()}
</section>
