<nav>
    <div class="nav-container">
        <a href="/static" class="nav-logo" title="Back to Homepage">Alex Bakulin</a>
        <div class="nav-links">
            {#each nav as link}
                <a href={link.href} class="link">{link.title}</a>
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
            href: '/about'
        },
        {
            title: 'blog',
            href: '/blog'
        },
        {
            title: 'portfolio',
            href: '/project'
        },
        {
            title: 'contacts',
            href: '/contact'
        },
        {
            title: 'temp',
            href: '/temp'
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
