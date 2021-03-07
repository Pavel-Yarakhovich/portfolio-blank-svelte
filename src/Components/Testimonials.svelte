<script>
  export let data;
</script>

<section id="testimonials">
  <div class="text-container">
    <div class="row">
      <div class="two columns header-col">
        <h1><span>Client Testimonials</span></h1>
      </div>

      <div class="ten columns flex-container">
        <ul class="slides">
          {#each data.testimonials as testimonials}
            <li key={testimonials.user}>
              <blockquote>
                <p>{testimonials.text}</p>
                <cite>{testimonials.user}</cite>
              </blockquote>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</section>
