<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Delbler Ferreira - Profissional</title>
    <style>
        :root {
            --primary-color: #6A52FF;
            --secondary-color: #4A90E2;
            --text-color: #333;
            --light-bg: #f8f9fa;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4edf9 100%);
            padding: 20px;
        }
        
        .title-container {
            text-align: center;
            max-width: 800px;
            width: 100%;
            padding: 40px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            position: relative;
            overflow: hidden;
        }
        
        .title-container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, var(--primary-color) 0%, transparent 70%);
            opacity: 0.05;
            z-index: -1;
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: var(--text-color);
            position: relative;
            display: inline-block;
        }
        
        h1::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--primary-color);
            transform: scaleX(0);
            transform-origin: left;
            animation: underline-grow 1.5s ease-in-out forwards;
        }
        
        .typewriter {
            overflow: hidden;
            border-right: 3px solid var(--primary-color);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 1px;
            animation: typing 2s steps(20, end), blink-caret 0.75s step-end infinite;
        }
        
        .profession-carousel {
            height: 80px;
            margin: 30px 0;
            position: relative;
            overflow: hidden;
        }
        
        .profession-item {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.22, 1, 0.36, 1);
        }
        
        .profession-item.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        .profession-title {
            font-size: 2.2rem;
            font-weight: 600;
            color: var(--primary-color);
            margin-bottom: 8px;
        }
        
        .profession-desc {
            font-size: 1.2rem;
            color: var(--text-color);
            max-width: 80%;
            text-align: center;
        }
        
        .roadmap-button {
            display: inline-block;
            margin-top: 30px;
            padding: 14px 32px;
            font-size: 1.1rem;
            font-weight: 600;
            color: white;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(106, 82, 255, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .roadmap-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(106, 82, 255, 0.4);
        }
        
        .roadmap-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: all 0.6s ease;
        }
        
        .roadmap-button:hover::before {
            left: 100%;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--primary-color) }
        }
        
        @keyframes underline-grow {
            to { transform: scaleX(1); }
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .profession-title {
                font-size: 1.8rem;
            }
            
            .profession-desc {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="title-container">
        <h1 class="typewriter">Delbler Ferreira</h1>
        
        <div class="profession-carousel">
            <div class="profession-item active">
                <div class="profession-title">Especialista em Machine Learning</div>
                <div class="profession-desc">Desenvolvendo soluções inteligentes com algoritmos avançados</div>
            </div>
            
            <div class="profession-item">
                <div class="profession-title">Engenheiro de Automação</div>
                <div class="profession-desc">Criando sistemas eficientes para otimizar processos</div>
            </div>
            
            <div class="profession-item">
                <div class="profession-title">Desenvolvedor Full Stack</div>
                <div class="profession-desc">Construindo aplicações web completas e escaláveis</div>
            </div>
            
            <div class="profession-item">
                <div class="profession-title">Contribuidor Open Source</div>
                <div class="profession-desc">Compartilhando conhecimento com a comunidade tech</div>
            </div>
        </div>
        
        <button class="roadmap-button">Ver Roadmap Completo</button>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const professionItems = document.querySelectorAll('.profession-item');
            let currentIndex = 0;
            
            function rotateProfession() {
                // Remover classe ativa de todos os itens
                professionItems.forEach(item => item.classList.remove('active'));
                
                // Adicionar classe ativa ao próximo item
                professionItems[currentIndex].classList.add('active');
                
                // Atualizar índice
                currentIndex = (currentIndex + 1) % professionItems.length;
            }
            
            // Iniciar rotação a cada 4 segundos
            setInterval(rotateProfession, 4000);
            
            // Efeito hover no botão
            const roadmapButton = document.querySelector('.roadmap-button');
            roadmapButton.addEventListener('click', function() {
                this.textContent = 'Redirecionando...';
                setTimeout(() => {
                    // Ação ao clicar (pode ser redirecionamento para o roadmap)
                    alert('Redirecionando para o Roadmap Profissional!');
                }, 800);
            });
        });
    </script>
