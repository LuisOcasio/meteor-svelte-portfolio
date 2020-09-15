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
  <section class="section">
    <img class="img1" src="{img1}" alt="pic of me" />
    <img class="img1" src="{img2}" alt="pic of me" />
  </section>

  <section class="section-text">
    <p class="welcome-text">
      Welcome to my portfolio!<br />
      My name is Luis.<br />
      I am fullstack web developer from Pennsylvania.
    </p>

    <button class="resume_button">
      <a href="https://resume.creddle.io/resume/63v349pbnj3">Resume</a>
    </button>
  </section>
</div>

<style>
  .header {
    height: 100%;
    width: 100%;
  }
  .about_section {
    width: 100%;
    background-color: #15202b;
    display: flex;
    align-items: center;
    /* border-bottom: 2px solid gray; */
    justify-content: space-between;
    font-size: small;
    line-height: 2.5rem;
    flex-direction: column;
  }
  .img1 {
    padding: 1rem;
    width: 35%;
    height: 50%;
  }
  .section-text {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 50%;
    width: 90%;
    font-size: x-large;
    align-items: center;
    padding: 3rem;
  }
  .welcome-text {
    width: 65%;
    line-height: 3rem;
  }
  .section {
    display: flex;
    font-size: 1.25rem;
    width: 90%;
    height: 50%;
    justify-content: space-around;
    padding: 3rem;
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
    margin-right: 2rem;
    margin-bottom: 3rem;
    margin-top: 1rem;
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
