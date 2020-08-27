<script>
  let src = "./assets/svg/royalblueHeader.svg";
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
    <h5>SOME CONETENT</h5>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam rem
      porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi. Doloribus
      neque totam doloremque quam voluptatem repudiandae, debitis rerum.
    </p>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam rem
      porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi. Doloribus
      neque totam doloremque quam voluptatem repudiandae, debitis rerum.
    </p>
  </section>

  <section class="section">
    <h5>A LITTLE MORE ABOUT ME</h5>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam rem
      porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi. Doloribus
      neque totam doloremque quam voluptatem repudiandae, debitis rerum.
    </p>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam rem
      porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi. Doloribus
      neque totam doloremque quam voluptatem repudiandae, debitis rerum.
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
  }
  .section {
    width: 50%;
    text-align: center;
    padding: 3rem;
  }
  .about_header {
    position: relative;
    text-align: center;
    color: white;
    background-color: #15202b;
    /* border-top: 2px solid gray; */
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
