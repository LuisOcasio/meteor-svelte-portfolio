<script>
  import { useTracker } from "meteor/rdb:svelte-meteor-data";
  import { Likes } from "../../api/likes";
  import { fly, fade } from "svelte/transition";
  let src = "/assets/svg/royalblueHeader.svg";
  let project1 = "/assets/projects/jaems.png";
  let project2 = "/assets/projects/latte-site.jpg";
  let project3 = "/assets/projects/market.png";
  let previousSlide = "/assets/svg/back.svg";
  let nextSlide = "/assets/svg/next.svg";
  let heart = "/assets/svg/heartline.svg";
  let heart_filled = "/assets/svg/heartfill.svg";

  let index = 0;
  let slide = 0;

  const Projects = [project1, project2, project3];

  const next = () => {
    index = (index + 1) % Projects.length;
    slide = (slide + 1) % projects.length;
  };

  const previous = () => {
    if (index && slide) {
      index = (index - 1) % Projects.length;
      slide = (slide - 1) % projects.length;
    }
  };

  const projects = [
    { Jaemsounds: "https://www.jaemsounds.com/" },
    { LatteLuv: "https://latteluv.netlify.app/" },
    { MarketAvenue: "https://marketavenue.netlify.app/" },
  ];

  const projects_url = [
    { 0: "https://github.com/LuisOcasio/Jaemsounds-Gatsby-WP-AWS" },
    { 1: "https://github.com/LuisOcasio/latte-luv" },
    { 2: "https://github.com/Lambda-School-Labs/quick-street-be" },
  ];

  const projects_about = [
    {
      0: "A Headless WordPress site created for a client in the music industry. This website allows users to stream and downloaded music across various devices thanks to its custom media player. Users can also purchase instrumentals through checkout service. The benefits of a headless cms is that my client has full control of the content on the site through a user friendly ui thanks to wordpress.",
    },
    {
      1: "Single page application created for a local coffee shop business. This applicaton takes full advantage of react and the react-router library to render components and routes on the client rather than fetching data from a server.",
    },
    {
      2: "An 8 week long project that included 5 other developers and a UX designer. Market Avenue is an application that brings local vendors and locals closer.",
    },
  ];

  const technologies = [
    {
      id: 1,
      project: [
        "\nGatsby\nWordPress\nGraphql\nAWS-Services\namplify\nroute53    \nlightsail",
      ],
    },
    { id: 2, project: ["\nspa\nreact\nsass\n"] },
    { id: 3, project: ["\nreact\nmongoDB\nnode\nexpress\nsass\n"] },
  ];

  $: project = Object.keys(projects[slide]);
  $: url = Object.values(projects[slide]);
  $: git = Object.values(projects_url[slide]);
  $: about = Object.values(projects_about[slide]);

  let like = false;
  let total = 0;

  $: getLikes = useTracker(() => Likes.find({}).fetch());

  function handleClick() {
    Likes.insert({
      like: true,
      createdAt: new Date(),
    });
    like = true;
  }
</script>

<div class="carousel_wrapper">
  <div class="carousel">
    <div class="previous_wrapper">
      <img
        class="previous"
        alt="go-back-arrow"
        src="{previousSlide}"
        on:click="{previous}"
      />
    </div>

    <div class="slide">
      <section class="slide_title">
        <h5>{project}</h5>
      </section>

      <div class="image_wrapper">
        {#each [Projects[index]] as src (index)} <img class="carousel-image"
        alt="landing page of project" src={src} in:fly={{ x: -50, duration: 2000 }}
        /> {/each}
      </div>

      <div class="like_section">
        {#if like}
        <p class="liked_title">Thanks for liking!</p>
        {:else}
        <p class="like_title">Like what you see? Give this page a like!</p>
        <h5>{($getLikes.length)}</h5>

        <img
          class="heart"
          src="{heart}"
          alt="heart filled pink"
          on:click|preventDefault="{handleClick}"
        />
        {/if}
      </div>
    </div>

    <div class="text-wrapper">
      <div class="text-section">
        <section class="section">
          <h5 class="section_title">About this project</h5>
          <p class="section_paragraph">{about}</p>
        </section>

        <section class="section">
          <h5 class="tech_title">Tech Stack used</h5>
          <div class="stack_list_wrapper">
            {#each [technologies[index]] as { id, project }}
            <p>{project.map((e) => { return e.toString() })}</p>
            {/each}
          </div>
        </section>

        <div class="project_buttons">
          <a href="{git}">
            <button class="code">Code</button>
          </a>
          <a href="{url}">
            <button class="view">View</button>
          </a>
        </div>
      </div>
    </div>
    <div class="next_wrapper">
      <img class="next" alt="next-arrow" src="{nextSlide}" on:click="{next}" />
    </div>
  </div>
</div>

<style>
  .heart {
    width: 1.5rem;
    padding: 1rem;
  }
  .like_title {
    padding: 1rem;
    width: 100%;
    color: #d617bd;
  }
  .like_section {
    height: 100%;
  }
  .liked_title {
    color: #d617bd;
  }
  .carousel_wrapper {
    height: 650px;
  }

  .carousel {
    display: flex;
    height: 100%;
    width: 100%;
    background-color: #15202b;
  }

  .image_wrapper {
    height: 71%;
    width: 85%;
  }

  .slide {
    width: 60%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 100%;
    padding: 1.5rem;
  }

  .like_section {
    height: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .slide_title {
    font-size: small;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    padding: 0.5rem;
  }

  .carousel-image {
    width: 80%;
    height: 80%;
    padding: 3rem;
  }
  .previous_wrapper {
    background-color: #21367f;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .previous {
    width: 40px;
    z-index: 1;
    padding: 0.5rem;
  }
  .next_wrapper {
    background-color: #21367f;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .next {
    width: 40px;
    z-index: 1;
    padding: 0.5rem;
  }
  .project_buttons {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    margin-top: 2rem;
  }
  .code {
    background-color: #21367f;
    color: #fff;
    border: 2px solid #2dfafc;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
  }
  .view {
    color: #fff;
    border: 2px solid #2dfafc;
    background-color: #21367f;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
  }
  .text-wrapper {
    display: flex;
    justify-content: flex-end;
    width: 50%;
    border-left: 2px solid #d617bd;
    padding: 1.5rem;
  }
  .text-section {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
  }
  .section {
    height: 100%;
    display: flex;
    flex-direction: column;
    font-size: small;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    text-align: center;
  }
  .section_paragraph {
    width: 100%;
    height: 100%;
    line-height: 1.5rem;
    text-align: left;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .section_title {
    border-bottom: 2px solid #d617bd;
    width: 50%;
    padding: 0.5rem;
  }
  .tech_title {
    border-bottom: 2px solid #d617bd;
    width: 50%;
    padding: 0.5rem;
  }
  .stack_list {
    width: 100%;
    height: 100%;
  }
  .stack_list_wrapper {
    height: 100%;
    display: flex;
    align-items: center;
    width: 100%;
    word-spacing: 30rem;
    line-height: 2rem;
    justify-content: center;
  }
</style>
