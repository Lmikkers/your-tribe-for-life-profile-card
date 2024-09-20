<script>
    export let data

    import Header from '$lib/header.svelte';
  
    function checkAvatarImage (avatar) {
      if (avatar.includes('https')) {
        return true
      } 
  
      return false
    }
    console.log(data);
    
    import mailIcon from '/assets/mailWhite.svg';
    import githubIcon from '/assets/github-mark-white.svg';
    import instaIcon from '/assets/instagramWhite.svg';
    import turnIcon from '/assets/turnedWhite.svg';

    // Variabele om bij te houden of het artikel open is
    let isFlip = false;

    // Functie om de .flip class toe te voegen
    const toggleFlip = () => {
        isFlip = !isFlip;
        console.log('toggle card', isFlip);
    };

</script>

<Header />

<main id="cardContainer">
    <div class="cards" class:flip={isFlip}>
        <article class="cardFront">
            <section>
                <ul>
                    <li><a href="mailto:larissa.mikkers@hva.nl"><img src="{mailIcon}" alt="mail icoon"></a></li>
                    <li><a href="https://github.com/{data.persons.github_handle}" target="_blank"><img src="{githubIcon}" alt="github logo icoon"></a></li>
                    <li><a href=""><img src="{instaIcon}" alt="instagram logo"></a></li>
                </ul>

                <button on:click={toggleFlip}><img src="{turnIcon}" alt="button to go to the back of the card"></button>
            </section>

            <section>
                <h1 class="typeWriter">{data.persons.name}</h1>
                <h2>{data.persons.surname}</h2>
            </section>
        </article>

        <article class="cardBack">
            <button on:click={toggleFlip}><img src="{turnIcon}" alt="button to go to the back of the card"></button>
            <h3>{data.persons.name}</h3>
            <p>{data.persons.bio}</p>
        </article>
    </div>
</main>

<style>
    main {
        /* min-height: 100vh; */
        height: calc(100vh - 5rem);
        display: grid;
        place-items: center;
        font-family: "Roboto", sans-serif;
        background: #fbf7f1;
        perspective: 1000px;
    }
    h1.typeWriter {
        overflow: hidden;
        border-right: 0.15em solid orange;
        white-space: nowrap;
        animation: typing 2.25s steps(30, end), blink-caret .5s step-end infinite;
    }
    h2 {
        font-size: 2rem;
        text-transform: lowercase;
        font-weight: 100;
    }
    article {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
       
        width: 40rem;
        height: 25rem;
        border-radius: 1rem;

        background: white;
        text-align: center;
        box-shadow: 0 0 20px 20px rgba(0,0,0,.1);

        -webkit-backface-visibility: hidden;
        backface-visibility: hidden;
    }
    article:first-child section:nth-child(1) {
        position: absolute;
        top: 2rem;
        display: flex;
        justify-content: space-between;
        width: 100%;
        padding: 0 2rem;
    }
    ul {
        list-style: none;
        display: flex;
        flex-direction: row;
        gap: 1em;
    }
    ul a {
        text-decoration: none;
        color: var(--fontColor);
    }
    button {
        font-size: 1rem;
        border: none;
        padding: 1rem;
        border-radius: 50%;
        cursor: pointer;
        width: 2rem;
        height: 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .cardBack{
        position: absolute;
        /* top: 0; */
        transition: .75s ease-in-out;
        /* wanneer je flipt staat de tekst goed */
        transform: rotateY(180deg);
        padding: 2rem 4rem;
        /* DISPLAY GRID */
        /* display: grid;
        grid-template-columns: repeat(10, 1fr);
        grid-template-rows: repeat(6, 1fr); */
    }
    button {
        width: 2.75rem;
        height: 2.75rem;
        background: black;
        border-radius: 50%;
        border: none;
        color: white;
        cursor: pointer;
        transition: 250ms ease-in-out;

        display: flex;
        align-items: center;
        justify-content: center;
    }
    .flip button {
        position: absolute;
        top: 2rem;
        right: 2rem;
    }
    button img,
    a img {
        width: 1.25em;
        aspect-ratio: 1 / 1 ;
        object-fit: contain;
    }
    button:hover {
        transform: rotate(-20deg);
        background-color: rgb(36, 36, 36);
    }

    /* wanneer de button wordt geklikt */
     /* nieuwe code */
    .cards {
        width: 80vw;
        max-width: 40rem;
        height: 25rem;
        position: relative;
        transform-style: preserve-3d;
        transition: transform 1s;
    }
    .cards.flip {
        transform: rotateY(180deg);
    }
    .cardFront, .cardBack {
        width: 100%;
        height: 100%;
        position: absolute;
        backface-visibility: hidden;
    }
    .cardFront {
        transform: rotateY(0deg);
    }
    .cardBack {
        transform: rotateY(180deg);
    }

    .cardBack h3 {
        grid-column: 4 / span 4;
        grid-row: 1/ span 2;
    }
    .cardBack > img {
        position: absolute;
        top: -3rem;
        left: -3rem;
        width: 12rem;
        height: 12rem;
        border-radius: 50%;
        border: 8px solid white;
        object-fit: cover;
    }
    .cardBack p {
        grid-column: 2 / span 8;
        grid-row: span 3;
        text-align: left;
        margin-bottom: 1rem;
    }
    .showCard .cardBack{
        display: flex;
        transition: .75s ease-in-out;
    }
    /* IPAD/ TABLET */
    @media (max-width: 768px) {
        h1 {
            font-size: 3rem;
        }  
    }
    /* PHONE */
    @media (max-width: 480px) {
        h1 {
            font-size: 2rem;
        }
    }

</style>