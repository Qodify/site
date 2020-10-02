<script>
  import { onMount } from "svelte";
  import { navigate } from "svelte-routing";
  import { fly } from "svelte/transition";
  import { storedPost, timeout } from "../components/stores";
  import marked from 'marked'

  const apiBaseUrl = "https://qs-api.azurewebsites.net/api";

  onMount(async () => {
    if ($storedPost.length < 1 || $timeout == true) {
      const res = await fetch(apiBaseUrl + "/blogposts");
      $storedPost = await res.json();
    }
  });

  // setTimeout(() => {
  //   $timeout=true;
  //   console.log("refetch");
  // }, 10 * 1000);

  function redirectTo(post) {
    navigate(`blog/${post.id}`, { replace: false });
  }
  const options = { year: "numeric", month: "long", day: "numeric" };
</script>

<style>
  .card-hover:hover {
    background-color: whitesmoke;
  }
</style>

<div class="container-md mt-5 mx-auto">
  {#each $storedPost as post}
    <div
      in:fly={{ y: 200, duration: 400 }}
      class="col-12 mx-auto mb-4"
      on:click={() => {
        redirectTo(post);
      }}>
      <div class="card card-hover">
        <div class="card-body">
          <h5 class="card-title">{@html marked(post.title)}</h5>
          <h6 class="card-subtitle mb-2 text-muted">
            {new Date(post.timestamp).toLocaleDateString(undefined, options)}
          </h6>
          <span style="white-space: pre-line, white-space: pre-wrap" class="card-text">{@html marked(post.heading)}</span>
        </div>
      </div>
    </div>
  {/each}
</div>
