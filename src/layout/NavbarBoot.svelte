<script>
  import { Link } from "svelte-routing";

  let current = "1";
</script>

<style>
  	.active {
		background-color: #ff3e00;
		color: red;
	}
</style>

<nav class="navbar navbar-expand navbar-light bg-light">
  <div>
    <Link BSclass="navbar-brand" to="/">
      <img
        src="favicon.png"
        width="30"
        height="30"
        class="d-inline-block align-top"
        alt=""
        loading="lazy" />
    </Link>
  </div>

  <ul class="navbar-nav mr-auto">
    <li
      class="nav-item"
      class:active={current === 1}
      on:click={() => (current = '1')}>
      <Link BSclass="nav-link" to="/">About me</Link>
    </li>
    <li class="nav-item">
      <Link BSclass="nav-link" to="/blog">Blog</Link>
    </li>
    <li class="nav-item">
      <Link BSclass="nav-link" to="/contact">Contact</Link>
    </li>
  </ul>
</nav>
