# 🖥️ Remo

> **Remo** é uma ferramenta experimental de acesso remoto desenvolvida em **.NET**, com foco em simplicidade, extensibilidade e aprendizado.  
O foco inicial do projeto é apenas entender o fluxo de um projeto de streaming de dados, mas com a previsão de se tornar uma ferramenta disponível para uso.

---

## 🧰 Tecnologias

- **.NET (C#)**
- **ASP.NET Core** — servidor / relay
- **WebSocket** — comunicação em tempo real
- **Arquitetura preparada para QUIC**
- **WPF** — interface desktop
- **TLS** — comunicação segura

---

## 🎯 Objetivos do Projeto

- 🔌 Acesso remoto leve e controlado
- 🧩 Arquitetura modular e extensível
- 🧪 Projeto voltado a aprendizado e portfólio
- 🛠️ Comunicação clara e previsível
- 🚀 Possibilidade de evolução para QUIC

---

## 🧱 Arquitetura (conceitual)

```
┌─────────────┐        WebSocket        ┌──────────────┐        WebSocket        ┌──────────────┐  
│  Remo WPF   │  ───────────────────>   │ Remo Server  │  ───────────────────>   │   Remo WPF   │
│   (Host)    │  <───────────────────   │   (Relay)    │  <───────────────────   │   (Client)   │
└─────────────┘        WebSocket        └──────────────┘        WebSocket        └──────────────┘                    
```

### Componentes

- **Remo Desktop (WPF - Host)**  
  Interface gráfica que recebe o acesso. Após o aceite, captura os dados e envia pela rede enquanto aguarda ações do Host.

- **Remo Server (Relay)**  
  Responsável por intermediar conexões, autenticação e roteamento.

- **Remo Transport**  
  Camada de abstração de transporte (WebSocket / QUIC futuramente).

- **Remo Desktop (WPF - Client)**  
  Interface gráfica que inicia o acesso. Após o aceite, recebe os dados do host, realiza ações e propaga de volta para o Host.
---

## 🔌 Camada de Transporte

O projeto utiliza uma abstração de transporte para permitir a troca futura do protocolo:

- WebSocket (implementação inicial)
- QUIC (planejado)

Essa decisão mantém o núcleo do sistema desacoplado da tecnologia de rede.

---

## 🧪 Exemplo de Uso (conceitual)

```bash
# inicia o agent na máquina remota
remo agent start

# lista agentes disponíveis
remo list

# conecta a um agent
remo connect <agent-id>
```

> ⚠️ Os comandos acima são ilustrativos. A API ainda está em desenvolvimento.

---

## 🛣️ Roadmap Inicial

- [ ] Estrutura da solução .NET
- [ ] Definição do protocolo de mensagens
- [ ] Implementação do Remo Agent
- [ ] Comunicação via WebSocket
- [ ] Interface WPF básica
- [ ] Autenticação simples
- [ ] Sessão remota inicial
- [ ] Transporte QUIC (experimental)

---

## 🔐 Aviso de Segurança

⚠️ **Este projeto é experimental e não deve ser utilizado em produção.**

Questões de segurança estão em estudo e evoluirão ao longo do desenvolvimento.

---

## 🤝 Contribuições

Sugestões, ideias e discussões são bem-vindas.  
Sinta-se à vontade para abrir uma *issue* ou *pull request*.

---

## 📄 Licença

Este projeto é distribuído sob a licença **MIT**.
