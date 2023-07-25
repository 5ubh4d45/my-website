<script>
    import IconMenuAnim from "$lib/icons/IconMenuAnim.svelte";
</script>

<div class="flex lg:hidden">
  <div class="dropdown">
    <button tabindex="0" class="btn btn-ghost btn-circle">
      <IconMenuAnim class="w-6 h-6"></IconMenuAnim>
    </button>
    <ul class="menu menu-sm dropdown-content mt-3 z-[1] p-2 shadow bg-base-100 rounded-box w-52">
      <li><a href="/">Homepage</a></li>
      <li><a href="/">Projects</a></li>
      <li><a href="/">About</a></li>
      <li><a href="/" class="text-secondary font-semibold">Contact Me!</a></li>
    </ul>
  </div>
</div>

<div class="hidden lg:flex">
  <ul class="menu menu-horizontal px-1">
    <li><a href="/">Homepage</a></li>
    <li>
      <details>
        <summary>Projects</summary>
        <ul class="p-2">
          <li><a href="/">Project 1</a></li>
          <li><a  href="/">Project 2</a></li>
        </ul>
      </details>
    </li>
    <li><a href="/">About</a></li>
    <li><a href="/" class="text-secondary font-semibold">Contact Me!</a></li>
  </ul>
</div>