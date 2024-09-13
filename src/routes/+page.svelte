<script>
    export let data
  
    function checkAvatarImage (avatar) {
      if (avatar.includes('https')) {
        return true
      } 
  
      return false
    }
    console.log(data);

    function flip() {
        console.log('test')
		count += 1;
	}

</script>

<style>
    h1 {
        font-family: "Expletus Sans", sans-serif;
        text-transform: uppercase;
        letter-spacing: 1.2rem;
        font-size: 3.8rem;
        font-weight: 500;
        color: #3797E7;
    }
    h2 {
        font-size: 2rem;
        text-transform: lowercase;
        font-weight: 100;
    }
    main {
        min-height: 100vh;
        display: grid;
        place-items: center;
        font-family: "Roboto", sans-serif;
        background: #fbf7f1;
        perspective: 1000px;
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
        color: black;
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
</style>

<main id="cardContainer">
    <article class="cardFront">
        <section>
            <ul>
                <li><a href="">Mail</a></li>
                <li><a href="">Github</a></li>
                <li><a href="">Insta</a></li>
            </ul>
    
            <button on:click={flip}></button>
        </section>

        <section>
            <h1>{data.persons.name}</h1>
            <h2>{data.persons.surname}</h2>
        </section>
    </article>

    <article class="cardBack">
        <p>{data.persons.bio}</p>
    </article>
</main>
