<nav>
    <div class="nav-container">
        <a href="/" class="nav-logo" title="Back to Homepage">Alex Bakulin</a>
        <div class="nav-links">
            <a href="/about" class="link">About me</a>
            <a href="/blog" class="link">Blog</a>
            <a href="/projects" class="link">My project</a>
            <a href="/contact" class="link">Contacts</a>
        </div>
    </div>
</nav>
<div class="container">
    <slot></slot>
</div>
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
