<script>
  let weight;
  let height;
  let name;

  $:bmi =  (weight /(Math.pow(height,2))*10000);
  
</script>

<body>
  <div id="container">
    <header>
      <h1>BMI Calculator</h1>
    </header>
    <main>
      <h2>Type your data</h2>
      <form action="#">
        <div class="input-control">
          <label for="name">Name: </label>
          <input autocomplete="off" type="text" id="name" bind:value={name} />
        </div>
        <div class="input-control">
          <label for="weight">Weight: </label>
          <input type="number" bind:value={weight} placeholder="Peso em KG" inputmode="numeric" id="weigth">
        </div>
        <div class="input-control">
          <label for="height">Height: </label>
          <input type="number" bind:value={height} placeholder="Altura em metros" inputmode="numeric" id="height">
        </div>
        <button id="btn_calculate">Calculate</button>
      </form>

      {#if weight && height}
      <div>	
         <h1>{name} seu bmi é</h1>
         <h2>{bmi.toFixed(6)}</h2>
      </div>
      {/if}
    </main>
    <footer>
      <p>FXP Software @ 2023</p>
    </footer>
  </div>
</body>

<style>



label{
  margin-bottom:10px;
}


button, input {
  width:100%;
}

input::placeholder {
  color:#ccc;
}
</style>