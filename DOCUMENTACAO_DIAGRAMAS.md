# Documentação dos Diagramas UML do Sistema de Gerenciamento de Restaurante

## Como entender os diagramas UML deste projeto

Este projeto utiliza diferentes tipos de diagramas UML para representar, de forma visual e padronizada, o funcionamento do sistema de gerenciamento de restaurante. Cada diagrama tem um propósito específico e, juntos, eles mostram como as partes do sistema se relacionam, como os dados são organizados, como os processos acontecem e como os usuários interagem com o sistema. Veja abaixo um resumo de cada tipo de diagrama presente neste projeto:

- **Diagrama de Classes:** Mostra as principais entidades do sistema (como Cliente, Pedido, Funcionario, Mesa, etc.), seus atributos (dados) e os relacionamentos entre elas. É a base para entender como as informações são estruturadas e como as entidades se conectam. Também inclui enums (tipos de status) e modelagem de permissões, escalas de trabalho e ficha técnica dos pratos.

- **Diagrama de Atividade:** Representa o passo a passo do atendimento ao cliente, desde a chegada ao restaurante até o pagamento e liberação da mesa. Mostra o fluxo de ações, decisões e quem é responsável por cada etapa (recepcionista, sistema, garçom, cozinha, bar). Ajuda a visualizar o processo completo e identificar possíveis melhorias ou gargalos.

- **Diagramas de Sequência:** Detalham a ordem das interações entre os participantes do sistema em situações específicas. Por exemplo, o diagrama de sequência de registro de pedido mostra como cliente, garçom, sistema, estoque, cozinha e bar trocam mensagens para que um pedido seja realizado e processado. O diagrama de confirmação automática de reserva mostra como o sistema verifica a disponibilidade de mesas e confirma (ou não) a reserva para o cliente.

- **Diagrama de Casos de Uso:** Apresenta os principais atores (pessoas ou sistemas externos) e os casos de uso (funcionalidades) do sistema. Mostra quem pode fazer o quê, facilitando a compreensão das responsabilidades de cada papel e das funcionalidades disponíveis.

- **Diagramas de Estado:** Mostram os possíveis estados de entidades importantes (como Pedido e Reserva) e como elas transitam de um estado para outro ao longo do tempo (por exemplo, de "Aguardando Preparo" para "Em Preparo", ou de "Pendente" para "Confirmada"). São úteis para entender o ciclo de vida dessas entidades e as regras de negócio envolvidas.

Esses diagramas, juntos, permitem que qualquer integrante do grupo compreenda tanto a estrutura de dados quanto o funcionamento dos processos do sistema, mesmo sem conhecimento prévio de programação. Eles também facilitam a comunicação entre os membros do grupo e com professores ou clientes, servindo como referência para implementação, testes e futuras manutenções.

## 1. Diagrama de Classes (`diagrama_classes.puml`)
- **Descrição:** Modela as principais entidades do sistema, seus atributos e relacionamentos.
- **Destaques:**
  - Uso de enums para status e tipos (StatusPedido, StatusMesa, StatusReserva, TipoMesa, UnidadeMedida).
  - Modelagem de permissões (Permissao, CargoPermissao).
  - Estrutura para escalas de trabalho e turnos (EscalaFuncionario, Turno).
  - Ficha técnica de itens do cardápio (ComponenteItemCardapio).
  - Recursos para eventos (RecursoEvento).

## 2. Diagrama de Atividade (`Diagrama de Atividade.puml`)
- **Descrição:** Representa o fluxo completo de atendimento ao cliente, desde a recepção até o pagamento e liberação da mesa.
- **Destaques:**
  - Raias para cada ator/setor (Recepcionista, Sistema, Garçom, Cozinha, Bar).
  - Uso consistente dos enums StatusMesa.
  - Fluxo detalhado para diferentes formas de pagamento.

## 3. Diagrama de Sequência - Registrar Pedido (`DiagramaDeSequencia_RegistrarPedido.puml`)
- **Descrição:** Mostra a interação entre Cliente, Garçom, Sistema, Estoque, Cozinha e Bar no processo de registro de um pedido.
- **Destaques:**
  - Verificação de disponibilidade de itens no estoque.
  - Atualização de status do pedido e da mesa.
  - Envio automático de pedidos para cozinha e bar.

## 4. Diagrama de Sequência - Confirmação Automática de Reserva (`DiagramaDeSequencia_ConfirmacaoReserva.puml`)
- **Descrição:** Detalha o processo de confirmação automática de reservas (UC14), incluindo verificação de disponibilidade e atualização do status da reserva.
- **Destaques:**
  - Fluxo alternativo para reservas pendentes quando não há mesas disponíveis.
  - Uso do enum StatusReserva.

## 5. Diagrama de Casos de Uso (`diagrama de caso de uso.wsd`)
- **Descrição:** Apresenta os principais atores do sistema e suas interações com os casos de uso.
- **Destaques:**
  - Cobertura de todos os requisitos funcionais principais.
  - Relações <<include>> entre casos de uso.

## 6. Diagramas de Estado
- **Status do Pedido (`StatusPedido_Estados.puml`):**
  - Mostra o ciclo de vida do pedido, do registro ao pagamento/cancelamento.
- **Status da Reserva (`StatusReserva_Estados.puml`):**
  - Mostra o ciclo de vida da reserva, incluindo confirmação, check-in, no-show e cancelamentos.

---

**Observação:** Todos os diagramas utilizam enums e nomes padronizados para garantir consistência e rastreabilidade entre requisitos e modelagem.

**Para visualizar os diagramas:**
- Abra os arquivos `.puml` ou `.wsd` no PlantUML ou Visual Studio Code com extensão PlantUML.
- Os arquivos SVG gerados estão na pasta `diagramas/` para visualização rápida.
