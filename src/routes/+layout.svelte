<script lang="ts">
    import "../app.css";
    import Navbar from "$lib/components/navbar/Navbar.svelte";
    import Footer from "$lib/components/Footer.svelte";
</script>

<Navbar/>
<main class="flex flex-col mx-2 min-h-screen">
    <slot/>
</main>
<Footer />
