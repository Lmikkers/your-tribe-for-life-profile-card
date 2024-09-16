<script>
    export let data
</script>

<header>
    <nav>
        <a href="">LM</a>
        <ul>
            <li><a href="#">i-love-web</a></li>
            <li><a href="#">Portfolio</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
</header>

<style>
    header {
        width: 100%;
    }
    nav {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 10fr 1fr;
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
        font-size: 1.25rem;
        font-family: var(--mainFont);
        padding: 1rem;
        background-color: antiquewhite;
    }
</style>