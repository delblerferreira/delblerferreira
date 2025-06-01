<div align="center" style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
  <div style="
    border: 3px solid #4A90E2;
    border-radius: 15px;
    padding: 25px;
    display: inline-block;
    background: linear-gradient(135deg, #f8f9fa 0%, #ffffff 100%);
    box-shadow: 0 6px 20px rgba(0,0,0,0.12);
    max-width: 600px;
    width: 100%;
    position: relative;
    overflow: hidden;
  ">
    <!-- Efeito de partículas animadas -->
    <div style="
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: radial-gradient(circle, rgba(74,144,226,0.1) 0%, transparent 70%);
      opacity: 0.3;
      z-index: 0;
      animation: pulse 8s infinite alternate;
    "></div>
    
    <img 
      src="https://i.postimg.cc/LXRTBZXB/8G-Rede.png" 
      width="150" 
      height="150" 
      style="
        border-radius: 15px;
        border: 3px solid #4A90E2;
        display: block;
        margin: 0 auto 20px;
        box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        position: relative;
        z-index: 1;
        animation: float 6s ease-in-out infinite;
      " 
    />
    
    <h1 id="animated-name" style="
      margin: 0 0 8px 0; 
      color: #2c3e50; 
      font-size: 2.2rem;
      position: relative;
      z-index: 1;
    ">Delbler Ferreira Amancio</h1>
    
    <div id="profession-carousel" style="
      height: 30px;
      position: relative;
      overflow: hidden;
      margin: 0 auto 10px;
      max-width: 80%;
    ">
      <p class="profession-item" style="
        margin: 0; 
        color: #4A90E2; 
        font-size: 1.1rem; 
        font-weight: 500;
        font-style: italic;
        text-align: center;
        position: absolute;
        width: 100%;
        opacity: 0;
        transform: translateY(20px);
        transition: all 0.8s ease;
      ">Engenheiro Multidisciplinar</p>
      
      <p class="profession-item" style="
        margin: 0; 
        color: #4A90E2; 
        font-size: 1.1rem; 
        font-weight: 500;
        font-style: italic;
        text-align: center;
        position: absolute;
        width: 100%;
        opacity: 0;
        transform: translateY(20px);
        transition: all 0.8s ease;
      ">Desenvolvedor Full-Stack</p>
      
      <p class="profession-item" style="
        margin: 0; 
        color: #4A90E2; 
        font-size: 1.1rem; 
        font-weight: 500;
        font-style: italic;
        text-align: center;
        position: absolute;
        width: 100%;
        opacity: 0;
        transform: translateY(20px);
        transition: all 0.8s ease;
      ">Especialista em Automação</p>
    </div>
  </div>

  <!-- RESTANTE DO CÓDIGO PERMANECE IGUAL -->
  ## 🚀 Portfólio Profissional
  ---
  <div style="display: flex; flex-wrap: wrap; gap: 20px; margin-top: 20px; font-family: Arial, sans-serif; color: #2c3e50;">
    <!-- ... conteúdo existente ... -->
  </div>

  <!-- ... restante do seu código ... -->

  <style>
    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0px); }
    }
    
    @keyframes pulse {
      0% { transform: scale(1); opacity: 0.2; }
      100% { transform: scale(1.5); opacity: 0.4; }
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
  
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      // Anima o nome principal
      const nameElement = document.getElementById('animated-name');
      setTimeout(() => {
        nameElement.style.animation = 'fadeIn 1.2s forwards';
      }, 300);
      
      // Configura o carrossel de profissões
      const professions = document.querySelectorAll('.profession-item');
      let currentIndex = 0;
      
      function showNextProfession() {
        // Esconde todas as profissões
        professions.forEach(prof => {
          prof.style.opacity = '0';
          prof.style.transform = 'translateY(20px)';
        });
        
        // Mostra a próxima profissão
        professions[currentIndex].style.opacity = '1';
        professions[currentIndex].style.transform = 'translateY(0)';
        
        // Atualiza o índice
        currentIndex = (currentIndex + 1) % professions.length;
      }
      
      // Mostra a primeira profissão após 1 segundo
      setTimeout(() => {
        showNextProfession();
        
        // Alterna as profissões a cada 3 segundos
        setInterval(showNextProfession, 3000);
      }, 1200);
    });
  </script>
</div>
