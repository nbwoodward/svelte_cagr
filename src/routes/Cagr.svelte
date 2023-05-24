<script lang="ts">
  let startingAmount = "10,000"
  let endingAmount = "20,000"
  let years = "7"

  const stringToInt = (val: string) => parseInt(val.replace(/[^0-9\.]/g,''))

	const calculateCAGR = (startingAmount: string, endingAmount: string, years: string) => {

    const start = stringToInt(startingAmount)
    const end = stringToInt(endingAmount)
    const yr = stringToInt(years)

		const cagr = (end / start) ** (1 / yr) - 1;

		return (cagr * 100).toFixed(2);
	}

  const clean = (val) => {
    return val
  }

  const handleChange = () => {
    startingAmount = String(stringToInt(startingAmount).toLocaleString('en-US'))
    endingAmount = String(stringToInt(endingAmount).toLocaleString('en-US'))
    years = String(stringToInt(years).toLocaleString('en-US'))
  }


</script>

<div class="cagr-calculator">
	<div class="container">
		<label for="startingAmount">Starting Amount</label>
    <input class="startingAmount" bind:value={startingAmount} on:input={handleChange}/>
	</div>
	<div class="container">
		<label for="startingAmount">Ending Amount</label>
    <input class="startingAmount" bind:value={endingAmount} on:input={handleChange}/>
	</div>
	<div class="container">
		<label for="startingAmount">Years</label>
    <input class="startingAmount" bind:value={years} on:input={handleChange}/>
	</div>
	<div class="cagr">
    <h3>CAGR:</h3> <h3>{calculateCAGR(startingAmount, endingAmount, years)}%</h3>
	</div>
</div>

<style>
	.cagr-calculator {
		display: flex;
		margin: 1rem 0;
    flex-direction:column;
    text-align:center;
	}

	.container {
		display:flex;
		flex-direction:row;
		align-items: end;
    margin-top:10px;
    justify-content: space-between;
	}

	input{
    font-size: 120%;
    width: 200px;
		border: 0;
		border: 0;
		border-bottom: 1px solid #eee;
		background:inherit;
		padding-bottom:5px;
    text-align:right;
  }

  input:focus-visible {
    outline: 0;
  }

  label {
    padding-right:15px;
    padding-bottom:5px;
  }

  .cagr {
    margin:0;
    display:flex;
    flex-direction: row;
    justify-content: space-between;
  }
</style>
