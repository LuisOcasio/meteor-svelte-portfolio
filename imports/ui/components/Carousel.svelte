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
      0: "A Headless WordPress site created for a client in the music industry. This website allows users to stream and downloaded music across various devices thanks to its custom media player.  ",
    },
    {
      1: "Single page application created for a local coffee shop business. This applicaton takes full advantage of react and the react-router library to render components and routes on the client rather than fetching data from a server.",
    },
    {
      2: "An 8 week long project that included 5 other developers and a UX designer. Market Avenue is an application that brings local vendors and locals closer.",
    },
  ];

  const technologies = {
    0: ["Gatsby", "WordPress", "Graphql", "amplify", "route53", "lightsail"],

    1: ["single page application", "React", "Mobile Resoponsive"],

    2: ["React", "mongoDB", "node", "express", "sass"],
  };

  $: project = Object.keys(projects[slide]);
  $: url = Object.values(projects[slide]);
  $: git = Object.values(projects_url[slide]);
  $: about = Object.values(projects_about[slide]);
  $: tech_stack_list = Object.values(technologies[slide]);

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

<div class="carousel" id="projects">
  <div class="previous_wrapper">
    <img
      class="previous"
      alt="go-back-arrow"
      src="{previousSlide}"
      on:click="{previous}"
    />
  </div>

  <!-- slide section -->
  <div class="slide-wrapper">
    <div class="slide">
      <h5>{project}</h5>

      {#each [Projects[index]] as src (index)}
      <div class="image_wrapper">
        <img class="carousel-image" alt="landing page of project" src={src}
        in:fly={{ x: -50, duration: 2000 }} />
      </div>
      {/each}

      <div class="like_section">
        {#if like}
        <p class="liked_title">Thanks for liking!</p>
        <img
          class="heart"
          src="{heart_filled}"
          alt="heart filled pink"
          on:click|preventDefault="{handleClick}"
        />
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

    <div class="text-section">
      <div class="section1">
        <h5 class="section_title">Project Role</h5>
        <p class="section_paragraph">{about}</p>
      </div>

      <div class="section2">
        <h5 class="tech_title">Tech Stack</h5>
        <div class="stack_list_wrapper">
          {#each tech_stack_list as tech }
          <li>{tech}</li>
          {/each}
        </div>

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
  </div>
  <div class="next_wrapper">
    <img class="next" alt="next-arrow" src="{nextSlide}" on:click="{next}" />
  </div>

  <style>
    li {
      padding: 0.25rem;
    }
    .main_slide {
      display: flex;
      width: 100%;
      height: 100%;
    }
    .heart {
      width: 1.5rem;
      padding: 1rem;
    }
    .like_title {
      padding: 1rem;
      width: 100%;
      color: #d617bd;
      text-align: center;
    }
    .liked_title {
      color: #d617bd;
    }
    .carousel {
      display: flex;
      background-color: #15202b;
      height: 800px;
      width: 100%;
    }

    .image_wrapper {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;
    }
    .slide-wrapper {
      width: 100%;
      height: 100%;
      display: flex;
    }
    .slide {
      width: 60%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      height: 100%;
      padding: 1rem;
    }
    .slide_section {
      width: 100%;
      height: 100%;
      display: flex;
    }
    .like_section {
      display: flex;
      align-items: center;
      flex-direction: column;
      margin-bottom: 1rem;
    }

    .slide_title {
      font-size: small;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      padding: 0.5rem;
    }

    .carousel-image {
      width: 90%;
      height: 80%;
    }
    .previous_wrapper {
      background-color: #21367f;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 10%;
    }
    .previous {
      width: 60%;
      z-index: 1;
    }
    .next_wrapper {
      background-color: #21367f;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 10%;
    }
    .next {
      width: 60%;
      z-index: 1;
    }
    .project_buttons {
      display: flex;
      justify-content: space-around;
      align-items: flex-end;
      width: 100%;
      padding: 1rem;
      height: 50%;
    }
    .code {
      background-color: #21367f;
      color: #fff;
      border: 2px solid #2dfafc;
      width: 5rem;
      height: 2rem;
      text-decoration: none;
      border-radius: 35px;
      font-size: small;
    }
    .view {
      color: #fff;
      border: 2px solid #2dfafc;
      background-color: #21367f;
      width: 5rem;
      height: 2rem;
      text-decoration: none;
      border-radius: 35px;
      font-size: small;
    }
    .text-section {
      display: flex;
      flex-direction: column;
      width: 50%;
      justify-content: space-between;
      align-items: center;
      border-left: 2px solid #d617bd;
    }
    .section1 {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      font-size: small;
      height: 50%;
      width: 100%;
      align-items: center;
    }
    .section2 {
      display: flex;
      flex-direction: column;
      font-size: small;
      align-items: center;
      justify-content: space-between;
      height: 50%;
      width: 100%;
    }
    .section_paragraph {
      width: 90%;
      line-height: 1.5rem;
      text-align: left;
      display: flex;
      height: 100%;
      align-items: center;
    }
    .section_title {
      border-bottom: 2px solid #d617bd;
      width: 60%;
      padding: 0.5rem;
      text-align: center;
    }
    .tech_title {
      border-bottom: 2px solid #d617bd;
      width: 60%;
      padding: 0.5rem;
      text-align: center;
    }
    .stack_list {
      width: 100%;
    }
    .stack_list_wrapper {
      width: 90%;
      height: 100%;
      display: flex;
      flex-direction: column;
      text-align: left;
      font-size: small;
      justify-content: center;
      line-height: 1.5rem;
      margin-top: 1rem;
    }
    @media screen and (max-width: 865px) {
      .project_buttons {
        max-width: 100%;
      }
    }
    @media screen and (max-width: 768px) {
      .carousel-image {
        width: 60%;
      }
      .text-section {
        display: flex;
        flex-direction: row-reverse;
        justify-content: space-around;
        width: 100%;
        height: 40%;
        border-left: none;
      }
      .section1,
      .section2 {
        width: 50%;
        height: 100%;
      }

      .slide {
        height: 50%;
        width: 100%;
        display: flex;
        padding: inherit;
      }
      .slide_section {
        display: flex;
        width: 100%;
        height: 100%;
        align-items: center;
      }
      .section_paragraph {
        text-align: center;
        height: 100%;
        padding: 1rem;
        align-items: flex-start;
      }
      .project_buttons {
        display: flex;
        justify-content: space-around;
        width: 100%;
      }
      .slide-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
      }
    }

    @media screen and (max-width: 375px) {
      .project_buttons {
        display: flex;
        flex-direction: row;
        width: 100%;
      }
    }
    @media screen and (max-width: 489px) {
      .section_paragraph {
        line-height: normal;
      }
      .text-section {
        display: flex;
        height: 100%;
        width: 100%;
      }
      .section_title {
        width: 70%;
      }
      .tech_title {
        width: 70%;
      }
    }

    @media screen and (max-width: 668px) {
      .slide {
        width: 90%;
        height: 50%;
      }
      .text-section {
        height: 40%;
        display: flex;
        flex-direction: row;
      }
      .section1 {
        width: 50%;
        height: 100%;
      }

      .section2 {
        height: 100%;
        width: 50%;
      }
      .stack_list_wrapper {
        width: 80%;
        line-height: normal;
        display: flex;
        align-items: flex-start;
        height: 100%;
      }
      li {
        width: 100%;
      }
      .section_paragraph {
        padding: 1.5rem;
      }
    }
    @media screen and (max-width: 445px) {
      .project_buttons {
        height: 100%;
      }
      .slide {
        width: 90%;
        height: 40%;
      }
      .text-section {
        height: 100%;
      }
      .section1 {
        width: 50%;
        height: 100%;
      }

      .section2 {
        height: 100%;
        width: 50%;
      }
      .stack_list_wrapper {
        height: 100%;
        width: 100%;
        line-height: normal;
      }
    }
  </style>
</div>
