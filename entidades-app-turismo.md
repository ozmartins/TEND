# Modelo de Entidades — Aplicativo de Turismo Gamificado

Este documento descreve as entidades iniciais necessárias para a implementação do aplicativo de turismo gamificado.

---

## 1. Usuario

Representa uma pessoa cadastrada no aplicativo.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único do usuário. |
| `Nome` | `string` | Nome do usuário. |
| `Email` | `string` | Endereço de e-mail. |
| `FotoUrl` | `string?` | URL da foto de perfil. |
| `DataCadastro` | `DateTime` | Data e hora do cadastro. |
| `PontosTotais` | `int` | Saldo/pontuação total atual. |
| `Nivel` | `int` | Nível atual do usuário. |
| `UltimaLatitude` | `decimal?` | Última latitude conhecida. |
| `UltimaLongitude` | `decimal?` | Última longitude conhecida. |
| `UltimaAtualizacaoLocalizacao` | `DateTime?` | Data da última atualização da localização. |

---

## 2. PontoTuristico

Representa uma atração ou local que pode ser descoberto e visitado.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `Nome` | `string` | Nome da atração. |
| `Descricao` | `string` | Descrição turística/histórica. |
| `CategoriaId` | `Guid` | Categoria do ponto turístico. |
| `Latitude` | `decimal` | Latitude do local. |
| `Longitude` | `decimal` | Longitude do local. |
| `Endereco` | `string?` | Endereço da atração. |
| `Cidade` | `string` | Cidade. |
| `Estado` | `string` | Estado/UF. |
| `Pais` | `string` | País. |
| `RaioCheckinMetros` | `int` | Distância máxima permitida para check-in. |
| `PontosCheckin` | `int` | Pontos concedidos pela visita. |
| `ImagemPrincipalUrl` | `string?` | Imagem principal da atração. |
| `HorarioFuncionamento` | `string?` | Informações sobre funcionamento. |
| `SiteUrl` | `string?` | Site oficial ou página relacionada. |
| `Ativo` | `bool` | Indica se a atração está disponível no app. |

---

## 3. CategoriaPontoTuristico

Classifica os pontos turísticos.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `Nome` | `string` | Nome da categoria. |
| `Descricao` | `string?` | Descrição da categoria. |
| `Icone` | `string?` | Ícone ou identificador visual. |

Exemplos: História, Natureza, Museu, Cultura e Gastronomia.

---

## 4. ImagemPontoTuristico

Representa as imagens associadas a uma atração.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `PontoTuristicoId` | `Guid` | Ponto turístico relacionado. |
| `Url` | `string` | URL da imagem. |
| `Descricao` | `string?` | Legenda ou descrição da imagem. |
| `Ordem` | `int` | Ordem de apresentação. |

---

## 5. Visita

Registra uma visita/check-in realizado pelo usuário.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `UsuarioId` | `Guid` | Usuário responsável pela visita. |
| `PontoTuristicoId` | `Guid` | Local visitado. |
| `DataHora` | `DateTime` | Data e hora do check-in. |
| `Latitude` | `decimal` | Latitude registrada no check-in. |
| `Longitude` | `decimal` | Longitude registrada no check-in. |
| `PrecisaoGpsMetros` | `decimal?` | Precisão informada pelo GPS. |
| `DistanciaDoPontoMetros` | `decimal` | Distância calculada até a atração. |
| `PontosRecebidos` | `int` | Pontos concedidos pela visita. |
| `Validada` | `bool` | Indica se a visita foi considerada válida. |

---

## 6. Conquista

Define uma conquista que pode ser desbloqueada.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `Nome` | `string` | Nome da conquista. |
| `Descricao` | `string` | Descrição e condição da conquista. |
| `IconeUrl` | `string?` | Ícone ou medalha. |
| `Tipo` | `enum/string` | Tipo de condição utilizada. |
| `Meta` | `int` | Valor necessário para conclusão. |
| `PontosBonus` | `int` | Pontos concedidos ao desbloquear. |
| `Ativa` | `bool` | Indica se pode ser obtida. |

Tipos possíveis: `QuantidadeVisitas`, `QuantidadeCidades`, `Categoria` e `PontosAcumulados`.

---

## 7. ConquistaUsuario

