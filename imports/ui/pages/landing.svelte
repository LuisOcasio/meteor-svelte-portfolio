<script>
    import Carousel from '../components/Carousel.svelte'
    import About from '../components/About.svelte'
    import Contact from '../components/Contact.svelte'
    import NavBar from '../components/NavBar.svelte'

    let src = 'assets/denverBanner.png'
    let desc = 'art-work'
</script>

<div class="wrapper">
    <NavBar />
    <div class="banner-section" id='home'>
        <img class="banner" alt={desc} src={src} />
    </div>
        <div class='photo_desc' >
            <p>photo by: Luis Ocasio - Denver, CO 'RINO ART DISTRICT'</p>
        </div>
    <div class="tech-icons" >
        <div class="icon-container" id="skills">
            <img
                src="https://img.icons8.com/color/48/000000/javascript.png"
                alt="javascript-logo"
            />
            <li>JavaScript</li>
        </div>
        <div class="icon-container">
            <img
                src="https://img.icons8.com/color/48/000000/react-native.png"
                alt="react-logo"
            />
            <li>React</li>
        </div>
        <div class="icon-container">
            <img
                src="https://img.icons8.com/doodle/48/000000/svetle.png"
                alt="svelte-log"
            />
            <li>Svelte</li>
        </div>
        <div class="icon-container">
            <img
                src="https://img.icons8.com/color/48/000000/graphql.png"
                alt="graphql-logo"
            />
            <li>graphql</li>
        </div>
        <div class="icon-container">
            <img
                src="https://img.icons8.com/color/48/000000/python.png"
                alt="python-logo"
            />
            <li>Python</li>
        </div>
    </div>

    <Carousel />
    <About />
    <Contact />

</div>

<style>
    .wrapper {
    max-width: 1100px;
    margin:auto;
    }

    li {
        list-style-type: none;
    }
      .banner {
     height: 100%;
     width: 100%;
    }
    .photo_desc{
        font-size: xx-small;
    }
    .tech-icons {
        background-color: #15202b;
        border-bottom: 2px solid gray;
        height: 5%;
        display: flex;
        align-items: center;
        justify-content: space-around;
        font-size: large;
        width: 100%;

    }
    .icon-container {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        padding: 1.5rem;
        height: 100%;
        width: 100%;
    }
    @media screen and (max-width: 550px) {
        .tech-icons{
        display: flex;

        flex-wrap: wrap;
        }
        .icon-container{
            width: 25%;
        }
    }
    @media screen and (min-width: 375px) {
        .tech-icons{
            width: 100%;
        }
        li{
        font-size: small;
        }
        .icon-container{
            width: 25%;
        }
        .banner-section{
            display: flex;
            align-items: center;
            height: 50%;
        }   
    }
</style>
