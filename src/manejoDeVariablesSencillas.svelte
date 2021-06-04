<script>
	//export let name;
	let contador = 0;
	const aumentar = () =>{
		contador ++
		
	}
	let textColor = 'text-primary';
	$: doble = contador *3;
	$: mensaje = contador > 6  ? 'esto es mayor a 6':'es menor a 5'
	$: if (contador > 5){
			textColor = 'text-danger'}
</script>

<main>
	<h1 class={textColor}>Contador:  {contador} </h1>
	<button on:click = {aumentar}> Aumentar</button>
	<h3>{mensaje}</h3>
	<h2>contador por 3: {doble}</h2>
	
</main>

<style>
	.text-primary{
		color:blue;
	}
	.text-danger{
		color:brown;
	}
</style>