Mantém o progresso de um usuário em uma conquista.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `UsuarioId` | `Guid` | Usuário relacionado. |
| `ConquistaId` | `Guid` | Conquista relacionada. |
| `ProgressoAtual` | `int` | Progresso atual. |
| `Concluida` | `bool` | Indica se foi desbloqueada. |
| `DataConclusao` | `DateTime?` | Data da conclusão. |
| `PontosRecebidos` | `int` | Pontos recebidos pela conquista. |

---

## 8. Desafio

Representa um desafio temporário ou permanente.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `Nome` | `string` | Nome do desafio. |
| `Descricao` | `string` | Descrição do objetivo. |
| `DataInicio` | `DateTime?` | Início da disponibilidade. |
| `DataFim` | `DateTime?` | Final da disponibilidade. |
| `PontosRecompensa` | `int` | Recompensa pela conclusão. |
| `Tipo` | `enum/string` | Tipo de desafio. |
| `Meta` | `int` | Quantidade necessária para conclusão. |
| `Ativo` | `bool` | Indica se está disponível. |

Exemplo: **Visite 3 atrações históricas de Criciúma.**

---

## 9. DesafioUsuario

Registra o progresso individual em um desafio.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `UsuarioId` | `Guid` | Usuário participante. |
| `DesafioId` | `Guid` | Desafio relacionado. |
| `ProgressoAtual` | `int` | Progresso atual. |
| `Concluido` | `bool` | Indica se o desafio foi concluído. |
| `DataConclusao` | `DateTime?` | Data da conclusão. |
| `PontosRecebidos` | `int` | Pontos recebidos. |

---

## 10. Nivel

Define os níveis de progressão disponíveis.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `Numero` | `int` | Número do nível. |
| `Nome` | `string` | Nome apresentado ao usuário. |
| `PontosMinimos` | `int` | Pontuação mínima para alcançar o nível. |
| `PontosMaximos` | `int?` | Limite superior do nível. |
| `IconeUrl` | `string?` | Ícone representativo. |

Exemplos:

- Nível 1 — Visitante
- Nível 5 — Explorador
- Nível 10 — Aventureiro

---

## 11. MovimentacaoPontos

Mantém o histórico de créditos e débitos de pontos.

| Propriedade | Tipo sugerido | Descrição |
|---|---|---|
| `Id` | `Guid` | Identificador único. |
| `UsuarioId` | `Guid` | Usuário relacionado. |
| `DataHora` | `DateTime` | Momento da movimentação. |
| `Quantidade` | `int` | Quantidade creditada ou debitada. |
| `Tipo` | `enum/string` | Origem/tipo da movimentação. |
| `OrigemId` | `Guid?` | Identificador da entidade que originou a movimentação. |
| `Descricao` | `string` | Descrição apresentada no extrato. |

Exemplos:

- `+120 — Visita à Mina Octávio Fontana`
- `+300 — Desafio Explorador de Criciúma`

---

# Relacionamentos principais

```text
Usuario
   |
   | 1:N
   |
Visita ---------------- PontoTuristico
                           |
                           N:1
                           |
                  CategoriaPontoTuristico
                           |
                           1:N
                           |
                  ImagemPontoTuristico

Usuario
   |
   +------ ConquistaUsuario ------ Conquista
   |
   +------ DesafioUsuario -------- Desafio
   |
   +------ MovimentacaoPontos
```

## Cardinalidades

- `Usuario 1:N Visita`
- `PontoTuristico 1:N Visita`
- `CategoriaPontoTuristico 1:N PontoTuristico`
- `PontoTuristico 1:N ImagemPontoTuristico`
- `Usuario N:N Conquista`, por meio de `ConquistaUsuario`
- `Usuario N:N Desafio`, por meio de `DesafioUsuario`
- `Usuario 1:N MovimentacaoPontos`

---

# Entidades recomendadas para o MVP

Para uma primeira versão funcional, priorizar:

1. `Usuario`
2. `PontoTuristico`
3. `CategoriaPontoTuristico`
4. `ImagemPontoTuristico`
5. `Visita`
6. `MovimentacaoPontos`
7. `Conquista`
8. `ConquistaUsuario`

As entidades `Desafio`, `DesafioUsuario` e `Nivel` podem ser implementadas posteriormente, sem impedir o funcionamento do fluxo principal de descoberta, visita, check-in e pontuação.
