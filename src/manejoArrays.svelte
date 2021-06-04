<script>
	let cursos = ['curso 1','curso 2','curso 3']
	let numeros = [1,5,8,12,9,6]
	const addNumero = () => {
		 let num = Math.floor(Math.random() * (20 - 1)) + 1 ;
		// numeros.push(num)
		numeros = [...numeros, num]

	}
</script>

<main class="container">
	<h1>cursos</h1>
	<ul>
		{#each cursos as curso, index}
			<li>{index+1} - {curso}</li>
		{/each}
	</ul>
	
	<ul>
		{#if numeros.length >10}
			 <h1> lo picaste demasiado</h1>
			 {:else}
			 <button on:click={addNumero} class="btn btn-primary">Agregar numero</button>
			 <h4> pica el boton</h4>
		{/if}
		{#each numeros as numero}
			<li>
				{numero}
			</li>
		{/each}
	</ul>
 </main>