</body>
</html>
---
---
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
  ">
    <img 
      src="https://i.postimg.cc/LXRTBZXB/8G-Rede.png" 
      width="150" 
      height="150" 
      style="
        border-radius: 15px;
        border: 3px solid #4A90E2;
        display: block;
        margin: 0 auto 20px;
        box-shadow: 0 4px 8px rgba,0,0,0,0.1);
      " 
    />
    <h1 style="margin: 0 0 8px 0; color: #2c3e50; font-size: 2.2rem;">Delbler Ferreira Amancio</h1>
    <p style="margin: 0; color: #4A90E2; font-size: 1.1rem; font-weight: 500;">
      <em>Engenheiro Multidisciplinar | Desenvolvedor Full-Stack | Especialista em Automação</em>
    </p>
  </div>
  </div>
  
## 🚀 Portfólio Profissional
---
<div style="display: flex; flex-wrap: wrap; gap: 20px; margin-top: 20px; font-family: Arial, sans-serif; color: #2c3e50;">
  
  <div style="flex: 1; min-width: 280px; background: #f0f8ff; padding: 20px; border-radius: 10px; border-left: 5px solid #4A90E2; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
    <h3 style="margin-top: 0; display: flex; align-items: center; gap: 8px;">
      <span>🎓</span> Formação Acadêmica
    </h3>
    <ul style="list-style: none; padding-left: 0;">
      <li style="margin-bottom: 10px;">👨‍💻 Engenharia de Software <em>(em Formação)</em></li>
      <li style="margin-bottom: 10px;">🏭 Engenharia de Produção <em>(em Formação)</em></li>
      <li>⚙️ Engenharia Mecânica <em>(em Formação)</em></li>
    </ul>
  </div>

  <div style="flex: 1; min-width: 280px; background: #f0f8ff; padding: 20px; border-radius: 10px; border-left: 5px solid #4A90E2; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
    <h3 style="margin-top: 0; display: flex; align-items: center; gap: 8px;">
      <span>💼</span> Experiência & Foco
    </h3>
    <ul style="list-style: none; padding-left: 0;">
      <li style="margin-bottom: 10px;">📊 Administrador de Finanças Freelance</li>
      <li>💡 Foco em: Automação de Processos, Análise de Dados, Soluções Tech-Driven</li>
    </ul>
  </div>

  <div style="flex: 1; min-width: 280px; background: #f0f8ff; padding: 20px; border-radius: 10px; border-left: 5px solid #4A90E2; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
    <h3 style="margin-top: 0; display: flex; align-items: center; gap: 8px;">
      <span>🌱</span> Aprendizado Atual
    </h3>
    <ul style="list-style: none; padding-left: 0;">
      <li style="margin-bottom: 10px;">🌐 Web Development</li>
      <li style="margin-bottom: 10px;">🐍 Python Avançado</li>
      <li>🤖 Machine Learning</li>
    </ul>
  </div>

</div>

---

### 🛠️ Stack Tecnológico Completo

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 12px; margin: 25px 0;">

**Linguagens & Frameworks**  
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)

**Ferramentas & Plataformas**  
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

**Cloud & Databases**  
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

</div>

---

### 📌 Projetos em Destaque

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; margin: 30px 0;">

