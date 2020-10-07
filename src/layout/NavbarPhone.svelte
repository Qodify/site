<script>
  import { Link } from "svelte-routing";
  import { fly } from "svelte/transition";

  let visible;
</script>

<style>
  .links {
    z-index: 1;
    position: absolute;
    /* opacity: 0.97; */
  }
  .linkitem1 {
    top: 0;
    width: 100vw;
    background-color: lightgrey;
    border-bottom: 1px ridge white;
  }
  .linkitem2 {
    top: 61px;
    width: 100vw;
    background-color: lightgrey;
    box-shadow: 0px 5px 8px #aaa;
  }

  ul {
    list-style-type: none;
    padding: 0;
    display: inline;
  }


  img {
    cursor: pointer;
    vertical-align: middle;
    opacity: 0.75;
    padding: 15.5px 15.5px;
  }
  .container {
    background-color: #f8f9fa;
  }
  .overlay{
    position: relative;

  }
</style>

<div class="container" in:fly={{ x: -200, duration: 400 }}>
  <ul>
    <li>
      <img
        on:click={() => (visible = !visible)}
        src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b2/Hamburger_icon.svg/1024px-Hamburger_icon.svg.png"
        alt="dropdown menu"
        width="32px"
        height="32px"
        loading="lazy" />
    </li>
    {#if visible}
    <div class="overlay">
      <div class="linkitem1 links" transition:fly={{ x: -200, duration: 200 }}>
        <Link on:click={() => (visible = !visible)} ref="link" to="/">About me</Link>
      </div>
      <!-- <div class="divider" transition:fly={{ x: -200, duration: 400 }}/> -->
      <div  class="linkitem2 links" transition:fly={{ x: -200, duration: 200 }}>
        <Link on:click={() => (visible = !visible)} ref="link" to="/blog">Blog</Link>
      </div>
    </div>
    {/if}
  </ul>
</div>
