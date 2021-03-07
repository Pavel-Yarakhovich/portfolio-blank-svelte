<script>
  export let data;
</script>

<footer>
  <div class="row">
    <div class="twelve columns">
      <ul class="social-links">
        {#each data.social as network}
          <li key={network.name}>
            <a href={network.url}> <i class={network.class} /> </a>
          </li>
        {/each}
      </ul>

      <ul class="copyright">
        <li>
          Made by{' '}
          <a title="Pavel Yarakhovich" href="https://www.linkedin.com/feed/"> Pavel Yarakhovich </a>
        </li>
      </ul>
    </div>
    <div id="go-top">
      <a class="smoothscroll" title="Back to Top" href="#home">
        <i class="icon-up-open" />
      </a>
    </div>
  </div>
</footer>
