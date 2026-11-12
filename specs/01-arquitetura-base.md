# Especificação 01 — Arquitetura Base

## Objetivo

Criar a estrutura inicial do aplicativo React Native, compilável diretamente pelo Android Studio, sem Expo.

## Requisitos técnicos

- Usar React Native com TypeScript.
- O projeto deve possuir pasta `android/` funcional.
- A aplicação deve ser compilável via Android Studio e via Gradle.
- Não utilizar Expo, Expo Router ou bibliotecas que dependam exclusivamente de Expo.
- Adotar navegação baseada em React Navigation.
- Implementar gerenciamento de estado de forma simples e previsível.
- Centralizar acesso HTTP em uma camada de serviços.
- Separar componentes visuais, telas, serviços, modelos e hooks.

## Estrutura sugerida

```text
src/
  components/
  screens/
  navigation/
  services/
  hooks/
  models/
  stores/
  utils/
  constants/
  theme/
```

## Navegação principal

Criar uma navegação inferior com:

- Explorar
- Mapa
- Conquistas
- Perfil

## Critérios de aceite

- O projeto abre e compila no Android Studio.
- O app inicia em um emulador Android.
- A navegação inferior funciona.
- Cada item da navegação abre uma tela placeholder.
- Nenhuma dependência do Expo está presente.
