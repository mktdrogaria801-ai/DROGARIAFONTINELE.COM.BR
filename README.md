<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cadastro - Drogaria Fontinele</title>
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      background-color: #f4f6f9;
      color: #333;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 40px;
    }
    .logo {
      width: 250px;
      margin-bottom: 20px;
    }
    .form-container {
      background: #fff;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      width: 100%;
      max-width: 420px;
    }
    h1 {
      color: #0056b8;
      text-align: center;
      margin-bottom: 25px;
    }
    label {
      display: block;
      margin-bottom: 6px;
      font-weight: 600;
      color: #333;
    }
    input {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      margin-bottom: 15px;
      font-size: 15px;
    }
    button {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 8px;
      background-color: #e50019;
      color: #fff;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background-color: #c40015;
    }
    .privacy {
      font-size: 13px;
      color: #555;
      text-align: center;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <img src="LOGO%20DROGARIA%20FONTINELE%20VA.png" alt="Drogaria Fontinele" class="logo">
  <div class="form-container">
    <h1>Cadastro de Cliente</h1>
    <form id="cadastroForm">
      <label for="nome">Nome completo</label>
      <input type="text" id="nome" name="nome" required>

      <label for="cpf">CPF</label>
      <input type="text" id="cpf" name="cpf" required maxlength="14" placeholder="000.000.000-00">

      <label for="endereco">Endereço</label>
      <input type="text" id="endereco" name="endereco" required>

      <label for="telefone">Telefone</label>
      <input type="tel" id="telefone" name="telefone" required placeholder="(99) 99999-9999">

      <button type="button" onclick="enviarWhatsApp()">Enviar pelo WhatsApp</button>
    </form>
    <p class="privacy">Seus dados são tratados com segurança e usados apenas para cadastro.</p>
  </div>

  <script>
    function enviarWhatsApp() {
      const nome = document.getElementById('nome').value.trim();
      const cpf = document.getElementById('cpf').value.trim();
      const endereco = document.getElementById('endereco').value.trim();
      const telefone = document.getElementById('telefone').value.trim();

      if (!nome || !cpf || !endereco || !telefone) {
        alert('Por favor, preencha todos os campos antes de enviar.');
        return;
      }

      const mensagem = `Olá, Drogaria Fontinele! Quero realizar meu cadastro.%0A%0A` +
        `*Nome:* ${nome}%0A` +
        `*CPF:* ${cpf}%0A` +
        `*Endereço:* ${endereco}%0A` +
        `*Telefone:* ${telefone}`;

      const numero = '5599984632902'; // número da drogaria com DDI e DDD
      const url = `https://wa.me/${numero}?text=${mensagem}`;

      window.open(url, '_blank');
    }
  </script>
</body>
</html>
