# SentinelTrade

Sistema de Trade Financeiro de Alta Criticidade, desenvolvido como exercício integrador acadêmico para a corretora fictícia **Orion Capital**.

> ⚠️ Projeto acadêmico. Não opera com dinheiro real, bolsa real ou dados financeiros reais — todos os ativos, contas e cotações são simulados.

---

## 📋 Sobre o projeto

A Orion Capital é uma corretora fictícia que negocia ações, ETFs e fundos imobiliários. Hoje suas operações dependem de sistemas pouco integrados, o que dificulta a rastreabilidade das ordens, o controle de risco e a auditoria.

O **SentinelTrade** nasce para resolver isso: uma plataforma distribuída, segura, escalável e tolerante a falhas, que permite a investidores autorizados:

- acompanhar cotações em tempo quase real;
- manter uma carteira de ativos;
- enviar ordens de compra e venda;
- consultar o histórico de operações.

Como o impacto de falhas aqui é financeiro, regulatório e reputacional, o sistema é tratado como de **alta criticidade** — cada decisão de arquitetura leva em conta segurança, auditabilidade e recuperação de falhas.

## 🎯 Requisitos do sistema

- [ ] Autenticação de usuários com MFA (múltiplo fator)
- [ ] Cadastro de investidores, contas, carteiras, ativos e limites financeiros
- [ ] Recebimento de cotações em tempo quase real (provedor externo simulado)
- [ ] Envio de ordens: compra, venda, cancelamento e consulta
- [ ] Validação de saldo, posição em carteira, limite de risco e situação do mercado antes de transmitir a ordem
- [ ] Integração com Bolsa/Corretora simulada
- [ ] Acompanhamento do ciclo de vida das ordens
- [ ] Logs de auditoria imutáveis
- [ ] Notificação ao investidor (execução, rejeição, cancelamento, falha)
- [ ] Mecanismos de recuperação, indisponibilidade controlada e prevenção de duplicidade de ordens

## 🏗️ Arquitetura (visão geral)

O sistema é dividido em componentes que conversam entre si, cada um com uma responsabilidade clara:

```
[Investidor] ──> [App/Frontend] ──> [SentinelTrade - Backend]
                                          │
                    ┌─────────────────────┼─────────────────────┐
                    ▼                     ▼                     ▼
         [Autenticação/MFA]      [Motor de Ordens]     [Banco de Dados]
                                          │
                                          ▼
                              [Bolsa/Corretora Simulada]
                                          ▲
                                          │
                         [Provedor de Cotações Simulado]
```

- **Provedor de cotações**: componente externo (simulado) que envia preços atualizados continuamente.
- **Motor de ordens**: valida saldo, risco e situação do mercado antes de enviar a ordem para a bolsa simulada.
- **Banco de dados**: guarda histórico, carteiras e logs de auditoria (imutáveis).
- **Notificações**: avisa o investidor sobre o que aconteceu com sua ordem.

## 🛠️ Tecnologias 

> Em fase de estruturação


## 👥 Equipe

| Leonardo Aquino Cruz |
| Victor Esteves Gallo Pirello|


