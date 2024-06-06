# CURSO DE WEBSOCKETS
👨‍⚖️WEBSOCKETS É UMA TECNOLOGIA QUE PERMITE A COMUNICAÇÃO BIDIRECIONAL EM TEMPO REAL ENTRE UM CLIENTE (GERALMENTE UM NAVEGADOR) E UM SERVIDOR. DIFERENTE DO HTTP, QUE É BASEADO EM REQUISIÇÕES E RESPOSTAS, WEBSOCKETS MANTÉM UMA CONEXÃO ABERTA PERMITINDO A TROCA CONTÍNUA DE MENSAGENS.

<img src="FOTO.png" align="center" width="400"> <br>

## CONCEITO:
1. **WebSocket**:
   - WebSockets é uma tecnologia que permite a comunicação bidirecional em tempo real entre um cliente (geralmente um navegador) e um servidor. Diferente do HTTP, que é baseado em requisições e respostas, WebSockets mantém uma conexão aberta permitindo a troca contínua de mensagens.

2. **Protocolo WebSocket**:
   - O protocolo WebSocket foi padronizado pela IETF como RFC 6455 em 2011. Ele funciona sobre o TCP e permite que os dados sejam enviados e recebidos através da mesma conexão, mantendo-a aberta até que um dos lados decida fechá-la.

3. **Aplicações**:
   - WebSockets são usados em aplicações que requerem atualizações em tempo real, como chats, jogos online, dashboards de monitoramento, notificações em tempo real, etc.

## PRATICAS COMUNS:
1. **Manter Conexão Viva (Heartbeat)**:
   - Em aplicações reais, é comum implementar um mecanismo de "heartbeat" para manter a conexão viva e detectar desconexões. Isso pode ser feito enviando mensagens de ping/pong periodicamente.

2. **Múltiplos Clientes**:
   - Certifique-se de gerenciar múltiplos clientes adequadamente. Isso inclui manter um registro das conexões ativas e lidar com desconexões limpamente.

3. **Segurança**:
   - Considere usar WebSockets sobre TLS (wss://) para criptografar a comunicação e proteger os dados transmitidos.

## CARACTERISTICAS:
### POSITIVAS:
1. **Comunicação Bidirecional**:
   - WebSockets permitem comunicação bidirecional entre o cliente e o servidor, possibilitando a troca contínua de mensagens sem a necessidade de repetidas requisições HTTP.

2. **Baixa Latência**:
   - Como a conexão é mantida aberta, há uma redução significativa na latência em comparação com as requisições HTTP tradicionais, onde cada interação requer uma nova conexão.

3. **Eficiência de Recursos**:
   - WebSockets são mais eficientes em termos de uso de largura de banda e recursos do servidor, pois evitam o overhead de estabelecer conexões repetidamente.

4. **Tempo Real**:
   - São ideais para aplicações que exigem atualização em tempo real, como chats, jogos online, notificações em tempo real e dashboards de monitoramento.

5. **Simplicidade de API**:
   - A API de WebSockets é relativamente simples e fácil de usar, com eventos claros para conexão, mensagens, erros e fechamento de conexões.

### NEGATIVAS:
1. **Compatibilidade com Proxies e Firewalls**:
   - Nem todos os proxies e firewalls suportam WebSockets. Isso pode resultar em problemas de conectividade em algumas redes corporativas ou restritas.

2. **Complexidade de Implementação**:
   - Embora a API seja simples, a implementação de um sistema robusto e seguro pode ser complexa, especialmente ao lidar com autenticação, autorização e gerenciamento de conexões.

3. **Manutenção de Conexão**:
   - Manter conexões abertas pode consumir recursos do servidor, especialmente em aplicações com um grande número de usuários simultâneos. Isso pode exigir uma arquitetura de servidor mais robusta e escalável.

4. **Problemas de Escalabilidade**:
   - WebSockets podem apresentar desafios de escalabilidade, especialmente quando se trata de balanceamento de carga e distribuição de conexões entre múltiplos servidores.

5. **Segurança**:
   - A implementação de segurança em WebSockets pode ser mais desafiadora do que em requisições HTTP tradicionais. É necessário garantir que a comunicação seja criptografada (usando `wss://` em vez de `ws://`) e que as mensagens sejam autenticadas e autorizadas corretamente.

6. **Fallback**:
   - Em alguns casos, é necessário implementar soluções de fallback para navegadores ou ambientes que não suportam WebSockets, como polling ou long-polling, o que pode adicionar complexidade ao código.

## SUBSIDIOS:
- [CURSO CRIADO PELO "MANOEL CAMPOS DEV"](https://youtube.com/playlist?list=PLyo0RUAM69UvnqUq5SFeVahS_YTUVgq4v&si=Ng1YrEs6_lXSchar)
- [CURSO FEITO PELO VILHALVA](https://github.com/VILHALVA)
- [VEJA A DOCUMENTAÇÃO](https://websocket.org/)
- [TECNOLOGIA](https://github.com/VILHALVA/CURSO-DE-NODEJS)
- [LINGUAGEM DE PROGRAMAÇÃO](https://github.com/VILHALVA/CURSO-DE-JAVASCRIPT)
- [VEJA O MANUAL](./MANUAL.md) 
- [VEJA A SINTAXE](./SINTAXE.md)
- [VEJA OS PROJETOS](https://github.com/VILHALVA?tab=repositories&q=topic:WEBSOCKETS)