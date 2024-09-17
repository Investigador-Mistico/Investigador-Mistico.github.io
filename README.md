# PainelFichav1-
Esse painel foi criado para gerar fichas criminais para denúncias, use com sabedoria.

<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <base href="https://investigacaodigital.gov/ficha-criminal/">
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Painel de Ficha Criminal Digital</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
  <style>
    body {
      background-color: #0d0d2b;
      color: #e0e0e0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    .container {
      background-color: #1f2a48;
      border-radius: 20px;
      padding: 30px;
      margin-top: 50px;
      box-shadow: 0 0 25px rgba(0, 255, 255, 0.3);
    }
    h1 {
      color: #00ffff;
      text-align: center;
      margin-bottom: 30px;
      text-transform: uppercase;
      letter-spacing: 4px;
    }
    .form-control {
      background-color: #0f3460;
      border: none;
      color: #e0e0e0;
      margin-bottom: 15px;
    }
    .btn-primary {
      background-color: #00ffff;
      border: none;
      color: #0d0d2b;
      font-weight: bold;
      transition: all 0.3s ease;
    }
    .btn-primary:hover {
      background-color: #00d4b7;
      transform: scale(1.1);
    }
    #notification {
      position: fixed;
      top: 20px;
      right: 20px;
      background-color: #00ffff;
      color: #0d0d2b;
      padding: 10px 20px;
      border-radius: 50px;
      display: none;
      z-index: 1000;
    }
    #fichasIcon {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background-color: #00ffff;
      color: #0d0d2b;
      width: 70px;
      height: 70px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      font-size: 24px;
      box-shadow: 0 0 15px rgba(0, 255, 255, 0.5);
    }
    #fichasCount {
      position: absolute;
      top: -10px;
      right: -10px;
      background-color: #ff0055;
      color: white;
      border-radius: 50%;
      width: 25px;
      height: 25px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 14px;
      font-weight: bold;
    }
    #fichasModal .modal-content {
      background-color: #1f2a48;
      color: #e0e0e0;
    }
    #fichasModal .modal-header {
      border-bottom: 1px solid #0f3460;
    }
    #fichasModal .modal-footer {
      border-top: 1px solid #0f3460;
    }
    #fichasModal .close {
      color: #e0e0e0;
    }
    #fichasList {
      list-style-type: none;
      padding: 0;
    }
    #fichasList li {
      background-color: #0f3460;
      margin-bottom: 10px;
      padding: 10px;
      border-radius: 5px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    #fichasList li button {
      background-color: #00ffff;
      border: none;
      color: #0d0d2b;
      padding: 5px 10px;
      border-radius: 3px;
      cursor: pointer;
    }
    #detalhesModal .modal-content {
      background-color: #1f2a48;
      color: #e0e0e0;
    }
    #foto-preview {
      max-width: 100%;
      max-height: 200px;
      margin-top: 10px;
    }
    @media (max-width: 768px) {
      h1 {
        font-size: 22px;
      }
      .container {
        padding: 15px;
        margin-top: 30px;
      }
      .btn-primary {
        font-size: 14px;
      }
      #fichasIcon {
        width: 60px;
        height: 60px;
      }
      #fichasCount {
        width: 20px;
        height: 20px;
        font-size: 12px;
      }
    }
  </style>
</head>
<body>
<div class="container">
  <h1><i class="fas fa-user-secret"></i> Painel de Ficha Criminal Digital</h1>
  <form id="fichaForm">
    <div class="mb-3">
      <label for="nome" class="form-label">Nome do Acusado</label>
      <input type="text" class="form-control" id="nome" required>
    </div>
    <div class="mb-3">
      <label for="cpf" class="form-label">CPF</label>
      <input type="text" class="form-control" id="cpf" required>
    </div>
    <div class="mb-3">
      <label for="dataNascimento" class="form-label">Data de Nascimento</label>
      <input type="date" class="form-control" id="dataNascimento" required>
    </div>
    <div class="mb-3">
      <label for="detalhes" class="form-label">Detalhes do Crime</label>
      <textarea class="form-control" id="detalhes" rows="3" required></textarea>
    </div>
    <div class="mb-3">
      <label for="provas" class="form-label">Provas</label>
      <textarea class="form-control" id="provas" rows="3" required></textarea>
    </div>
    <div class="mb-3">
      <label for="foto" class="form-label">Foto do Acusado</label>
      <input type="file" class="form-control" id="foto" accept="image/*">
      <img id="foto-preview" src="" alt="Preview da foto do acusado" style="display: none;">
    </div>
    <button type="submit" class="btn btn-primary btn-lg w-100">Salvar Ficha e Gerar PDF</button>
  </form>
</div>

<div id="notification">Ficha salva com sucesso!</div>

<div id="fichasIcon">
  <i class="fas fa-folder"></i>
  <span id="fichasCount">0</span>
