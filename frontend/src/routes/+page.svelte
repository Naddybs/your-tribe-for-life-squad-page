<script>
    export let data // dit export statement zorgt ervoor dat de data van de pagina beschikbaar is in deze component
</script>

<main>
    {#each data.persons as person}
    <h2>{person.name}</h2>
    <img src={person.avatar} alt="Profile picture of {person.name}" />
    <h3>{person.prefix} {person.surname}</h3>
    {/each}
</main>
