# Especificação 06 — Pontuação e Níveis

## Objetivo

Implementar a progressão do usuário através de pontos e níveis.

## Entidades

### MovimentacaoPontos

- `id: string`
- `usuarioId: string`
- `dataHora: string`
- `quantidade: number`
- `tipo: string`
- `origemId?: string`
- `descricao: string`

### Nivel

- `id: string`
- `numero: number`
- `nome: string`
- `pontosMinimos: number`
- `pontosMaximos?: number`
- `iconeUrl?: string`

## Regras

- Toda alteração de pontos deve gerar uma movimentação.
- `pontosTotais` nunca deve ser alterado no app cliente.
- O backend calcula nível e saldo.
- Pontuação deve ser idempotente por evento de origem.

## Funcionalidades

- Mostrar saldo atual.
- Mostrar nível atual.
- Mostrar progresso até o próximo nível.
- Mostrar extrato de movimentações.

## Critérios de aceite

- Check-in bem-sucedido atualiza saldo.
- Nível muda automaticamente ao atingir a faixa necessária.
- O usuário consegue visualizar o histórico de pontos.
