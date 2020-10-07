<script>
  import { Link } from "svelte-routing";
  import { fly } from "svelte/transition";

  let current = "about";
</script>

<style>
  ul {
    list-style-type: none;
    display: inline;
    padding: 0;
  }
  li {
    display: inline-block;
  }

  img {
    vertical-align: middle;
    margin: auto;
    opacity: 0.75;
    padding: 0px 11.5px;
  }
  img:hover {
    opacity: 1;
  }

  :global([ref="link"]) {
    display: inline-block;
    padding: 18px 24px;
    text-decoration: none;
    color: grey;
    font-size: 16px;
  }

  .selected {
    background-color: #fef7ea;
    border-bottom: 3px solid #ddd5c5;
    outline: 0;
  }

  .container {
    background-color: #f8f9fa;
  }
</style>

<div class="container" in:fly={{ x: -200, duration: 400 }}>
  <ul>
    <li>
      <div on:click={() => (current = 'about')}>
        <Link to="/">
          <img
            src="../favicon.svg"
            width="40px"
            height="40px"
            alt="Logo"
            loading="lazy" />
        </Link>
      </div>
    </li>
    <li
      class={current === 'about' ? 'selected' : ''}
      on:click={() => (current = 'about')}>
      <Link ref="link" to="/">About me</Link>
    </li>
    <li
      class={current === 'blog' ? 'selected' : ''}
      on:click={() => (current = 'blog')}>
      <Link ref="link" to="/blog">Blog</Link>
    </li>
    <li />
  </ul>
</div>
