<script lang="ts">
    import TopNav from "$lib/components/TopNav.svelte";
    import "./layout.css";
    let { children } = $props();
</script>

<TopNav />
{@render children()}
