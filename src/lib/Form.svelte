<script>
  let weight;
  let height;
  let name;

  $: bmi = (weight / Math.pow(height, 2)) * 10000;

  const handleSubmit = () => {
    alert(`${name}seu Bmi é de ${bmi.toFixed(3)}`);
  };
</script>

<form action="#">
  <div class="input-control">
    <label for="name">Name: </label>
    <input autocomplete="off" type="text" id="name" bind:value={name} />
  </div>
  <div class="input-control">
    <label for="weight">Weight: </label>
    <input
      type="number"
      bind:value={weight}
      placeholder="Peso em KG"
      inputmode="numeric"
      id="weigth"
    />
  </div>
  <div class="input-control">
    <label for="height">Height: </label>
    <input
      type="number"
      bind:value={height}
      placeholder="Altura em metros"
      inputmode="numeric"
      id="height"
    />
  </div>
  <button id="btn_calculate" on:click={handleSubmit}>Calculate</button>
</form>
