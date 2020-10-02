<script>
  import Navbar from "./layout/Navbar.svelte";
  import Footer from "./layout/Footer.svelte";
  import { Router, Route } from "svelte-routing";
  import Home from "./pages/Home.svelte";
  import Blog from "./pages/Blog.svelte";
  import BlogPost from "./pages/BlogPost.svelte";

</script>

<svelte:head>
  <meta
    name="viewport"
    content="width=device-width, initial-scale=1, shrink-to-fit=no" />
  <style>

  </style>
</svelte:head>

<body>
  <div class="alert alert-warning mb-0" role="alert">
    This site is not yet finished, don't expect to find a lot here.
  </div>
<Router>
  <Navbar/>
  <Route path="/" component={Home} />
  <Route path="blog" component={Blog} />
  <Route path="blog/:id" component={BlogPost} />

</Router>
</body>
<Footer/>

