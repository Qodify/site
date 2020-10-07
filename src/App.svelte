<script>
  import Navbar from "./layout/Navbar.svelte";
  import Footer from "./layout/Footer.svelte";
  import { Router, Route } from "svelte-routing";
  import Home from "./pages/Home.svelte";
  import Blog from "./pages/Blog.svelte";
  import BlogPost from "./pages/BlogPost.svelte";
  import NavbarController from "./layout/NavbarController.svelte";
</script>

<svelte:head>
  <meta
    name="viewport"
    content="width=device-width, initial-scale=1, shrink-to-fit=no" />
  <style>
    body {
      margin: 0;
      padding: 0;
    }
    .alert {
      background-color: #fff3cd;
      padding: 5px 5px;
      border-style: solid;
      border-width:1px;
      border-color: #FFEEBA;
      color: #856404;
      font-size: small;
      
    }
  </style>
</svelte:head>

<body>
  <!-- <div class="alert">Site under construction.</div> -->
  <Router>
    <NavbarController />
    <Route style="display:block" path="/" component={Home} />
    <Route path="blog" component={Blog} />
    <Route path="blog/:id" component={BlogPost} />
    <Route path="contact" component={Home} />
  </Router>
</body>
<!-- <Footer /> -->
