# Especificação 08 — Desafios

## Objetivo

Permitir campanhas ou objetivos temporários de exploração.

## Entidades

### Desafio

- `id: string`
- `nome: string`
- `descricao: string`
- `dataInicio?: string`
- `dataFim?: string`
- `pontosRecompensa: number`
- `tipo: string`
- `meta: number`
- `ativo: boolean`

### DesafioUsuario

- `id: string`
- `usuarioId: string`
- `desafioId: string`
- `progressoAtual: number`
- `concluido: boolean`
- `dataConclusao?: string`
- `pontosRecebidos: number`

## Exemplos

- Visite 3 atrações históricas de uma cidade.
- Visite 5 locais durante um fim de semana.
- Complete uma rota turística.

## Regras

- Apenas desafios ativos contam progresso.
- O período de validade deve ser respeitado pelo backend.
- A conclusão deve ser idempotente.

## Critérios de aceite

- Usuário visualiza desafios ativos.
- Progresso é atualizado após eventos relevantes.
- Desafios expirados não recebem progresso.
