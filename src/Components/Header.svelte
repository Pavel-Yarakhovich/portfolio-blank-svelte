<script>
  export let data;
  const links = [
    "home",
    "about",
    "resume",
    "portfolio",
    "testimonials",
    "contact",
  ];
  let activeLink = "home";
  function scrollTo(id) {
    activeLink = id;
    document
      .getElementById(id)
      .scrollIntoView({ behavior: "smooth", block: "start" });
  }
</script>

<style>
  #nav {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  #nav > li {
    display: flex;
    align-items: center;
    padding: 0.5rem 1.5rem;
  }
  #nav > li:hover {
    cursor: pointer;
  }
  .current > span {
    color: orange;
  }
</style>

<header id="home">
  <nav id="nav-wrap">
    <img src="/assets/logo.png" alt="Logo"/>
    <ul id="nav" class="nav">
      {#each links as link}
        <li class={activeLink === link ? 'current' : ''}>
          <span on:click={() => scrollTo(link)}> {link.toUpperCase()} </span>
        </li>
      {/each}
    </ul>
  </nav>

  <div class="row banner">
    <div class="banner-text">
      <h1 class="responsive-headline">I'm {data.name}</h1>
      <h3>
        Based in
        {data.address.city}.
        <span>{data.occupation}</span>.
        {data.description}.
      </h3>
      <hr />
      <ul class="social">
        {#each data.social as network}
          <li key={network.name}>
            <a href={network.url}> <i class={network.className} /> </a>
          </li>
        {/each}
      </ul>
    </div>
  </div>

  <p class="scrolldown">
    <a class="smoothscroll" href="#about"> <i class="icon-down-circle" /> </a>
  </p>
</header>
