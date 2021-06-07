<script>
    import { loop_guard } from "svelte/internal";

    let texto = "";
    let numero = 0;
    let rango = 1;
    let check = false;
    let newFruta = "";
    let frutas = ["mandarina", "mango"];
    let verduras = ["tomate", "papa", "chile"];
    const addFruta = () => {
        frutas = [...frutas, newFruta];
    };
    let radio = "";
    let arrayResultado = [];
    $: console.log(arrayResultado);
</script>

<main class="container-fluid">
    <h1>Bindings</h1>
    <input type="text" bind:value={texto} />
    <p>{texto}</p>
    <input type="number" bind:value={numero} />
    <p>{numero}</p>
    <input type="range" bind:value={rango} min="0" max="20" />
    <p>{rango}</p>
    <input type="checkbox" bind:checked={check} />
    <p>{check} deseas aceptar las politicas</p>
    <button disabled={!check}>enviar</button>
    <h2>Lista de frutas</h2>
    <ul>
    {#each frutas as fruta}
        <li>
        {fruta}
        </li>
    {/each}
    </ul>
    <input id="inputFruta" type="text" bind:value={newFruta} />
    <button on:click={addFruta}>agregar fruta</button>

    <h2>Lista de verduras 2</h2>
    {#each verduras as verdura}
        <input type="checkbox" value={verdura} bind:group={arrayResultado} />
        {verdura}
    {/each}
    <p>arrayResultado: {arrayResultado}</p>

    <h2>Lista de verduras</h2>
        {#each verduras as verdura}
    <input type="radio" value={verdura} bind:group={radio} />
    {verdura}
    {/each}
    <p>{radio}</p>
</main>
