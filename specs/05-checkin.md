# Especificação 05 — Check-in por Proximidade

## Objetivo

Permitir check-in somente quando o usuário estiver fisicamente próximo do ponto turístico.

## Fluxo

1. Usuário abre o detalhe do ponto turístico.
2. App obtém localização atual.
3. App calcula distância entre usuário e ponto.
4. Se estiver dentro do raio permitido, libera o check-in.
5. Usuário confirma.
6. Backend valida a tentativa.
7. Usuário recebe os pontos.

## Dados enviados ao backend

```json
{
  "pontoTuristicoId": "string",
  "latitude": 0,
  "longitude": 0,
  "precisaoGpsMetros": 0
}
```

## API esperada

```text
POST /visitas/checkin
```

## Regras

- O backend é a autoridade final da validação.
- O app não deve conceder pontos localmente.
- O usuário não pode receber pontos repetidamente pelo mesmo ponto, salvo regra explícita futura.
- A precisão do GPS deve ser considerada na validação.
- A distância deve ser recalculada no backend.

## Resposta de sucesso

Deve retornar:

- visita criada;
- pontos recebidos;
- saldo atualizado;
- progresso de conquistas afetadas.

## Critérios de aceite

- Check-in fica desabilitado fora do raio.
- Check-in fica disponível dentro do raio.
- Falhas de validação são exibidas.
- Pontos só aparecem após confirmação do backend.
