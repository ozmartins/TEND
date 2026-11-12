# Especificação 02 — Autenticação e Usuário

## Objetivo

Permitir que o usuário possua uma sessão autenticada e um perfil básico.

## Entidade principal

### Usuario

- `id: string`
- `nome: string`
- `email: string`
- `fotoUrl?: string`
- `pontosTotais: number`
- `nivel: number`

## Funcionalidades

- Tela de login.
- Persistência segura do token de autenticação.
- Restauração automática da sessão.
- Logout.
- Consulta dos dados do usuário autenticado.

## API esperada

```text
POST /auth/login
GET /me
POST /auth/logout
```

## Regras

- O usuário não autenticado não deve acessar as telas principais.
- O token deve ser enviado em todas as requisições autenticadas.
- Em caso de HTTP 401, a sessão deve ser encerrada.

## Critérios de aceite

- Usuário consegue autenticar.
- Sessão persiste ao reiniciar o app.
- Logout remove a sessão.
- Falha de autenticação exibe mensagem compreensível.
