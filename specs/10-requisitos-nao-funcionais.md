# Especificação 10 — Requisitos Não Funcionais

## Segurança

- Nunca confiar na localização enviada pelo cliente sem validação.
- Tokens de autenticação devem ser armazenados de forma segura.
- Nenhuma chave secreta deve ficar embutida no app.
- Comunicação apenas via HTTPS em produção.

## Antifraude de localização

O backend deve avaliar:

- distância até o ponto;
- precisão do GPS;
- velocidade implícita entre check-ins;
- saltos geográficos impossíveis;
- repetição anormal de tentativas.

## Performance

- Listas devem ser paginadas ou limitadas.
- Imagens devem possuir cache.
- Consultas de pontos próximos devem ser geograficamente otimizadas.
- O app deve evitar atualização contínua de GPS quando não necessária.

## UX

- Sempre mostrar feedback durante ações de rede.
- Check-in deve possuir confirmação visual clara.
- Erros de localização devem ser compreensíveis.
- Permissões devem ser solicitadas apenas quando necessárias.

## Observabilidade

O app deve registrar, sem dados sensíveis:

- erros de API;
- falhas de geolocalização;
- falhas de check-in;
- crashes.

## Testes mínimos

- Testes unitários para cálculo de distância.
- Testes de serviços HTTP.
- Testes de reducers/stores, caso utilizados.
- Testes de regras de habilitação do check-in.
- Testes manuais em dispositivo Android real para GPS e permissões.

## Critérios de aceite

- Aplicação não quebra sem GPS.
- Aplicação não quebra sem rede.
- Check-ins duplicados não geram pontos duplicados.
- Erros críticos possuem tratamento explícito.
