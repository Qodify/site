<script>
  import { onMount } from "svelte";
  import { navigate } from "svelte-routing";
  import { fly } from "svelte/transition";
  import { storedPost, timeout } from "../components/stores";
  import marked from "marked";

  const apiBaseUrl = "https://qs-api.azurewebsites.net/api";

  let postcheck = $storedPost;

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
</script>

<style>
  .card-hover:hover {
    background-color: #fbfbfb;
  }

  .pers {
    padding: 0px 16px 0px 16px;
    margin: 100px 0;
    border-style: solid;
    border-width: 1px;
    border-color: #dfdfdf;
    border-radius: 2px;
    box-shadow: 1px 1px 2px #ddd;
    cursor: pointer;
  }

  .margin {
    margin: 16px 0 0 0;
    margin-left: 1.1em;
    margin-right: 1.1em;
  }

  .title {
    font-size: larger;
    font-weight: 600;
  }

  /* .center {
    margin: auto;
    text-align: center;
    margin-top:16px
  } */



  [class*="container"] {
    margin-top: 0;
    font-size: small;
  }

  /* 600px > */
  @media screen and (min-width: 600px) {
    .container {
      margin: auto;
      max-width: 600px;
      font-size: unset;
    }
  }

  /* 992px > */
  @media screen and (min-width: 992px) {
    .container {
      margin: auto;
      max-width: 800px;
      font-size: unset;
    }
  }
</style>

<div>
  {#if postcheck}
    <div class="">
      {#each $storedPost as post}
        <div class="margin">
          <div
            in:fly={{ y: 200, duration: 400 }}
            class="pers container card-hover"
            on:click={() => {
              redirectTo(post);
            }}>
            <div class="title">
              {@html marked(post.title)}
            </div>
            <h5>
              {new Date(post.timestamp).toLocaleDateString(undefined, {
                year: 'numeric',
                month: 'long',
                day: 'numeric',
              })}
            </h5>
            <span
              style="white-space: pre-line, white-space: pre-wrap"
              class="">{@html marked(post.heading)}</span>
          </div>
        </div>
      {/each}
    </div>
  {/if}
</div>
