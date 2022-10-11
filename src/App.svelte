<script lang="ts">
  import Header from './lib/Header.svelte';
  import Cars from './lib/Cars.svelte';
</script>

<div class="h-full w-full bg-[#f4e3b7] relative">
  <Header />

  <div
    class=" bg-blue-500 h-full w-full flex flex-col justify-between items-center"
  >
    <div class="mt-20">
      <!-- contain car stuff and main part of page -->
      <Cars />
    </div>
  </div>
</div>