</div>

<div class="modal fade" id="fichasModal" tabindex="-1" aria-labelledby="fichasModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="fichasModalLabel">Fichas Criminais Salvas</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <ul id="fichasList"></ul>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-danger" id="limparFichas">Limpar Todas as Fichas</button>
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
      </div>
    </div>
  </div>
</div>

<div class="modal fade" id="detalhesModal" tabindex="-1" aria-labelledby="detalhesModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="detalhesModalLabel">Detalhes da Ficha Criminal</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body" id="detalhesModalBody"></div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
      </div>
    </div>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  const fichaForm = document.getElementById('fichaForm');
  const fichasIcon = document.getElementById('fichasIcon');
  const fichasCount = document.getElementById('fichasCount');
  const fichasList = document.getElementById('fichasList');
  const detalhesModalBody = document.getElementById('detalhesModalBody');
  const notification = document.getElementById('notification');
  let fichas = [];

  fichaForm.addEventListener('submit', (e) => {
    e.preventDefault();

    const ficha = {
      nome: document.getElementById('nome').value,
      cpf: document.getElementById('cpf').value,
      dataNascimento: document.getElementById('dataNascimento').value,
      detalhes: document.getElementById('detalhes').value,
      provas: document.getElementById('provas').value,
      foto: document.getElementById('foto').files[0] ? URL.createObjectURL(document.getElementById('foto').files[0]) : ''
    };

    fichas.push(ficha);
    updateFichasCount();
    showNotification('Ficha salva com sucesso!');
    fichaForm.reset();
    document.getElementById('foto-preview').style.display = 'none';
    gerarPDF(ficha);
  });

  fichasIcon.addEventListener('click', () => {
    const modal = new bootstrap.Modal(document.getElementById('fichasModal'));
    renderFichasList();
    modal.show();
  });

  document.getElementById('limparFichas').addEventListener('click', () => {
    fichas = [];
    updateFichasCount();
    renderFichasList();
  });

  function updateFichasCount() {
    fichasCount.textContent = fichas.length;
  }

  function renderFichasList() {
    fichasList.innerHTML = '';
    fichas.forEach((ficha, index) => {
      const li = document.createElement('li');
      li.innerHTML = `
        <span>${ficha.nome} - ${ficha.cpf}</span>
        <button onclick="verDetalhes(${index})">Ver Detalhes</button>
      `;
      fichasList.appendChild(li);
    });
  }

  window.verDetalhes = (index) => {
    const ficha = fichas[index];
    detalhesModalBody.innerHTML = `
      <p><strong>Nome:</strong> ${ficha.nome}</p>
      <p><strong>CPF:</strong> ${ficha.cpf}</p>
      <p><strong>Data de Nascimento:</strong> ${ficha.dataNascimento}</p>
      <p><strong>Detalhes:</strong> ${ficha.detalhes}</p>
      <p><strong>Provas:</strong> ${ficha.provas}</p>
      ${ficha.foto ? `<img src="${ficha.foto}" alt="Foto do Acusado" style="max-width: 100%; margin-top: 10px;">` : ''}
    `;
    const modal = new bootstrap.Modal(document.getElementById('detalhesModal'));
    modal.show();
  };

  function showNotification(message) {
    notification.textContent = message;
    notification.style.display = 'block';
    setTimeout(() => {
      notification.style.display = 'none';
    }, 3000);
  }

  function gerarPDF(ficha) {
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();
    
    const backgroundImage = new Image();
    backgroundImage.src = 'https://i.im.ge/2024/09/17/fv5Nbq.c40658c3a12c4283c79b08d7abe73109.jpeg';
    doc.addImage(backgroundImage, 'JPEG', 0, 0, 210, 297);
    
    doc.setFontSize(18);
    doc.text('Documento Confidencial', 20, 20);
    doc.setFontSize(12);
    doc.text(`Nome: ${ficha.nome}`, 20, 30);
    doc.text(`CPF: ${ficha.cpf}`, 20, 40);
    doc.text(`Data de Nascimento: ${ficha.dataNascimento}`, 20, 50);

    doc.setFontSize(14);
    doc.setTextColor(255, 0, 0);
    doc.text('Detalhes do Crime:', 20, 60);
    doc.setTextColor(0, 0, 0);
    doc.text(ficha.detalhes, 20, 70);

    doc.setFontSize(14);
    doc.setTextColor(255, 0, 0);
    doc.text('Provas:', 20, 80);
    doc.setTextColor(0, 0, 0);
    doc.text(ficha.provas, 20, 90);

    if (ficha.foto) {
      const img = new Image();
      img.src = ficha.foto;
      doc.addImage(img, 'JPEG', 20, 100, 50, 50);
    }

    doc.save('Ficha_Criminal.pdf');
  }
});
</script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
