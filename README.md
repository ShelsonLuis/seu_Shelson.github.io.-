<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <title>Lista de Tarefas</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f2f5;
      display: flex;
      justify-content: center;
      padding-top: 50px;
    }

    .app {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 300px;
    }

    h2 {
      text-align: center;
      color: #333;
    }

    input[type="text"] {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }

    button {
      width: 100%;
      padding: 10px;
      background-color: #28a745;
      border: none;
      border-radius: 6px;
      color: white;
      font-size: 16px;
      cursor: pointer;
    }

    button:hover {
      background-color: #218838;
    }

    ul {
      list-style: none;
      padding: 0;
    }

    li {
      background: #f8f9fa;
      margin-top: 5px;
      padding: 10px;
      border-radius: 6px;
      display: flex;
      justify-content: space-between;
    }

    .delete {
      color: red;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="app">
    <h2>Lista de Tarefas</h2>
    <input type="text" id="tarefa" placeholder="Digite uma tarefa...">
    <button onclick="adicionarTarefa()">Adicionar</button>
    <ul id="lista"></ul>
  </div>

  <script>
    function adicionarTarefa() {
      const input = document.getElementById("tarefa");
      const texto = input.value.trim();
      if (texto === "") return;

      const li = document.createElement("li");
      li.innerHTML = `${texto} <span class="delete" onclick="removerTarefa(this)">×</span>`;
      document.getElementById("lista").appendChild(li);

      input.value = "";
    }

    function removerTarefa(elemento) {
      elemento.parentElement.remove();
    }
  </script>
</body>
</html>
