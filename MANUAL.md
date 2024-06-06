# MANUAL
## PASSO 1: INSTALAR NODE.JS E NPM:
Se você ainda não tem o Node.js instalado, você pode baixá-lo e instalá-lo a partir do [site oficial do Node.js](https://nodejs.org/). O npm (Node Package Manager) é instalado automaticamente junto com o Node.js.

Para verificar se o Node.js e o npm estão instalados corretamente, você pode usar os seguintes comandos no terminal ou prompt de comando:

```bash
node -v
npm -v
```

## PASSO 2: CRIAR UM NOVO PROJETO NODE.JS:
Crie um diretório para o seu novo projeto e navegue até ele no terminal:

```bash
mkdir meu-projeto-websocket
cd meu-projeto-websocket
```

Inicialize um novo projeto Node.js com `npm init`. Siga as instruções no terminal para configurar seu projeto. Você pode aceitar os valores padrão pressionando `Enter` repetidamente.

```bash
npm init
```

## PASSO 3: INSTALAR A BIBLIOTECA WEBSOCKET:
Instale a biblioteca `ws`, que é uma implementação de WebSocket para Node.js:

```bash
npm install ws
```

## PASSO 4: CRIAR O SERVIDOR WEBSOCKET:
Crie um arquivo chamado `server.js` no diretório do seu projeto e adicione o seguinte código para criar um servidor WebSocket:

```javascript
const WebSocket = require('ws');

// Cria um servidor WebSocket na porta 8080
const wss = new WebSocket.Server({ port: 8080 });

wss.on('connection', function connection(ws) {
  console.log('Novo cliente conectado');

  // Evento para quando o servidor recebe uma mensagem do cliente
  ws.on('message', function incoming(message) {
    console.log('Recebido: %s', message);
    
    // Envia uma mensagem de volta para o cliente
    ws.send(`Você disse: ${message}`);
  });

  // Envia uma mensagem de boas-vindas ao cliente assim que ele se conecta
  ws.send('Bem-vindo ao servidor WebSocket!');
});

console.log('Servidor WebSocket está escutando na porta 8080');
```

## PASSO 5: EXECUTAR O SERVIDOR WEBSOCKET:
Para iniciar o servidor WebSocket, execute o arquivo `server.js` usando Node.js:

```bash
node server.js
```

Se tudo estiver configurado corretamente, você verá a mensagem "Servidor WebSocket está escutando na porta 8080" no terminal.

## PASSO 6: CRIAR O CLIENTE WEBSOCKET:
Para testar seu servidor, você pode criar um arquivo HTML com um cliente WebSocket. Crie um arquivo chamado `index.html` no diretório do seu projeto e adicione o seguinte código:

```html
<!DOCTYPE html>
<html>
<head>
  <title>WebSocket Client</title>
</head>
<body>
  <script>
    // Conecta ao servidor WebSocket
    const socket = new WebSocket('ws://localhost:8080');

    // Evento que ocorre quando a conexão é aberta
    socket.onopen = function(event) {
      console.log('Conectado ao servidor WebSocket');
      socket.send('Olá, servidor!');
    };

    // Evento que ocorre quando uma mensagem é recebida do servidor
    socket.onmessage = function(event) {
      console.log('Mensagem recebida do servidor: ' + event.data);
    };

    // Evento que ocorre quando a conexão é fechada
    socket.onclose = function(event) {
      console.log('Desconectado do servidor WebSocket');
    };

    // Evento que ocorre em caso de erro
    socket.onerror = function(error) {
      console.log('Erro: ' + error.message);
    };
  </script>
</body>
</html>
```

## PASSO 7: TESTAR A CONEXÃO WEBSOCKET:
1. Abra o arquivo `index.html` em um navegador (você pode simplesmente arrastar e soltar o arquivo no navegador ou abrir com um servidor HTTP local).

2. Verifique o console do navegador (pressione `F12` ou `Ctrl+Shift+I` e vá para a aba "Console") para ver as mensagens de conexão e comunicação.

