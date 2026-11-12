# SDD — App de Turismo Gamificado

Este diretório contém especificações independentes para implementação incremental do aplicativo.

## Stack assumida

- React Native
- TypeScript
- Projeto nativo React Native CLI
- Android compilado pelo Android Studio / Gradle
- Sem Expo
- Backend consumido via API REST
- GPS nativo do dispositivo
- Persistência local apenas quando necessária para cache e sessão

## Ordem sugerida de implementação

1. `01-arquitetura-base.md`
2. `02-autenticacao-e-usuario.md`
3. `03-pontos-turisticos.md`
4. `04-mapa-e-geolocalizacao.md`
5. `05-checkin.md`
6. `06-pontuacao-e-niveis.md`
7. `07-conquistas.md`
8. `08-desafios.md`
9. `09-perfil-e-historico.md`
10. `10-requisitos-nao-funcionais.md`

Cada arquivo deve ser tratado como uma especificação implementável e verificável de forma independente.
