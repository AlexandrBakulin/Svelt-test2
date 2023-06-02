<nav>
    <div class="nav-container">
        <a href="/static" class="nav-logo" title="Back to Homepage">Alex Bakulin</a>
        <div class="nav-links">
            {#each nav as link}
                {#if link.isShow}
                <a href={link.href} class="link">{link.title}</a>
                {/if}
            {/each}
        </div>
    </div>
</nav>
<div class="container">
    <slot></slot>
</div>
<script>
    const nav = [
        {
            title: 'About me',
            href: '/about',
            isShow: true
        },
        {
            title: 'blog',
            href: '/blog',
            isShow: true
        },
        {
            title: 'portfolio',
            href: '/project',
            isShow: true
        },
        {
            title: 'contacts',
            href: '/contact',
            isShow: true
        },
        {
            title: 'temp',
            href: '/temp',
            isShow: false
        },
    ]
</script>
<style>
    .container {
        max-width: 1400px;
        margin: 50px auto;
    }
    .nav-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .nav-links {
        display: flex;
        justify-content: flex-end;
        align-items: center;
        margin: -1em 0;
        flex: 1 0 auto;
    }
    .nav-links .link {
        position: relative;
        margin: 1em;
        font-size: 0.85rem;
        letter-spacing: 1px;
        color: black;
    }
    .nav-logo {
        position: relative;
        line-height: 1;
        font-size: 1.1rem;
        color: black;
    }
</style>
