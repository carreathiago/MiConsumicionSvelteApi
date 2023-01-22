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
      <tbody>
                <td>{Dato.id}</td>
                <td>{Dato.name}</td>
                <td>{Dato.email}</td>
                <td>{Dato.legajo}</td>
                <td>{Dato.password}</td>
                <td>{Dato.app}</td>
                <td>{Dato.role}</td>
                <td>{Dato.status}</td>
              </tbody>
                </table>
    {:else}
    <p>Cargando datos...</p>
    {/each}
</div>
<style>
  
  @import url('https://fonts.googleapis.com/css2?family=Exo:wght@200&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Exo:wght@500&display=swap');
  
table {
  font-family: 'Exo', sans-serif;
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

table td {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: .625em;
  text-align: center;
  font-size: .85em;
  letter-spacing: .1em;
  text-transform: uppercase;
}

@media screen and (max-width: 600px) {
  table {
    border: 0;
  }
  
  table tbody {
    border: none;
    clip: rect(0 0 0 0);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
  }
  
}
</style>