<script>
  let src = "./assets/svg/royalblueHeader.svg";
  let img1 = "./assets/svg/littleguy.svg";
  let img2 = "./assets/svg/kai.svg";
</script>

<div class="about_header">
  <img class="header" src="{src}" alt="blue-header" />
  <h1 class="about_title">About Me</h1>
  <button class="resume_button">
    <a href="https://resume.creddle.io/resume/63v349pbnj3">Resume</a>
  </button>
</div>

<div class="about_section">
  <section class="section">
    <img class="img1" src="{img1}" alt="pic of me" />
    <img class="img1" src="{img2}" alt="pic of me" />
  </section>

  <section class="section">
    <p>
      Welcome to my portfolio! My name is Luis Ocasio. I am fullstack web
      developer from Pennsylvania.
    </p>
  </section>
</div>

<style>
  .about_section {
    height: 650px;
    width: 100%;
    background-color: #15202b;
    display: flex;
    align-items: center;
    /* border-bottom: 2px solid gray; */
    justify-content: space-between;
    font-size: small;
    padding: 1rem;
  }
  .img1 {
    width: 80%;
    height: 80%;
  }
  .section {
    width: 100%;
    text-align: center;
    padding: 1rem;
    display: flex;
  }
  .about_header {
    position: relative;
    text-align: center;
    color: white;
    background-color: #15202b;
  }

  .about_title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .resume_button {
    position: absolute;
    top: 50%;
    left: 20%;
    transform: translate(-50%, -50%);
    background-color: #21367f;
    color: #fff;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
    margin-right: 2.25rem;
    border: 2px solid #d617bd;
  }
</style>
