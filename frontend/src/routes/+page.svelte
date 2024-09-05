<script>
  import Card from '$lib/cards.svelte';

  // Hardcoded gegevens voor de klasgenoten
  let classmates = [
    { name: "Nadira", role: "Designer", imageUrl: "https://via.placeholder.com/100" },
    { name: "Latoya", role: "Developer", imageUrl: "https://via.placeholder.com/100" },
    { name: "Daan", role: "Project Manager", imageUrl: "https://via.placeholder.com/100" },
    { name: "Jaymar", role: "Creative Thinker", imageUrl: "https://via.placeholder.com/100" },
    { name: "Kaan", role: "Developer", imageUrl: "https://via.placeholder.com/100" }
  ];
</script>

<!-- Container voor alle kaarten -->
<ul class="cards-container">
 {#each classmates as classmate}
    <li>
      <Card 
        name={classmate.name} 
        role={classmate.role} 
        imageUrl={classmate.imageUrl} 
      />
    </li>
 {/each}
</ul>

<style>
  .cards-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px; /* Zorgt voor ruimte tussen de kaarten */
    padding: 0;
  }

  li {
    list-style: none; /* Verwijdert de standaard lijststijl */
  }
</style>
