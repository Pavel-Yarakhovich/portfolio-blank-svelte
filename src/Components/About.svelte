<script>
  export let data;
  $: profilepic = `/assets/${data.image}`;
</script>

<section id="about">
  <div class="row">
    <div class="three columns">
      <img class="profile-pic" src={profilepic} alt="Sonny's Profile Pic" />
    </div>
    <div class="nine columns main-col">
      <h2>About Me</h2>

      <p>
        {@html data.bio}
      </p>
      <div class="row">
        <div class="columns contact-details">
          <h2>Contact Details</h2>
          <p class="address">
            <span>{data.name}</span>
            <br />
            <span>
              {data.address.street}
              <br />
              {data.address.city}
              {data.address.state},
              {data.address.zip}
            </span>
            <br />
            <span>{data.phone}</span>
            <br />
            <span>{data.email}</span>
          </p>
        </div>
        <div class="columns download">
          <p>
            <a href={data.resumeDownload} class="button">
              <i class="fa fa-download" />Download Resume
            </a>
          </p>
        </div>
      </div>
    </div>
  </div>
</section>
