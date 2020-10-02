<script>
  import { Link } from "svelte-routing";
</script>

<nav class="navbar navbar-expand navbar-light bg-light">
  <div>
    <Link BSclass="navbar-brand" to="/">
      <img
        src="../favicon.svg"
        width="30"
        height="30"
        class="d-inline-block align-top"
        alt=""
        loading="lazy" />
    </Link>
  </div>

  <ul class="navbar-nav mr-auto">
    <li
      class="nav-item px-3">
      <Link BSclass="nav-link" to="/">About me</Link>
    </li>
    <li class="nav-item px-3">
      <Link BSclass="nav-link" to="/blog">Blog</Link>
    </li>
    <li class="nav-item px-3">
      <Link BSclass="nav-link" to="/contact">Contact</Link>
    </li>
  </ul>
</nav>
