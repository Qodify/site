<script>
</script>

<style>
  .pers {
    text-align: justify;
  }

  [class*="container"] {
    padding: 0 1.1em;
  }

  /* 600px > */
  @media screen and (min-width: 600px) {
    .container {
      margin: auto;
      max-width: 600px;
    }
  }

  /* 992px > */
  @media screen and (min-width: 992px) {
    .container {
      margin: auto;
      max-width: 800px;
    }
  }

  .grid-container {
    display: grid;
    grid-template-columns: auto 1px auto;
    justify-content: center;
    column-gap: 1em;
    margin-bottom: 2em;
  }
  img {
    border-radius: 50px;
    -webkit-filter: grayscale(100%); /* Safari 6.0 - 9.0 */
    filter: grayscale(100%);
  }
  img:hover {
    -webkit-filter: grayscale(0%); /* Safari 6.0 - 9.0 */
    filter: grayscale(0%);
  }

  .divider {
    background-color: rgb(189, 183, 109);
  }
  h2 {
    margin-top: 2em;
  }

  .desc{
    text-align: center;
    font-size: small;
    color:rgb(189, 183, 109)
  }
</style>

<div class="pers container">
  <h2>Hi!</h2>
  <p>
    Welcome to one of my creative outlets. This site is developed and maintained
    by me. Though right now it's under heavy construction. Not only does this
    site function as a creative outlet, it's also a showcase of my digital
    talents. I know, I know. Everyone and their dog has a website. but not
    always without "wordpress" in the url, or developed with a modern framework
    like Svelte, which loads in my blogposts by an api written in ASP.NET Core
    (with Continuous Deployment thanks to Github Actions) which retrieves them
    from a remote Azure database...
  </p>
  <p>You get the point.</p>
  <p>
    So you will probably find IT related posts here, but also other topics. That
    is, if I find I'm finally done writing the website.
  </p>
  <br />
  <p class="desc">visit my github or LinkedIn</p>
  <div class="grid-container">
    <div>
      <a href="https://github.com/Qodify">
        <img src="../githublogo.jpg" alt="link to my Github page" width="60px" />
      </a>
    </div>
    <div class="divider" />
    <div>
      <a href="https://www.linkedin.com/in/quinten-spillemaeckers-it/">
        <img src="../linkedinlogo.png" alt="link to my Linkedin page" width="60px" />
      </a>
    </div>
  </div>
</div>
