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
    .container {
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
    }
</style>