[![GitHub Streak](https://streak-stats.demolab.com?user=delblerferreira&theme=blueberry&hide_border=true&locale=pt_BR)](https://git.io/streak-stats)

<div style="background: #f8f9fa; padding: 15px; border-radius: 10px; width: 100%;">
  <h3 style="margin-top: 0; color: #2c3e50;">Projetos Notáveis</h3>
  <ul>
    <li><strong>Sistema de Automação Empresarial</strong> - Python, Flask, MySQL</li>
    <li><strong>Plataforma de Análise de Dados</strong> - Pandas, Matplotlib, Streamlit</li>
    <li><strong>Aplicativo Web para Gestão Financeira</strong> - React, Node.js, MongoDB</li>
  </ul>
</div>

</div>

---

### 📈 Estatísticas de Desenvolvimento

<div align="center" style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin: 30px 0;">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=delblerferreira&show_icons=true&theme=radical&include_all_commits=true&count_private=true&hide_border=true"/>

<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=delblerferreira&layout=compact&langs_count=8&theme=radical&hide_border=true"/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=delblerferreira&theme=react&hide_border=true&area=true" height="240em"/>

</div>

---

### 🌐 Contato Profissional

<div align="center" style="display: flex; flex-wrap: wrap; justify-content: center; gap: 12px; margin: 30px 0;">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/delbler-ferreira-consultor)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/delbler_ferreira)
[![Medium](https://img.shields.io/badge/Medium-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@delblerferreira9)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:delblerferreira9@gmail.com)
[![Beacons](https://img.shields.io/badge/Portfólio-6A52FF?style=for-the-badge&logo=beacons&logoColor=white)](https://beacons.ai/delblerferreira)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/delblerferreira)

</div>

---

### 🎯 Roadmap Profissional 2025

```mermaid
gantt
    title Metas para 2025
    dateFormat  YYYY-MM-DD
    section Especialização
    Machine Learning           :active,    des1, 2025-01-01, 2025-06-30
    Publicação Técnica         :         des2, after des1, 90d
    section Desenvolvimento
    Sistema Automação          :         des3, 2025-03-01, 120d
    section Comunidade
    1k GitHub Followers        :         des4, 2025-07-01, 180d
```

---

<details>
<summary>📚 Guia de Estudos (Clique para Expandir)</summary>

<table>
  <thead>
    <tr>
      <th style="background-color:#4A90E2; color:white; padding:8px; border:1px solid #4A90E2;">Assunto</th>
      <th style="background-color:#4A90E2; color:white; padding:8px; border:1px solid #4A90E2;">Tempo (h)</th>
      <th style="background-color:#4A90E2; color:white; padding:8px; border:1px solid #4A90E2;">Período</th>
      <th style="background-color:#4A90E2; color:white; padding:8px; border:1px solid #4A90E2;">Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border:1px solid #4A90E2; padding:8px;">Leitura Técnica</td>
      <td style="border:1px solid #4A90E2; padding:8px;">1h</td>
      <td style="border:1px solid #4A90E2; padding:8px;">02/2025 a 05/2025</td>
      <td style="border:1px solid #4A90E2; padding:8px; background-color:#5bc0de; color:white;">Concluido</td>
    </tr>
    <tr>
      <td style="border:1px solid #4A90E2; padding:8px;">Prática de Codificação</td>
      <td style="border:1px solid #4A90E2; padding:8px;">2h</td>
      <td style="border:1px solid #4A90E2; padding:8px;">02/2025 a 12/2025</td>
      <td style="border:1px solid #4A90E2; padding:8px; background-color:#5bc0de; color:white;">Em Andamento</td>
    </tr>
    <tr>
      <td style="border:1px solid #4A90E2; padding:8px;">Revisão de Algoritmos</td>
      <td style="border:1px solid #4A90E2; padding:8px;">30min</td>
      <td style="border:1px solid #4A90E2; padding:8px;">02/2025 a 10/2025</td>
      <td style="border:1px solid #4A90E2; padding:8px; background-color:#5bc0de; color:white;">Em Andamento</td>
    </tr>
  </tbody>
</table>

---

### 📊 Andamento do Estudo (Gráfico Customizado)

```mermaid
gantt
    title Progresso dos Estudos
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%Y
    section Leitura Técnica
    Concluido           :active,    lt, 2025-02-01, 2025-05-31
    section Prática de Codificação
    Em Andamento           :active,    pc, 2025-02-01, 2025-12-31
    section Revisão de Algoritmos
    Em Andamento           :active,    ra, 2025-02-01, 2025-10-31
