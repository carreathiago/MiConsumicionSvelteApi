<script>
import Api from "../Api.svelte";
</script>

<main>
    <h1>Datos de usuarios:</h1>
    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>Nombre</th>
                <th>Email</th>
                <th>Legajo</th>
                <th>Contraseña</th>
                <th>App</th>
                <th>Rol</th>
                <th>Estado</th>
            </tr>
        </thead>
    </table>
    <Api />
</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Exo+2&display=swap');
h1 {
    text-align: center;
    font-family: 'Exo 2', sans-serif;
}
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