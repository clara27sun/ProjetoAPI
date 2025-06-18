<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ProjetoAPI - Documentação</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            line-height: 1.6;
            background-color: #f4f4f4;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h1 {
            color: #333;
            border-bottom: 3px solid #007bff;
            padding-bottom: 10px;
        }
        h2 {
            color: #007bff;
            margin-top: 30px;
        }
        .endpoint {
            background: #f8f9fa;
            border: 1px solid #dee2e6;
            border-radius: 5px;
            padding: 15px;
            margin: 10px 0;
        }
        .method {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 3px;
            font-weight: bold;
            margin-right: 10px;
        }
        .get { background: #28a745; color: white; }
        .post { background: #007bff; color: white; }
        .example {
            background: #e9ecef;
            border-left: 4px solid #007bff;
            padding: 10px;
            margin: 10px 0;
            font-family: 'Courier New', monospace;
        }
        .response {
            background: #d4edda;
            border: 1px solid #c3e6cb;
            border-radius: 5px;
            padding: 10px;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🚀 ProjetoAPI</h1>
        
        <h2>📋 Descrição</h2>
        <p>A <strong>ProjetoAPI</strong> é uma API RESTful simples desenvolvida em Node.js para gerenciamento de usuários. Esta API permite realizar operações básicas como listar, buscar e criar usuários através de endpoints HTTP.</p>
        
        <h2>🎯 Funcionalidades</h2>
        <ul>
            <li>Listar todos os usuários cadastrados</li>
            <li>Buscar usuário específico por ID</li>
            <li>Criar novos usuários</li>
            <li>Suporte a CORS para integração frontend</li>
            <li>Respostas em formato JSON</li>
        </ul>
        
        <h2>🔗 Endpoints Disponíveis</h2>
        
        <div class="endpoint">
            <span class="method get">GET</span><strong>/</strong>
            <p>Retorna informações gerais da API e lista de endpoints disponíveis.</p>
            <div class="response">
                <strong>Resposta:</strong> Objeto JSON com informações da API
            </div>
        </div>
        
        <div class="endpoint">
            <span class="method get">GET</span><strong>/users</strong>
            <p>Retorna a lista completa de usuários cadastrados no sistema.</p>
            <div class="response">
                <strong>Resposta:</strong> Array JSON contendo todos os usuários
            </div>
        </div>
        
        <div class="endpoint">
            <span class="method get">GET</span><strong>/users/:id</strong>
            <p>Busca um usuário específico pelo seu ID.</p>
            <div class="response">
                <strong>Resposta:</strong> Objeto JSON do usuário ou erro 404 se não encontrado
            </div>
        </div>
        
        <div class="endpoint">
            <span class="method post">POST</span><strong>/users</strong>
            <p>Cria um novo usuário no sistema.</p>
            <div class="example">
                <strong>Body esperado:</strong><br>
                {<br>
                &nbsp;&nbsp;"nome": "Nome do Usuário",<br>
                &nbsp;&nbsp;"email": "email@exemplo.com"<br>
                }
            </div>
            <div class="response">
                <strong>Resposta:</strong> Objeto JSON com mensagem de sucesso e dados do usuário criado
            </div>
        </div>
        
        <h2>🚀 Como Usar</h2>
        
        <h3>1. Iniciando o Servidor</h3>
        <div class="example">
            node index.js
        </div>
        <p>O servidor será iniciado na porta 5000 (ou na porta definida pela variável PORT).</p>
        
        <h3>2. Testando os Endpoints</h3>
        
        <h4>Listar todos os usuários:</h4>
        <div class="example">
            curl http://localhost:5000/users
        </div>
        
        <h4>Buscar usuário por ID:</h4>
        <div class="example">
            curl http://localhost:5000/users/1
        </div>
        
        <h4>Criar novo usuário:</h4>
        <div class="example">
            curl -X POST http://localhost:5000/users \<br>
            -H "Content-Type: application/json" \<br>
            -d '{"nome":"João Silva","email":"joao@email.com"}'
        </div>
        
        <h2>🛠️ Tecnologias Utilizadas</h2>
        <ul>
            <li><strong>Node.js</strong> - Runtime JavaScript</li>
            <li><strong>HTTP Module</strong> - Módulo nativo do Node.js para criar servidor</li>
            <li><strong>JSON</strong> - Formato de dados para requisições e respostas</li>
        </ul>
        
        <h2>📝 Estrutura do Projeto</h2>
        <div class="example">
            ProjetoAPI/<br>
            ├── index.js      # Arquivo principal da API<br>
            ├── readme.md     # Documentação (este arquivo)<br>
            └── package.json  # Dependências do projeto
        </div>
        
        <h2>👥 Exemplos de Resposta</h2>
        
        <h3>GET /users</h3>
        <div class="example">
            {<br>
            &nbsp;&nbsp;"users": [<br>
            &nbsp;&nbsp;&nbsp;&nbsp;{<br>
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": 1,<br>
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"nome": "João Silva",<br>
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"email": "joao@email.com"<br>
            &nbsp;&nbsp;&nbsp;&nbsp;}<br>
            &nbsp;&nbsp;]<br>
            }
        </div>
        
        <h3>POST /users</h3>
        <div class="example">
            {<br>
            &nbsp;&nbsp;"message": "Usuário criado com sucesso",<br>
            &nbsp;&nbsp;"user": {<br>
            &nbsp;&nbsp;&nbsp;&nbsp;"id": 1641234567890,<br>
            &nbsp;&nbsp;&nbsp;&nbsp;"nome": "Maria Santos",<br>
            &nbsp;&nbsp;&nbsp;&nbsp;"email": "maria@email.com"<br>
            &nbsp;&nbsp;}<br>
            }
        </div>
        
        <h2>📞 Contato</h2>
        <p>Para dúvidas ou sugestões sobre esta API, entre em contato através do GitHub.</p>
        
        <footer style="margin-top: 40px; text-align: center; color: #666;">
            <p>Desenvolvido para fins educacionais | ProjetoAPI v1.0.0</p>
        </footer>
    </div>
</body>
</html>
