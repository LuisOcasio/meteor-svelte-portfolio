<script>
  let src = "./assets/svg/royalblueHeader.svg";
  let img1 = "./assets/svg/littleguy.svg";
  let img2 = "./assets/svg/kai.svg";
</script>

<div class="about_header">
  <img class="header" src="{src}" alt="blue-header" id="about" />
  <h3 class="about_title">About Me</h3>
</div>

<div class="about_section">
  <p>Welcome to my portfolio!</p>
  <section class="section">
    <img class="img1" src="{img1}" alt="pic of me" />
    <p>I'm Luis.</p>
    <img class="img1" src="{img2}" alt="pic of me" />
  </section>
  <p>A fullstack web developer from Pennsylvania.</p>
  <section class="section-text">
    <button class="resume_button">
      <a href="https://resume.creddle.io/resume/63v349pbnj3">Resume</a>
    </button>
  </section>
</div>

<style>
  p {
    padding: 3rem;
    text-align: center;
    line-height: 2rem;
  }
  .header {
    height: 100%;
    width: 100%;
  }
  .about_section {
    width: 100%;
    height: 100%;
    background-color: #15202b;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    font-size: x-large;
    padding: 1rem;
  }
  .img1 {
    width: 25%;
    height: 25%;
  }
  .section-text {
    display: flex;
    flex-direction: column;
    height: 50%;
    width: 100%;
    font-size: x-large;
  }
  .welcome-text {
    width: 100%;
    line-height: 2.5rem;
    margin-left: 20%;
  }
  .section {
    width: 90%;
    height: 50%;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
  .about_header {
    position: relative;
    text-align: center;
    color: white;
    background-color: #15202b;
    width: 100%;
  }

  .about_title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
  }

  .resume_button {
    background-color: #21367f;
    color: #fff;
    width: 15%;
    height: 32px;
    text-decoration: none;
    border-radius: 35px;
    font-size: medium;
    align-self: flex-end;
    border: 2px solid #d617bd;
    margin: 1rem 1rem 1rem;
  }
  @media screen and (max-width: 768px) {
    .section-text {
      width: 100%;
      text-align: center;
    }
  }

  @media screen and (max-width: 375px) {
    .resume_button {
      width: 25%;
    }
  }
</style>
