<script lang="ts">

import ThemeToggle from "$lib/components/navbar/ThemeToggle.svelte";
import NavItemList from "$lib/components/navbar/NavItemList.svelte";
</script>


<div class="navbar bg-base-100 px-4 mb-3 shadow-md rounded-lg">
  <div class="py-4 px-4 navbar-start flex-1">
    <a href="/static" class=" text-3xl font-bold">
      <span class="text-primary">iXALE</span>.dev
    </a>
  </div>
  
  <div class="flex navbar-end">
    <NavItemList />
    <ul class="menu menu-horizontal items-center">
      <li>
        <ThemeToggle />
      </li>
    </ul>
  </div>
</div>


