<script>
  export let name;
  export let role;
  export let imageUrl;
</script>

<div class="card">
  <div class="card-inner">
    <div class="card-front">
      <h2>{name}</h2>
      <img src={imageUrl} alt="Profile picture of {name}" />
      <p>{role}</p>
    </div>
    <div class="card-back">
      <!-- Dit is de achtergrond van de kaart, bijvoorbeeld de Pokémon achterkant -->
      <img src="/pokemon.png" alt="Pokémon background" />
    </div>
  </div>
</div>

<style>
.card {
  width: 150px;
  height: 200px;
  perspective: 1000px;
  margin: 1em;
}

.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  cursor: pointer;
}

.card:hover .card-inner {
  transform: rotateY(180deg);
}

.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  border-radius: 10px;
}

.card-front {
  background-color: pink;
  color: black;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
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

img {
  border-radius: 50%;
  width: 80px;
  height: 80px;
  object-fit: cover;
  margin-bottom: 10px;
}
</style>
