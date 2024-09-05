<script>
    export let data // dit export statement zorgt ervoor dat de data van de pagina beschikbaar is in deze component
    import Card from "$lib/Card.svelte"
</script>

<main>
    <h1>Squad page</h1>
    <section>
      {#each data.persons as person}
        <Card
            name = {person.name}
            avatar = {person.avatar}
            prefix = {person.prefix}
            surname = {person.surname}
        />
      {/each}
    </section>
</main>

<style>
    section {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
    main{
        text-align: center;
    }
    h1{
        color: #fde9ff;
  font-weight: 900;
  text-transform: uppercase;
  font-size: clamp(3rem, 10vw, 6rem);
  line-height: 0.75em;
  text-align: center;
  text-shadow: 3px 1px 1px #0526429c, 2px 2px 1px #e916fb, 4px 2px 1px #4af7ff, 3px 3px 1px #165bfb, 5px 3px 1px #4af7ff, 4px 4px 1px #ff00ff, 6px 4px 1px #4af7ff, 5px 5px 1px #165bfb, 7px 5px 1px #4af7ff, 6px 6px 1px #ff00ff, 8px 6px 1px #4af7ff, 7px 7px 1px #165bfb, 9px 7px 1px #4af7ff;
    }
</style>