<script lang="ts">
  import Toaster, { showToast } from './lib/Toaster.svelte';

</script>
<Toaster>
<main>

  <hgroup>
    <h1>Project A</h1>
    <h2>mobile version</h2>
  </hgroup>

  
  <button onclick={() => {
    navigator.geolocation.getCurrentPosition(
      (position) => {
        const { latitude, longitude } = position.coords;
        // Send these coordinates to your backend
        showToast(`latitude: ${latitude} | longitude: ${longitude}`, {duration: 50000})
      },
      (error) => {
        showToast("Error fetching location", {type: 'error'})
        console.error(error)
      },
    );
  }}>Use my Location</button>
</main>

</Toaster>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
