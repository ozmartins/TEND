# Especificação 04 — Mapa e Geolocalização

## Objetivo

Exibir o usuário e os pontos turísticos em um mapa e disponibilizar a localização atual do dispositivo.

## Requisitos

- Solicitar permissão de localização em runtime.
- Utilizar API de geolocalização compatível com React Native CLI.
- Não utilizar APIs do Expo.
- Exibir mapa nativo.
- Centralizar o mapa na posição atual quando possível.

## Funcionalidades

- Mostrar posição atual.
- Mostrar marcadores dos pontos turísticos.
- Diferenciar visitados e não visitados.
- Ao tocar em marcador, abrir resumo da atração.
- Permitir abrir tela de detalhes.

## Estados de permissão

Tratar explicitamente:

- permissão concedida;
- permissão negada;
- permissão negada permanentemente;
- GPS desabilitado;
- posição indisponível.

## Critérios de aceite

- App solicita permissão corretamente no Android.
- Posição do usuário aparece no mapa.
- Marcadores são exibidos.
- Erros de GPS não causam crash.
- Usuário recebe orientação quando a permissão estiver bloqueada.
