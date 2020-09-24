<script>
  import Navbar from "./layout/Navbar.svelte";
  import NavbarFancy from "./layout/NavbarFancy.svelte";
  import NavbarBoot from "./layout/NavbarBoot.svelte";
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
<Router>
  <NavbarBoot />
  <Route path="/" component={Home} />
  <Route path="blog" component={Blog} />
</Router>
</body>
<Footer/>

