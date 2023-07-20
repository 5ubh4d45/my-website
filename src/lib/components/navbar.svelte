<script lang="ts">
    // import IconSpinner from "$lib/icons/spinner-3dBounce.svelte";
    // import IconAccount from "$lib/icons/account.svelte";
    import IconSunAnim from "$lib/icons/sun-anim.svelte"
    import IconMoonAnim from "$lib/icons/moon-anim.svelte"
    
    let theme = 'night';
    let isDarkMode = true;

    let themeList = [
        {name: "light", mode: "light"},
        {name: "dark", mode: "dark"},
        {name: "night", mode: "dark"},
        {name: "winter", mode: "light"},
        {name: "forest", mode: "dark"},
        {name: "pastel", mode: "light"}
    ]

    /**
     * Set the theme
     * @param {{ target: Event; }} event
     * @returns {void} void
     */
    function set_theme(event: Event) {
        const select = event.target as HTMLSelectElement;
        theme = select.value;
        const themeMode = themeList.find((item) => item.name === theme)?.mode;
				isDarkMode = themeMode !== 'light';
        
        // console.log("Current theme: " + theme + " Theme Mode: " + themeMode + " DarkMode: " + isDarkMode);
        document.documentElement.setAttribute('data-theme', theme);
    }

</script>


<div class="navbar bg-base-100 px-2 mb-3 shadow-md rounded-lg">
  <div class="py-4 px-4 navbar-start flex-1">
    <a href="/" class=" text-3xl font-bold">
      <span class="text-primary">Svelte</span>Kit
    </a>
  </div>
  <div class="flex navbar-end">
    <ul class="menu menu-horizontal items-center">
      <!--      <li>-->
      <!--        <label for="prose-toggle">-->
      <!--          <IconSpinner/>-->
      <!--          <IconSpinner class="w-6 h-6 text-primary"/>-->
      <!--          <IconAccount class="w-6 h-6 text-secondary"/>-->
      <!--          <span class="text-base font-semibold">Prose</span>-->
      <!--          <input-->
      <!--              id="prose-toggle"-->
      <!--              type="checkbox"-->
      <!--              on:change={handle_toggle}-->
      <!--              class="toggle toggle-accent toggle-md justify-center"-->
      <!--          />-->
      <!--        </label>-->
      <!--      </li>-->
      <li>
        <label for="theme-selector">
          {#if isDarkMode}
            <span><IconMoonAnim class="w-8 h-8 pr-1" /></span>
          {:else}
            <span><IconSunAnim class="w-9 h-9 pr-1"/></span>
          {/if}
          <select
              id="theme-selector"
              class="select select-primary select-ghost w-full max-w-xs"
              on:change={set_theme}
          >
            <option disabled selected>Select Theme</option>
            <option value="dark">Dark</option>
            <option value="night">Night</option>
            <option value="light">Light</option>
            <option value="winter">Winter</option>
            <option value="forest">Forest</option>
            <option value="pastel">Pastel</option>
          </select>
        </label>
      
      </li>
    </ul>
  </div>
</div>
