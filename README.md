# SentinelTrade

Sistema de Trade Financeiro de Alta Criticidade, desenvolvido como exercício integrador acadêmico para a corretora fictícia Orion Capital.

> Projeto acadêmico. Não opera com dinheiro real, bolsa real ou dados financeiros reais — todos os ativos, contas e cotações são simulados.

---

## Sobre o projeto
A Orion Capital é uma corretora fictícia que negocia ações, ETFs e fundos imobiliários. Hoje suas operações dependem de sistemas pouco integrados, o que dificulta a rastreabilidade das ordens, o controle de risco e a auditoria.

O SentinelTrade vem para resolver isso: uma plataforma distribuída, segura, escalável e tolerante a falhas, que permite a investidores autorizados:
- acompanharem cotações em tempo quase real;
- manter uma carteira de ativos;
- enviar ordens de compra e venda;
- consultar o histórico de operações.

Como o impacto de falhas aqui é financeiro, regulatório e reputacional, o sistema é tratado como de alta criticidade, cada decisão de arquitetura leva em conta segurança, auditabilidade e recuperação de falhas.

## Requisitos do sistema
Requisitos Funcionais(RF):
RF-01: Cadastro de investidores, contas, carteiras, ativos e limites financeiros
RF-02: Consulta de informações (carteira, conta, limites)
RF-03: Recebimento de cotações em tempo quase real (provedor externo simulado)
RF-04: Envio de ordens: compra, venda, cancelamento e consulta
RF-05: Validação de saldo, posição em carteira, limite de risco e situação do mercado antes de transmitir a ordem
RF-06: Integração com Bolsa/Corretora simulada
RF-07: Acompanhamento do ciclo de vida das ordens
RF-08: Logs de auditoria imutáveis
RF-09: Notificação ao investidor (execução, rejeição, cancelamento, falha)
RF-10: Consulta de histórico

Requisitos Não Funcionais(RNF):
RNF-01: Autenticação de usuários com MFA (múltiplo fator)
RNF-02: Mecanismos de recuperação, indisponibilidade controlada e prevenção de duplicidade de ordens
RNF-03: Integridade dos dados
RNF-04: Desempenho
RNF-05: Escalabilidade sem comprometer o sistema
RNF-06: Segurança de dados e operações
RNF-07: Recuperação no caso e falhas
RNF-08: Consistência dos dados
RNF-09: Disponibilidade
RNF-10: Proteção de senhas

## UML (Casos de Uso) do Sistema



## Arquitetura (visão geral)

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

- Provedor de cotações: componente externo (simulado) que envia preços atualizados continuamente.
- Motor de ordens: valida saldo, risco e situação do mercado antes de enviar a ordem para a bolsa simulada.
- Banco de dados: guarda histórico, carteiras e logs de auditoria (imutáveis).
- Notificações: avisa o investidor sobre o que aconteceu com sua ordem.

## Tecnologias 

> Em fase de estruturação


## Equipe

| Leonardo Aquino Cruz |10445016
| Victor Esteves Gallo Birello|10737139


