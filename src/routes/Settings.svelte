<script>
  import { fade } from "svelte/transition";
  import { openDir } from "$lib/commands";
  import { appDir } from "@tauri-apps/api/path";

  // NOTE: added this to shut up the console warning
  export let location;
</script>

<!-- TODO - STYLE THIS PAGE -->
<div class="flex-center" in:fade>
  <h1>Settings</h1>
  {#await appDir() then directory}
    <button class="btn" on:click={() => openDir(directory)}>
      <i class="bi bi-folder" />
      Open App Directory</button
    >
  {/await}
</div>
