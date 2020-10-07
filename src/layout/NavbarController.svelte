<script>
  import MediaQuery from "svelte-media-query";
  import Navbar from "./Navbar.svelte"
  import NavbarPhone from "./NavbarPhone.svelte"
</script>
 
<MediaQuery query="(max-width: 400px)" let:matches>
	{#if matches}
	<NavbarPhone/>
  {:else}
  <Navbar/>
  {/if}
</MediaQuery>