# Especificação 03 — Pontos Turísticos

## Objetivo

Exibir ao usuário pontos turísticos cadastrados e permitir consultar seus detalhes.

## Entidade

### PontoTuristico

- `id: string`
- `nome: string`
- `descricao: string`
- `categoriaId: string`
- `latitude: number`
- `longitude: number`
- `endereco?: string`
- `cidade: string`
- `estado: string`
- `pais: string`
- `raioCheckinMetros: number`
- `pontosCheckin: number`
- `imagemPrincipalUrl?: string`
- `horarioFuncionamento?: string`
- `siteUrl?: string`
- `visitado: boolean`

## Funcionalidades

### Tela Explorar

- Mostrar pontos próximos.
- Exibir foto, nome, categoria, distância e pontos.
- Identificar visualmente locais já visitados.
- Ordenar por distância por padrão.
- Permitir tocar em um ponto para abrir detalhes.

### Tela Detalhes

Exibir:

- imagem;
- nome;
- descrição;
- categoria;
- distância;
- endereço;
- horário;
- pontos disponíveis;
- status de visita.

## API esperada

```text
GET /pontos-turisticos?latitude={lat}&longitude={lng}
GET /pontos-turisticos/{id}
```

## Critérios de aceite

- A lista é carregada a partir da API.
- A distância até cada ponto é exibida.
- O detalhe abre corretamente.
- Estados de carregamento, vazio e erro são tratados.
