# Especificação 07 — Conquistas

## Objetivo

Criar metas permanentes que recompensem a exploração do usuário.

## Entidades

### Conquista

- `id: string`
- `nome: string`
- `descricao: string`
- `iconeUrl?: string`
- `tipo: string`
- `meta: number`
- `pontosBonus: number`
- `ativa: boolean`

### ConquistaUsuario

- `id: string`
- `usuarioId: string`
- `conquistaId: string`
- `progressoAtual: number`
- `concluida: boolean`
- `dataConclusao?: string`
- `pontosRecebidos: number`

## Exemplos

- Visitar 1 ponto turístico.
- Visitar 5 pontos turísticos.
- Visitar 10 atrações históricas.
- Visitar atrações em 5 cidades.

## Funcionalidades

- Tela de conquistas.
- Separar concluídas e em andamento.
- Mostrar barra de progresso.
- Mostrar recompensa.
- Atualizar progresso após check-in.

## Regras

- Uma conquista só pode ser concluída uma vez por usuário.
- Pontos de bônus só podem ser concedidos uma vez.

## Critérios de aceite

- Progresso é atualizado pelo backend.
- Conquistas concluídas ficam visualmente destacadas.
- Recompensa é refletida no saldo de pontos.
