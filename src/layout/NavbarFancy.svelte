<script>
  import { Link } from "svelte-routing";

  export let menu = 1;
</script>

<style>
  nav.primary-navigation {
    margin: 0 auto;
    display: block;
    padding: 2em 0 0 0;
    text-align: center;
    font-size: 16px;
  }
  nav.primary-navigation ul li {
    list-style: none;
    margin: 0 auto;
    border-left: 2px solid #3ca0e7;
    display: inline-block;
    padding: 0 1.5em;
    position: relative;
    text-decoration: none;
    text-align: center;
    font-family: arvo;
  }
  nav.primary-navigation li :global(*) {
    color: black;
  }
  nav.primary-navigation li :global(*):hover {
    color: #3ca0e7;
  }
  nav.primary-navigation li:hover {
    cursor: pointer;
  }
  nav.primary-navigation ul li ul {
    visibility: hidden;
    opacity: 0;
    position: absolute;
    padding-left: 0;
    left: 0;
    display: none;
    background: white;
  }
  nav.primary-navigation ul li ul:hover {
    visibility: visible;
    opacity: 1;
    display: block;
    min-width: 250px;
    text-align: left;
    padding-top: 20px;
    box-shadow: 0px 3px 5px -1px #ccc;
  }
  nav.primary-navigation ul li ul li {
    clear: both;
    width: 100%;
    text-align: left;
    margin-bottom: 20px;
    border-style: none;
  }
  nav.primary-navigation ul li ul li :global(*):hover {
    padding-left: 10px;
    border-left: 2px solid #3ca0e7;
    transition: all 0.3s ease;
  }
  a {
    text-decoration: none;
  }
  nav > ul > li :global(*)a:hover {
    color: #3ca0e7;
  }
  ul li ul li :global(*) {
    transition: all 0.5s ease;
  }
</style>

<link
  href="https://fonts.googleapis.com/css?family=Arvo&display=swap"
  rel="stylesheet" />

<nav role="navigation" class="primary-navigation">
  <ul>
    <li
      style="color: {menu === 1 ? 'blue' : 'red'}"
      on:click|preventDefault={() => (menu = 1)}>
      <Link to="/">Home</Link>
    </li>
    <li on:click|preventDefault={() => (menu = 2)}>
      <Link to="/blog">blog</Link>
    </li>
  </ul>
</nav>
<div class="text-center">
  {#if menu === 1}
    <h1>Home</h1>
  {:else if menu === 2}
    <h1>Blog</h1>
  {/if}
</div>
