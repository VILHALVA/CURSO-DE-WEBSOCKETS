# SINTAXE
## EXEMPLO DE SERVIDOR WEBSOCKET COM NODE.JS:
Aqui está um exemplo simples de como criar um servidor WebSocket:

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

## EXEMPLO DE CLIENTE WEBSOCKET EM JAVASCRIPT:
Aqui está um exemplo de como se conectar ao servidor WebSocket usando um cliente WebSocket em JavaScript (por exemplo, em um navegador):

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

## EXPLICAÇÃO DO CÓDIGO:
1. **Servidor WebSocket**:
   - Criamos um servidor WebSocket na porta 8080.
   - Quando um novo cliente se conecta, o servidor escuta para mensagens recebidas e envia uma mensagem de boas-vindas.
   - Quando o servidor recebe uma mensagem do cliente, ele a imprime no console e responde ao cliente com uma mensagem que inclui o texto recebido.

2. **Cliente WebSocket**:
   - O cliente se conecta ao servidor WebSocket na URL `ws://localhost:8080`.
   - Quando a conexão é estabelecida (`onopen`), o cliente envia uma mensagem ao servidor.
   - Quando o cliente recebe uma mensagem do servidor (`onmessage`), ele a exibe no console do navegador.
