<script>
    export let data
</script>

<header>
    <nav>
        <a href="/">LM</a>
        <ul>
            <li><a href="/i-love-web">i-love-web</a></li>
            <li><a href="/portfolio">Portfolio</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
    </nav>
</header>

<style>
    header {
        width: 100%;
        height: 5rem;
    }
    nav {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 10fr 1fr;
        position: fixed;
        background: var(--secondColor);
        box-shadow: rgba(0, 0, 0, 0.04) 0px 3px 5px;
    }
    nav > a {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    ul {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row;
        gap: 1rem;
        width: 100%;
        list-style: none;
    }
    a {
        text-decoration: none;
        color: black;
        font-size: 1rem;
        font-family: var(--mainFont);
        padding: 1.75rem;
        transition: .25s ease-out;
    }
    a:hover {
        color: var(--mainColor);
    }
</style>