<script>
    export let data
  
    function checkAvatarImage (avatar) {
      if (avatar.includes('https')) {
        return true
      } 
  
      return false
    }
    console.log(data);
  </script>

<style>
    * {
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }
    section {
        width: 100%;
        height: 100vh;
        background-color: cornflowerblue;

        display: flex;
        justify-content: center;
        align-items: center;
    }
    section article h1 {
        font-size: 2.5rem;
        color: bisque;
    }
</style>

<section>
    <article>
        <h1>{data.persons.name}</h1>
        <h2>{data.persons.surname}</h2>
    </article>
</section>
<!-- <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p> -->

