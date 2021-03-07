<script>
  export let data;
</script>

<section id="resume">
  <div class="row education">
    <div class="three columns header-col">
      <h1><span>Education</span></h1>
    </div>

    <div class="nine columns main-col">
      <div class="row item">
        <div class="twelve columns">
          {#each data.education as education}
            <div key={education.school}>
              <h3>{education.school}</h3>
              <p class="info">
                {education.degree}
                <span>&bull;</span>
                <em class="date">{education.graduated}</em>
              </p>
              <p>{education.description}</p>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>

  <div class="row work">
    <div class="three columns header-col">
      <h1><span>Work</span></h1>
    </div>

    <div class="nine columns main-col">
      {#each data.work as work}
        <div key={work.company}>
          <h3>{work.company}</h3>
          <p class="info">
            {work.title}
            <span>&bull;</span>
            <em class="date">{work.years}</em>
          </p>
          <p>{work.description}</p>
        </div>
      {/each}
    </div>
  </div>

  <div class="row skill">
    <div class="three columns header-col">
      <h1><span>Skills</span></h1>
    </div>

    <div class="nine columns main-col">
      <p>{data.skillmessage}</p>

      <div class="bars">
        <ul class="skills">
          {#each data.skills as skills}
            <li key={skills.name}>
            <span style={{ width: skills.level }} class={`bar-expand${skills.name.toLowerCase()}`} />
              <em>{skills.name}</em>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</section>
