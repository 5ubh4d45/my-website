<script lang="ts">
    import IconMoonAnim from "$lib/icons/IconMoonAnim.svelte"
    import IconSunAnim from "$lib/icons/IconSunAnim.svelte"
    
    import {DARK_MODE, DEFAULT_THEME, DEFAULT_THEME_DATA} from "./Theme-Data"
    import {onMount} from "svelte";

    let themeName = DEFAULT_THEME;
    let darkmode = DARK_MODE;
    
    function resolveTheme(isDarkMode : boolean) {
        themeName = isDarkMode ? DEFAULT_THEME_DATA.dark : DEFAULT_THEME_DATA.light

        // console.log("Current navbar: " + navbar + " DarkMode: " + isDarkMode);
        document.documentElement.setAttribute('data-theme', themeName);
    }
    
    function handleToggle(e: Event) {
        const checkBox = e.target as HTMLInputElement;
        darkmode = checkBox.checked;
        
        resolveTheme(darkmode);
    }
    
    onMount(() => resolveTheme(true));
    
</script>

<label for="theme-toggle">
  {#if darkmode}
    <span><IconMoonAnim class="w-8 h-8 pr-1"/></span>
  {:else}
    <span><IconSunAnim class="w-9 h-9 pr-1"/></span>
  {/if}
  <!--          <span class="text-base font-semibold">Prose</span>-->
  <input
      id="theme-toggle"
      type="checkbox"
      on:change={handleToggle}
      bind:checked={darkmode}
      class="toggle toggle-accent toggle-md justify-center"
  />
</label>