<script>
    import Carousel from '../components/Carousel.svelte'
    import About from '../components/About.svelte'
    import Contact from '../components/Contact.svelte'
    import NavBar from '../components/NavBar.svelte'

    let src = 'assets/denverBanner.png'
    let desc = 'art-work'
</script>

<div class="wrapper">
    <NavBar/>
    <div class="banner-section" id='home'>
        <img class="banner" alt={desc} src={src} />
    </div>
        <div class='photo_desc' >
            <span>photo by: Luis Ocasio - Denver, CO 'RINO ART DISTRICT'</span>
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
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: center;
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
        padding: 0.5rem;
        text-align: left;
        width: 100%;

    }
    .tech-icons {
        background-color: #15202b;
        display: flex;
        align-items: center;
        font-size:small;
        text-align: center;
        width: 80%;
        padding: 3rem;
    }
    .icon-container {
        height: 100%;
        width: 25%;
    }
    @media screen and (max-width: 360px) {
    
    }
 
    @media screen and (max-width: 500px) {
        .tech-icons{
            width: 100%;
            display: flex;
            align-items: center;
        }
        .icon-container {
            width: 25%;
        }
    }
</style>
