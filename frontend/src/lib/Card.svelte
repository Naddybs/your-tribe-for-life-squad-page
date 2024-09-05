<!--  export gebruikt om de data van de parent component te tonen -->
<script>
  export let name;
  export let avatar;
  export let prefix;
  export let surname;
</script>

<!-- props gebruikt om te refereren naar de data van de parent component -->
<main class="card">
  <section class="card-inner">
    <article class="card-front">
      <h2>{name}</h2>
      <img src={avatar} alt="Profile picture of {name}" />
      <h3>{prefix}{surname}</h3>
    </article>
    <div class="card-back">
      <img src="/pokemon.png" alt="Pokémon background" />
    </div>
  </section>
</main>

<!-- kaarten scoped styling -->
<style>
  .card {
    width: 200px;
    height: 300px;
    perspective: 1000px;
    margin: 1em;
    position: relative;
    border-radius: 10px;
    overflow: hidden;
    background: linear-gradient(135deg, rgba(8, 234, 233, 0.82), #ff00ff);
    box-shadow: 0 4px 20px #ed66d8;
    border: solid 5px rgba(0, 0, 255, 0.19);
    transition: transform 0.6s ease, box-shadow 0.6s ease, margin 0.6s ease;
  }

  .card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transform-style: preserve-3d;
    cursor: pointer;
    transition: transform 0.6s ease;
  }

  .card:hover {
    transform: scale(1.2);
    box-shadow: 0 8px 30px rgba(246, 255, 142, 1); 
    z-index: 2;
    margin: 2em;
  }

  .card:hover .card-inner {
    transform: rotateY(180deg);
  }

  .card-front {
    background-color: rgba(255, 255, 255, 0.69);
    color: black;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 1;
  }

  img {
    border-radius: 50%;
    width: 150px;
    height: 150px;
    object-fit: cover;
    margin-bottom: 10px;
  }

  .card-back {
    transform: rotateY(180deg);
    background-color: #333;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card-back img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
  }

  .card-front, .card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    border-radius: 0.5em;
  }

  /* Kleur hologram effect */
  .card::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: conic-gradient(from 180deg, #ff00ff73, #00ffff99, #ea0b6d85, #00ff006e, #0000ff82, #ff00ff82);
    z-index: 1;
    transform: rotate(90deg);
    mix-blend-mode: overlay;
    pointer-events: none;
  }

  /* Lichtgevende effect */
  .card::after {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle at 50% 50%, rgba(236, 249, 181, 0.57), transparent);
    z-index: 0;
    transition: opacity 0.6s ease, transform 0.6s ease;
    opacity: 0;
    pointer-events: none;
  }

  .card:hover::after {
    opacity: 0.5;
    transform: rotate(45deg);
  }
</style>
