<script>
  import NavbarBoot from "./layout/Navbar.svelte";
  import Footer from "./layout/Footer.svelte";
  import { Router, Route } from "svelte-routing";
  import Home from "./pages/Home.svelte";
  import Blog from "./pages/Blog.svelte";

</script>

<svelte:head>
  <meta
    name="viewport"
    content="width=device-width, initial-scale=1, shrink-to-fit=no" />
  <style>
    body {
      height: 97vh;
    }
  </style>
</svelte:head>

<body>
  <div class="alert alert-warning" role="alert">
    This site is not yet finished, don't expect to find a lot here.
  </div>
<Router>
  <NavbarBoot />
  <Route path="/" component={Home} />
  <Route path="blog" component={Blog} />

</Router>
</body>
<Footer/>

