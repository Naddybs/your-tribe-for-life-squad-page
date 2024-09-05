<script>
    export let data // dit export statement zorgt ervoor dat de data van de pagina beschikbaar is in deze component
    import Card from "$lib/Card.svelte"
</script>

<main>
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
</style>