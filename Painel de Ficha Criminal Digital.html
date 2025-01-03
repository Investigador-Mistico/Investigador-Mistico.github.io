<html><head><base href="."><meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sistema de Cadastro Criminal</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<style>
  body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #1a237e 0%, #283593 100%);
    margin: 0;
    min-height: 100vh;
  }

  .welcome-screen {
    text-align: center;
    padding: 50px 20px;
    color: white;
    animation: fadeIn 1s ease-in;
    background: rgba(0,0,0,0.1);
    backdrop-filter: blur(5px);
    border-radius: 15px;
    margin: 50px auto;
    max-width: 800px;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .welcome-screen h1 {
    font-size: 2.5em;
    margin-bottom: 20px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  }

  .badge-icon {
    width: 120px;
    height: 120px;
    fill: white;
    margin-bottom: 30px;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
  }

  .main-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
  }

  .action-buttons {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 30px;
  }

  .modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    z-index: 1000;
    animation: fadeIn 0.3s ease-out;
  }

  .modal-content {
    position: relative;
    background: linear-gradient(to bottom, #ffffff, #f8f9fa);
    width: 90%;
    max-width: 900px;
    margin: 20px auto;
    padding: 30px;
    border-radius: 12px;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: 0 8px 32px rgba(0,0,0,0.15);
    animation: slideIn 0.4s ease-out;
  }

  @keyframes slideIn {
    from { transform: translateX(100%); opacity: 0; }
    to { transform: translateX(0); opacity: 1; }
  }

  @keyframes fadeOut {
    from { transform: translateX(0); opacity: 1; }
    to { transform: translateX(100%); opacity: 0; }
  }

  .close-btn {
    position: absolute;
    right: 20px;
    top: 20px;
    font-size: 24px;
    cursor: pointer;
    color: #666;
    transition: color 0.3s;
  }

  .close-btn:hover {
    color: #1a237e;
  }

  .form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 25px;
    background: rgba(255,255,255,0.9);
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  }

  .photo-upload {
    grid-column: 1;
    grid-row: span 3;
  }

  .photo-preview {
    width: 200px;
    height: 250px;
    border: 2px dashed #1a237e;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 15px;
    background: #f8f9fa;
    border-radius: 8px;
    transition: all 0.3s;
  }

  .photo-preview:hover {
    border-color: #283593;
    background: #f0f2f5;
  }

  .btn {
    background: #1a237e;
    color: white;
    padding: 12px 25px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 16px;
    transition: all 0.3s ease;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .btn:hover {
    background: #283593;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(26,35,126,0.3);
  }

  .history-icon {
    position: fixed;
    right: 30px;
    bottom: 30px;
    background: white;
    padding: 15px;
    border-radius: 50%;
    box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    cursor: pointer;
    transition: all 0.3s;
  }

  .history-icon:hover {
    transform: scale(1.1);
    box-shadow: 0 6px 16px rgba(0,0,0,0.3);
  }

  .form-group {
    margin-bottom: 20px;
  }

  label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
    color: #1a237e;
  }

  input, textarea, select {
    width: 100%;
    padding: 10px;
    border: 2px solid #e0e0e0;
    border-radius: 6px;
    box-sizing: border-box;
    transition: all 0.3s;
  }

  input:focus, textarea:focus, select:focus {
    border-color: #1a237e;
    outline: none;
    box-shadow: 0 0 0 3px rgba(26,35,126,0.1);
  }

  .history-list {
    display: none;
    position: fixed;
    right: 30px;
    bottom: 90px;
    background: white;
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.15);
    max-width: 350px;
    animation: slideUp 0.3s ease-out;
  }

  @keyframes slideUp {
    from { transform: translateY(20px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
  }

  .history-item {
    display: flex;
    align-items: center;
    padding: 12px;
    border-bottom: 1px solid #eee;
    cursor: pointer;
    transition: all 0.3s;
  }

  .history-item:hover {
    background: #f5f5f5;
    transform: translateX(5px);
  }

  .history-item a {
    text-decoration: none;
    color: #1a237e;
  }
</style>
</head>
<body>
  <div class="welcome-screen" id="welcomeScreen">
    <svg class="badge-icon" viewBox="0 0 24 24">
      <path fill="currentColor" d="M12,1L3,5V11C3,16.55 6.84,21.74 12,23C17.16,21.74 21,16.55 21,11V5L12,1M12,5A3,3 0 0,1 15,8A3,3 0 0,1 12,11A3,3 0 0,1 9,8A3,3 0 0,1 12,5M17.13,17C15.92,18.85 14.11,20.24 12,20.92C9.89,20.24 8.08,18.85 6.87,17C6.53,16.5 6.24,16 6,15.47C6,13.82 8.71,12.47 12,12.47C15.29,12.47 18,13.79 18,15.47C17.76,16 17.47,16.5 17.13,17Z"/>
    </svg>
    <h1>Sistema de Registro Criminal</h1>
    <p>Base de Dados de investigasão - Acesso Restrito</p>
    <div class="action-buttons">
      <button class="btn" onclick="openModal()">Nova Ficha Criminal</button>
      <button class="btn" onclick="toggleHistory()">Hist&#xf3;rico</button>
    </div>
  </div>

  <div class="modal" id="criminalModal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal()">&#xd7;</span>
      <h2>Cadastro de Ficha Criminal</h2>
      <form id="criminalForm">
        <div class="form-grid">
          <div class="photo-upload">
            <label>Foto do Suspeito</label>
            <div class="photo-preview" id="photoPreview">
              <img id="previewImage" style="display:none; max-width: 100%; max-height: 100%;">
              <span id="uploadText">Clique para adicionar foto</span>
            </div>
            <input type="file" id="photoInput" accept="image/*" style="display: none;">
            <button type="button" class="btn" onclick="document.getElementById(&apos;photoInput&apos;).click()">
              Carregar Foto
            </button>
          </div>

          <div class="form-group">
            <label>Nome Completo</label>
            <input type="text" id="nome" required>
          </div>

          <div class="form-group">
            <label>Alcunha/Vulgo</label>
            <input type="text" id="alcunha">
          </div>

          <div class="form-group">
            <label>Data de Nascimento</label>
            <input type="date" id="nascimento" required>
          </div>

          <div class="form-group">
            <label>RG</label>
            <input type="text" id="rg" required>
          </div>

          <div class="form-group">
            <label>CPF</label>
            <input type="text" id="cpf" required>
          </div>

          <div class="form-group">
            <label>Crimes Cometidos</label>
            <textarea id="crimes" required></textarea>
          </div>
        </div>

        <div style="text-align: center; margin-top: 20px;">
          <button type="submit" class="btn">Gerar Ficha Criminal</button>
        </div>
      </form>
    </div>
  </div>

  <div class="history-icon" onclick="toggleHistory()">
    <svg width="24" height="24" viewBox="0 0 24 24">
      <path fill="#1a237e" d="M13 3c-4.97 0-9 4.03-9 9H1l3.89 3.89.07.14L9 12H6c0-3.87 3.13-7 7-7s7 3.13 7 7-3.13 7-7 7c-1.93 0-3.68-.79-4.94-2.06l-1.42 1.42C8.27 19.99 10.51 21 13 21c4.97 0 9-4.03 9-9s-4.03-9-9-9zm-1 5v5l4.28 2.54.72-1.21-3.5-2.08V8H12z"/>
    </svg>
  </div>

  <div class="history-list" id="historyList">
    <h3>Hist&#xf3;rico de Fichas</h3>
    <div id="historyItems"></div>
  </div>

  <script>function openModal() {
  document.getElementById('criminalModal').style.display = 'block';
}
function closeModal() {
  document.getElementById('criminalModal').style.display = 'none';
}
function toggleHistory() {
  const historyList = document.getElementById('historyList');
  historyList.style.display = historyList.style.display === 'none' ? 'block' : 'none';
}
const photoInput = document.getElementById('photoInput');
const previewImage = document.getElementById('previewImage');
const uploadText = document.getElementById('uploadText');
const form = document.getElementById('criminalForm');
function showNotification(message) {
  const notification = document.createElement('div');
  notification.style.cssText = `
    position: fixed;
    top: 20px;
    right: 20px;
    background: #4CAF50;
    color: white;
    padding: 15px 25px;
    border-radius: 5px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    z-index: 1100;
    animation: slideIn 0.3s ease-out;
  `;
  notification.textContent = message;
  document.body.appendChild(notification);
  setTimeout(() => {
    notification.style.animation = 'fadeOut 0.3s ease-out';
    setTimeout(() => notification.remove(), 300);
  }, 3000);
}
photoInput.addEventListener('change', function (e) {
  const file = e.target.files[0];
  if (file) {
    const reader = new FileReader();
    reader.onload = function (e) {
      previewImage.style.display = 'block';
      previewImage.src = e.target.result;
      uploadText.style.display = 'none';
    };
    reader.readAsDataURL(file);
  }
});
form.addEventListener('submit', async function (e) {
  e.preventDefault();
  const {
    jsPDF
  } = window.jspdf;
  const doc = new jsPDF();
  doc.setGState(new doc.GState({
    opacity: 0.1
  }));
  doc.setFillColor(26, 35, 126);
  doc.rect(65, 100, 80, 80, 'F');
  doc.setGState(new doc.GState({
    opacity: 1
  }));
  doc.setFillColor(26, 35, 126);
  doc.rect(0, 0, 210, 40, 'F');
  doc.setTextColor(255, 255, 255);
  doc.setFontSize(24);
  doc.setFont(undefined, 'bold');
  doc.text('FICHA CRIMINAL', 105, 25, {
    align: 'center'
  });
  doc.setFontSize(12);
  doc.text('REGISTRO de INVESTIGASÃO CONFIDENCIAL', 105, 35, {
    align: 'center'
  });
  doc.setTextColor(0, 0, 0);
  doc.setFontSize(14);
  const startY = 60;
  const lineHeight = 12;
  doc.setDrawColor(26, 35, 126);
  doc.setLineWidth(0.5);
  doc.line(20, startY - 5, 190, startY - 5);
  doc.setFont(undefined, 'bold');
  doc.text('DADOS PESSOAIS', 20, startY);
  doc.setFont(undefined, 'normal');
  doc.text(`Nome Completo: ${document.getElementById('nome').value}`, 20, startY + lineHeight * 2);
  doc.text(`Alcunha/Vulgo: ${document.getElementById('alcunha').value}`, 20, startY + lineHeight * 3);
  doc.text(`Data de Nascimento: ${document.getElementById('nascimento').value}`, 20, startY + lineHeight * 4);
  doc.text(`RG: ${document.getElementById('rg').value}`, 20, startY + lineHeight * 5);
  doc.text(`CPF: ${document.getElementById('cpf').value}`, 20, startY + lineHeight * 6);
  doc.line(20, startY + lineHeight * 7, 190, startY + lineHeight * 7);
  doc.setFont(undefined, 'bold');
  doc.text('HISTÓRICO CRIMINAL', 20, startY + lineHeight * 8);
  doc.setFont(undefined, 'normal');
  const crimes = doc.splitTextToSize(document.getElementById('crimes').value, 160);
  doc.text(crimes, 20, startY + lineHeight * 9);
  if (previewImage.src) {
    try {
      doc.addImage(previewImage.src, 'JPEG', 130, startY, 60, 75);
      doc.rect(130, startY, 60, 75);
    } catch (e) {
      console.error('Error adding image to PDF:', e);
    }
  }
  doc.setDrawColor(26, 35, 126);
  doc.line(20, 270, 190, 270);
  doc.setFontSize(10);
  doc.setTextColor(128, 128, 128);
  doc.text(`Documento gerado em ${new Date().toLocaleDateString()} às ${new Date().toLocaleTimeString()}`, 105, 280, {
    align: 'center'
  });
  const pdfBlob = doc.output('blob');
  const pdfUrl = URL.createObjectURL(pdfBlob);
  const historyItem = document.createElement('div');
  historyItem.className = 'history-item';
  historyItem.innerHTML = `
        <span>${document.getElementById('nome').value}</span>
        <a href="${pdfUrl}" download="ficha_criminal.pdf" style="margin-left: auto;">📥</a>
      `;
  document.getElementById('historyItems').appendChild(historyItem);
  showNotification('Ficha criminal gerada com sucesso!');
  closeModal();
});</script>
</body>
</html>
