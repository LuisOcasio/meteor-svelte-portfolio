<script>
    import { onMount } from 'svelte'

    let showMobileMenu = false

    const navItems = [
        { label: 'Skills', href: '#' },
        { label: 'Projects', href: '#' },
        { label: 'Contact', href: '#' },
    ]

    const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu)

    const mediaQueryHandler = (e) => {
        if (!e.matches) {
            showMobileMenu = false
        }
    }

    onMount(() => {
        const mediaListener = window.matchMedia('(max-width: 767px)')
        mediaListener.addListener(mediaQueryHandler)
    })
</script>

<nav>
    <div class="inner">
        <h5>Full stack web developer</h5>
        <div
            on:click={handleMobileIconClick}
            class={`mobile-icon${showMobileMenu ? ' active' : ''}`}        >
            <div class="middle-line" />
            <ul class={`navbar-list${showMobileMenu ? ' mobile' : ''}`}>
                <a href="#home">Top of Page</a>
                <a href="#projects">Projects</a>
                <a href="#about">About</a>
                <a href="#contact">Contact</a>
            </ul>    
        </div>
    </div>
</nav>

<style>
    nav {
        background-color: #15202b;
        z-index: 2;
        display: flex;
        justify-content: space-between;
        height: 50px;
        width: 100%;
        position: sticky;
    }

    .inner {     
        display: flex;
        align-items: center;     
        justify-content: space-between;
        width: 100%;
    }

    .mobile-icon {
        width: 25px;
        height: 14px;
        position: relative;
        cursor: pointer;
    }

    .mobile-icon:after,
    .mobile-icon:before,
    .middle-line {
        content: '';
        position: absolute;
        width: 100%;
        height: 2px;
        background-color: #fff;
        transition: all 0.4s;
        transform-origin: center;
    }

    .mobile-icon:before,
    .middle-line {
        top: 0;
    }

    .mobile-icon:after,
    .middle-line {
        bottom: 0;
    }

    .mobile-icon:before {
        width: 66%;
    }

    .mobile-icon:after {
        width: 33%;
    }

    .middle-line {
        margin: auto;
    }

    .mobile-icon:hover:before,
    .mobile-icon:hover:after,
    .mobile-icon.active:before,
    .mobile-icon.active:after,
    .mobile-icon.active .middle-line {
        width: 100%;
    }

    .mobile-icon.active:before,
    .mobile-icon.active:after {
        top: 50%;
        transform: rotate(-45deg);
    }

    .mobile-icon.active .middle-line {
        transform: rotate(45deg);
    }

    .navbar-list {
        display: none;
        width: 100%;
        justify-content: space-between;
        margin: 0;

    }

    .navbar-list.mobile {
        background-color: rgba(0, 0, 0, 0.8);
        position: fixed;
        display: block;
        height: calc(100% - 50px);
        bottom: 0;
        left: 0;
    }

    .navbar-list li {
        list-style-type: none;
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .navbar-list li:before {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
    }

    .navbar-list a {
        color: #fff;
        text-decoration: none;
        display: flex;
        height: 45px;
        align-items: center;
        padding: 0 10px;
        font-size: 13px;
        width: 100%;
        justify-content: center;
    }
</style>
