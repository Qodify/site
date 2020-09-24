<script>
  import { Link } from "svelte-routing";
</script>

<style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333;
  }

  li {
    float: left;
  }

 nav > ul > li > :global(*) {
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
  }

  nav > ul > li > :global(*):hover {
    background-color: #111;
  }

</style>

<nav>
  <ul>
    <li>
      <Link to="/">About me</Link>
    </li>
    <li>
      <Link to="blog">Blog</Link>
    </li>
  </ul>
</nav>
