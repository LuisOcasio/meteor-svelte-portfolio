<script>
  let src = "./assets/svg/royalblueHeader.svg";
  let img1 = "./assets/svg/littleguy.svg";
  let img2 = "./assets/svg/kai.svg";
</script>

<div class="about_header">
  <img class="header" src="{src}" alt="blue-header" id="about" />
  <h4 class="about_title">About Me</h4>
</div>

<div class="about_section">
  <section class="section">
    <img class="img1" src="{img1}" alt="pic of me" />
    <img class="img1" src="{img2}" alt="pic of me" />
  </section>

  <section class="section-text">
    <p>
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
    height: 700px;
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
    padding: 2rem;
    width: 25%;
  }
  .section-text {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 100%;
    width: 100%;
    font-size: x-large;
    line-height: 3rem;
    align-items: center;
  }
  .section {
    text-align: left;
    display: flex;
    font-size: 1.25rem;
    width: 100%;
    height: 100%;
    justify-content: space-around;
    line-height: 3rem;
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
    width: 10%;
    height: 32px;
    text-decoration: none;
    border-radius: 35px;
    font-size: medium;
    align-self: flex-end;
    border: 2px solid #d617bd;
    margin-right: 2rem;
    margin-bottom: 3rem;
  }
  @media screen and (max-width: 768px) {
    .img1 {
      width: 80%;
    }
  }
  @media screen and (max-width: 668px) {
    .section-text {
      width: 100%;
      padding: 1rem;
    }
    .section {
      display: flex;
      flex-direction: column;
      height: 50%;
      width: 50%;
      text-align: center;
    }
    .about_section {
      display: flex;
      flex-direction: column-reverse;
      height: 100%;
    }
    @media screen and (max-width: 375px) {
      .slide_section {
        height: 50%;
      }
      .section {
        line-height: 2rem;
      }
    }
  }
</style>
