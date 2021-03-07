<script>
  export let data;
</script>

<section id="portfolio">
  <div class="row">
    <div class="twelve columns collapsed">
      <h1>Check Out Some of My Works.</h1>

      <div id="portfolio-wrapper" class="bgrid-quarters s-bgrid-thirds cf">
        {#each data.projects as projects}
          <div key={projects.title} class="columns portfolio-item">
            <div class="item-wrap">
              <a href={projects.url} title={projects.title}>
                <img alt={projects.title} src={"/assets/portfolio/" + projects.image} />
                <div class="overlay">
                  <div class="portfolio-item-meta">
                    <h5>{projects.title}</h5>
                    <p>{projects.category}</p>
                  </div>
                </div>
                <div class="link-icon"><i class="fa fa-link" /></div>
              </a>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
