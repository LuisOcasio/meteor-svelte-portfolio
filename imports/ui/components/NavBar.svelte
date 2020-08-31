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
            class={`mobile-icon${showMobileMenu ? ' active' : ''}`}
        >
            <div class="middle-line" />
            <ul class={`navbar-list${showMobileMenu ? ' mobile' : ''}`}>
                {#each navItems as item}
                    <li>
                        <a href={item.href}>{item.label}</a>
                    </li>
                {/each}
            </ul>
        </div>
    </div>
</nav>

<style>
    nav {
        width: 100%;
        background-color: #15202b;
        height: 75px;
        position: fixed;
        top: 0;
        z-index: 2;
    }

    .inner {
        max-width: 1100px;
        padding-left: 20px;
        padding-right: 20px;
        box-sizing: border-box;
        display: flex;
        align-items: center;
        height: 100%;
        justify-content: flex-end;
        justify-content: space-between;
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
        padding: 0 40px;
    }

    .navbar-list.mobile {
        background-color: rgba(0, 0, 0, 0.8);
        position: fixed;
        display: block;
        height: calc(100% - 75px);
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
