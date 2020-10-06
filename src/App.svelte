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
    body{
      height:100vh
    }
  </style>
</svelte:head>

<body class="">

<Router>
  <Navbar/>
  <Route path="/" component={Home} />
  <Route path="blog" component={Blog} />
  <Route path="blog/:id" component={BlogPost} />

</Router>
</body>
<Footer/>

