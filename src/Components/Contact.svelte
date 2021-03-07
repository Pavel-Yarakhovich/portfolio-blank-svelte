<script>
  export let data;
  let name = "",
    email = "",
    subject = "",
    message = "";

  function submitForm() {
    window.open(
      `mailto:${data.email}?subject=${encodeURIComponent(
        subject
      )}&body=${encodeURIComponent(name)} (${encodeURIComponent(
        email
      )}): ${encodeURIComponent(message)}`
    );
  };
</script>

<section id="contact">
  <div class="row section-head">
    <div class="two columns header-col">
      <h1><span>Get In Touch.</span></h1>
    </div>

    <div class="ten columns">
      <p class="lead">{data.contactmessage}</p>
    </div>
  </div>

  <div class="row">
    <div class="eight columns">
      <form on:submit={submitForm}>
        <fieldset>
          <div>
            <label for="contactName">
              Name
              <span class="required">*</span>
            </label>
            <input type="text" size="35" bind:value={name} />
          </div>

          <div>
            <label for="contactEmail">
              Email
              <span class="required">*</span>
            </label>
            <input type="text" size="35" bind:value={email} />
          </div>

          <div>
            <label for="contactSubject">Subject</label>
            <input type="text" size="35" bind:value={subject} />
          </div>

          <div>
            <label for="contactMessage">
              Message
              <span class="required">*</span>
            </label>
            <textarea cols="50" rows="15" bind:value={message} />
          </div>

          <div>
            <button on:click={submitForm} type="submit" class="submit">
              Submit
            </button>
          </div>
        </fieldset>
      </form>

      <div id="message-warning">Error boy</div>
      <div id="message-success">
        <i class="fa fa-check" />Your message was sent, thank you!
        <br />
      </div>
    </div>

    <aside class="four columns footer-widgets">
      <div class="widget widget_contact">
        <h4>Address and Phone</h4>
        <p class="address">
          {data.name}
          <br />
          {data.email}
          <br />
          <br />
          {data.address.street}
          <br />
          {data.address.city},
          {data.address.state}
          {data.address.zip}
          <br />
          <span>{data.phone}</span>
        </p>
      </div>
    </aside>
  </div>
</section>
