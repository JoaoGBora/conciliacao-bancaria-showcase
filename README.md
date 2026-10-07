# Conciliação Bancária x Contábil com IA

> 🔒 Código privado (projeto corporativo). Esta página descreve o escopo e a arquitetura.

## Problema
Conferir o extrato bancário contra os lançamentos contábeis do ERP é um trabalho manual, linha a linha, feito em várias contas e bancos diferentes.

## Solução
Plugin para o **Claude Code** que automatiza a conciliação:
- Lê extratos em **OFX** (e CSV, para bancos que só exportam nesse formato)
- Busca os lançamentos contábeis direto do **TOTVS Protheus** via API REST
- Cruza os dois lados e aponta o que bate, o que falta e o que diverge

## Arquitetura
```
Extratos OFX/CSV ─┐
                  ├─►  Motor de conciliação (Claude Code)  ─►  Relatório de divergências
Protheus (CTB) ───┘        via API REST
```

## Tecnologias
Claude Code (plugin com skills e agentes) · Python · OFX · TOTVS Protheus REST/ADVPL

## Status
Em desenvolvimento.
