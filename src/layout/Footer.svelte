<script>
</script>

<style>
  .footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100vw;
    background-color: #666;
    font-size: 0.71em;
    color: #aaa;
    display: inline;
  }


  div {
    display: inline-block;
    vertical-align: middle;
  }
  .linkedin {
    vertical-align: middle;
    opacity: 0.8;
    margin: 0 2em 0 0;
    border-radius: 1px;
  }
  .linkedin:hover {
    -webkit-filter: invert(100%); /* safari 6.0 - 9.0 */
    filter: invert(100%);
    background-color: #ff8c4d;
    opacity: 1;
  }
  .floatleft {
    float: right;
    height: 100%;
  }
</style>

<footer class="footer">
  <div class="©">©</div>
  <div>Quinten Spillemaeckers</div>
  <!-- <div class="floatleft">
    <img
      class="linkedin"
      src="../linkedin.svg"
      alt=""
      width="24px"
      on:click={() => {
        window.location = 'https://www.linkedin.com/in/quinten-spillemaeckers-it/';
      }} />
  </div>
  <div class="floatleft">
    <img
      class="linkedin"
      src="../facebook.svg"
      alt=""
      width="24px"
      on:click={() => {
        window.location = 'https://www.linkedin.com/in/quinten-spillemaeckers-it/';
      }} />
  </div> -->
</footer>
