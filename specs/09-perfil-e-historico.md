# Especificação 09 — Perfil e Histórico

## Objetivo

Consolidar a jornada turística do usuário.

## Tela Perfil

Exibir:

- nome;
- foto;
- nível;
- pontos;
- quantidade de locais visitados;
- quantidade de cidades exploradas;
- conquistas desbloqueadas.

## Histórico

Mostrar as últimas visitas contendo:

- ponto turístico;
- data;
- cidade;
- pontos recebidos.

## API esperada

```text
GET /me
GET /me/visitas
GET /me/movimentacoes-pontos
```

## Critérios de aceite

- Dados refletem o estado atual do backend.
- Histórico é exibido em ordem decrescente.
- Tela suporta carregamento incremental caso haja muitos registros.
