<script>
    import Header from '$lib/header.svelte';
    import Sprint13 from '$lib/sprint13.svelte'

</script>

<Header />

<main class="weloveweb">
    <h1>I-love-web</h1>
    <div class="container">
        <section class="sprints">
            <ul>
                <li><a href="#sprint13">Sprint 13</a></li>
                <li><a href="#sprint14">Sprint 14</a></li>
                <li><a href="#sprint15">Sprint 15</a></li>
                <li><a href="#sprint16">Sprint 16</a></li>
            </ul>
        </section>
        
        <section>
            <Sprint13 />
        </section>
    </div>
</main>


<style>
    /* .container {
        display: grid;
        grid-template-columns: 1fr 8fr;
        gap: 2rem;
        margin-top: 2rem;
    }
    .sprints ul {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    .sprints li a {
        color: var(--fontColor);
        font-size: 1.5rem;
        width: min-content;
        background: rgba(0, 0, 0, 0.083);
        border-radius: 4px;
        display: flex;
        padding: .75rem 1.25rem;
        justify-content: center;
        align-items: center;
        text-wrap: nowrap;
    }
    .sprints li a:hover {
        color: var(--mainColor);
    } */

h1 {
    font-size: 2.5rem;
    text-align: center;
    color: #0073e6;
    margin-bottom: 1.5rem;
}

.container {
    display: grid;
    grid-template-columns: 1fr 3fr;
    gap: 3rem;
    margin-top: 2rem;
}

.sprints ul {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.sprints li a {
    color: #333;
    font-size: 1.25rem;
    background: #e6f2ff;
    border-radius: 8px;
    padding: 1rem 1.5rem;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: background 0.3s ease, color 0.3s ease;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.sprints li a:hover {
    background: #0073e6;
    color: white;
}

.sprints li a:active {
    transform: scale(0.98);
}

section {
    background-color: #fff;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.1);
}

section h2 {
    color: #0073e6;
    margin-bottom: 1.5rem;
    font-size: 2rem;
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
        gap: 2rem;
    }

    .sprints ul {
        flex-direction: row;
        justify-content: space-around;
    }

    .sprints li a {
        font-size: 1rem;
        padding: 0.75rem 1rem;
    }
}

</style>