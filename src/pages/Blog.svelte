<script>
  let posts = [
    {
      id: "J---aiyznGQ",
      title: "new trick with bootstrap and svelte",
      subtitle: "",
      timestamp: "",
      body:
        "Some quick example text to build on the card title and make up the bulk of the card's content.",
    },
    {
      id: "J---aiyznGQ",
      title: "new trick with bootstrap and svelte",
      subtitle: "",
      timestamp: "",
      body:
        "Some quick example text to build on the card title and make up the bulk of the card's content.",
    },
    {
      id: "J---aiyznGQ",
      title: "new trick with bootstrap and svelte",
      subtitle: "",
      timestamp: "",
      body:
        "Some quick example text to build on the card title and make up the bulk of the card's content.",
    },
  ];
</script>

<style>
  .card-hover:hover {
    background-color: whitesmoke;
  }
</style>

<!--<script>
    import { Router, Link, Route } from "svelte-routing";
    // import BlogPost from './Blogpost.svelte'
</script>-->

<!-- <Route path="blog/:id" let:params>
  <BlogPost id="{params.id}" />
</Route> -->
<div class="container mt-5">
  {#each posts as { id, title, body }}
    <div class="col-8 mx-auto mb-4" on:click={() => alert(id)}>
      <div class="card card-hover">
        <div class="card-body">
          <h5 class="card-title">{title}</h5>
          <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
          <p class="card-text">{body}</p>
        </div>
      </div>
    </div>
  {/each}
</div>
