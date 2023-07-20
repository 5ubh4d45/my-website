<script lang="ts">
    import "../app.css";
    import Navbar from "$lib/components/navbar.svelte";
</script>

<div class="flex flex-col mx-2">
    <Navbar/>
    <slot/>
</div>