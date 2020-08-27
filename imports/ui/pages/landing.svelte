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
    <div class="banner-section">
        <img class="banner" alt={desc} src={src} />
    </div>

    <div class="tech-icons">
        <div class="icon-container">
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
        overflow: hidden;
    }

    li {
        list-style-type: none;
    }
    .banner-section {
        height: 650px;
    }
    .banner {
        width: 100%;
        height: 100%;
    }
    .tech-icons {
        background-color: #15202b;
        border-bottom: 2px solid gray;
        height: 100px;
        display: flex;
        align-items: center;
        justify-content: space-around;
        font-size: large;
        padding: 3rem;
    }
    .icon-container {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        height: 100%;
        align-items: center;
        padding: 1.5rem;
        height: 100%;
        width: 100%;
    }
</style>
