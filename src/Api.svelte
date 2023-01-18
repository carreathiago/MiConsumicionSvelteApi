<script>
    import {onMount} from "svelte";
    import { each } from "svelte/internal";
    
    let Datos = [];

    onMount(async () =>{
const response = await fetch("http://10.10.32.12:4000/api/v1/users");
Datos = await response.json();
    });
</script>

<div class="Datos">
    {#each Datos as Dato}
    <table>
    <thead>
        <tr>
            <th>{Dato.id}</th>
                <th>{Dato.name}</th>
                <th>{Dato.email}</th>
                <th>{Dato.legajo}</th>
                <th>{Dato.password}</th>
                <th>{Dato.app}</th>
                <th>{Dato.role}</th>
                <th>{Dato.status}</th>
            </tr>
            </thead>
                </table>
    {:else}
    <p>Cargando datos...</p>
    {/each}
</div>
<style>
    table {
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

table tr {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: .35em;
}

table th{
  padding: .625em;
  text-align: center;
}

table th {
  font-size: .85em;
  letter-spacing: .1em;
  text-transform: uppercase;
}

@media screen and (max-width: 600px) {
  table {
    border: 0;
  }
  
  table thead {
    border: none;
    clip: rect(0 0 0 0);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
  }
  
  table tr {
    border-bottom: 3px solid #ddd;
    display: block;
    margin-bottom: .625em;
  }
  
}
</style>