<script>
  let src = "./assets/svg/royalblueHeader.svg";
</script>

<div class="header_container">
  <img class="header" src="{src}" alt="blue-header" />
  <h1 class="header_title">Lets Keep In Touch</h1>
</div>

<footer id="hello">
  <form id="contact_form">
    <input type="name" placeholder="name" />
    <input type="email" placeholder="email" />
    <input type="phone" placeholder="phone" />
  </form>

  <form id="message_form">
    <input id="message_input" type="main_input" placeholder="message" />
  </form>

  <a href="/">
    <button>Submit</button>
  </a>

  <p>Follow me across these social media platforms.</p>

  <div id="social-media-icons">
    <a href="https://www.instagram.com/fullstack_og/" alt="social-media-icon">
      <img
        src="https://img.icons8.com/fluent/48/000000/instagram-new.png"
        alt="instagram-logo"
      />
    </a>
    <a href="https://twitter.com/FullstackOg" alt="social-media-icon">
      <img
        src="https://img.icons8.com/fluent/48/000000/twitter.png"
        alt="twitter-logo"
      />
    </a>
    <a href="https://www.linkedin.com/in/ocasio-perez/" alt="social-media-icon">
      <img
        src="https://img.icons8.com/office/48/000000/linkedin.png"
        alt="linkedin-logo"
      />
    </a>
  </div>

  <div>
    <a href="https://fullstackog.com/" alt="blog-site">
      <p>🚧Checkout My Blog Site🚧</p>
    </a>
  </div>
</footer>

<style>
  footer {
    bottom: 0;
    width: 100%;
    height: 700px;
    background-color: #15202b;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }
  input {
    height: 48px;
    width: 250px;
    border-radius: 5px;
    text-align: center;
  }
  button {
    width: 130px;
    height: 32.5px;
    border-radius: 5px;
    font-size: small;
    background-color: #21367f;
    color: #fff;
  }
  .header_container {
    position: relative;
    text-align: center;
    color: white;
    background-color: #15202b;
  }
  .header_title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  #contact_form {
    width: 100%;
    display: flex;
    justify-content: space-around;
    padding: 2rem;
  }
  #message_form {
    width: 100%;
    display: flex;
    justify-content: space-around;
    padding: 2rem;
  }
  #message_input {
    height: 250px;
    width: 50%;
  }
</style>
