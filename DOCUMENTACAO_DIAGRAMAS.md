# Documentação dos Diagramas UML do Sistema de Gerenciamento de Restaurante

Bem-vindo à documentação dos diagramas UML do projeto de Sistema de Gerenciamento de Restaurante! Aqui você encontrará uma visão clara e organizada de como o sistema foi modelado, facilitando o entendimento tanto para desenvolvedores quanto para interessados sem conhecimento técnico.

---

## 📚 Como entender os diagramas UML deste projeto

Este projeto utiliza diferentes tipos de diagramas UML para representar, de forma visual e padronizada, o funcionamento do sistema. Cada diagrama tem um propósito específico e, juntos, eles mostram:
- Como as partes do sistema se relacionam
- Como os dados são organizados
- Como os processos acontecem
- Como os usuários interagem com o sistema

> **Dica:** Os diagramas facilitam a comunicação entre membros do grupo, professores e clientes, servindo como referência para implementação, testes e futuras manutenções.

---

## 🧩 O que representa cada diagrama UML deste projeto

- **🏷️ Diagrama de Classes:**
  Este diagrama apresenta a estrutura fundamental do sistema, mostrando todas as principais entidades (como Cliente, Pedido, Funcionário, Mesa, Reserva, etc.), seus atributos (dados que cada entidade armazena) e os relacionamentos entre elas (como "um Pedido pertence a um Cliente" ou "uma Reserva pode envolver várias Mesas"). Ele também evidencia o uso de enums (tipos padronizados de status, como StatusPedido ou StatusMesa), além de modelar permissões, escalas de trabalho, ficha técnica dos pratos e recursos para eventos. É essencial para entender como as informações são organizadas e como as diferentes partes do sistema se conectam.

- **🔄 Diagrama de Atividade:**
  Este diagrama detalha o fluxo completo de atendimento ao cliente no restaurante, desde a chegada até o pagamento e liberação da mesa. Ele utiliza raias para separar as responsabilidades de cada ator/setor (Recepcionista, Sistema, Garçom, Cozinha, Bar), mostrando claramente quem faz o quê em cada etapa. O diagrama inclui decisões (como "há mesas disponíveis?"), fluxos alternativos (como lista de espera), paralelismos (preparo de comida e bebida ao mesmo tempo) e diferentes formas de pagamento. É ideal para visualizar processos, identificar gargalos e propor melhorias no atendimento.

- **⏩ Diagrama de Sequência:**
  Existem dois diagramas de sequência principais neste projeto:
  - **Registrar Pedido:** Mostra, passo a passo, como Cliente, Garçom, Sistema, Estoque, Cozinha e Bar interagem para registrar e processar um pedido. Detalha desde a escolha do pedido até a entrega na mesa, incluindo verificação de estoque, atualização de status e comunicação entre setores.
  - **Confirmação Automática de Reserva:** Detalha o processo de confirmação de reservas, incluindo a verificação de disponibilidade de mesas, sugestão de alternativas caso não haja disponibilidade e atualização do status da reserva. Mostra como o sistema lida com fluxos alternativos, como lista de espera ou reagendamento.
  Esses diagramas são fundamentais para entender a ordem e o conteúdo das mensagens trocadas entre os participantes do sistema em situações reais.

- **👤 Diagrama de Casos de Uso:**
  Este diagrama apresenta todos os atores do sistema (pessoas ou sistemas externos, como Gerente, Garçom, Recepcionista, Chef, etc.) e os principais casos de uso (funcionalidades) disponíveis, como "Gerenciar Funcionários", "Registrar Pedido", "Gerenciar Reservas", entre outros. Ele mostra quem pode executar cada ação e as relações de inclusão entre casos de uso (<<include>>), facilitando a visualização dos requisitos funcionais e das responsabilidades de cada papel no sistema.

- **🔁 Diagramas de Estado:**
  São dois diagramas que mostram o ciclo de vida das principais entidades dinâmicas do sistema:
  - **Status do Pedido:** Exibe todos os estados possíveis de um pedido (Aguardando Preparo, Em Preparo, Pronto para Entrega, Entregue, Pago, Cancelado) e as transições entre eles, como "Pedido criado", "Iniciar preparo", "Pagamento realizado" ou "Cancelamento". Ajuda a entender as regras de negócio e os possíveis caminhos de um pedido.
  - **Status da Reserva:** Mostra os estados de uma reserva (Pendente de Confirmação, Confirmada, Check-in, Concluída, No-show, Cancelada pelo Cliente, Cancelada pelo Restaurante) e como as reservas transitam entre esses estados, incluindo situações como confirmação, chegada do cliente, não comparecimento ou cancelamento. Esclarece o ciclo de vida das reservas e as ações possíveis em cada etapa.

---

## 🗂️ Resumo dos Diagramas

### 1. 🏷️ **Diagrama de Classes** [`diagrama_classes.puml`]
- **Descrição:** Modela as principais entidades do sistema, seus atributos e relacionamentos.
- **Destaques:**
  - Uso de enums para status e tipos (StatusPedido, StatusMesa, StatusReserva, TipoMesa, UnidadeMedida)
  - Modelagem de permissões (Permissao, CargoPermissao)
  - Estrutura para escalas de trabalho e turnos (EscalaFuncionario, Turno)
  - Ficha técnica de itens do cardápio (ComponenteItemCardapio)
  - Recursos para eventos (RecursoEvento)

### 2. 🔄 **Diagrama de Atividade** [`Diagrama de Atividade.puml`]
- **Descrição:** Representa o fluxo completo de atendimento ao cliente, desde a recepção até o pagamento e liberação da mesa.
- **Destaques:**
  - Raias para cada ator/setor (Recepcionista, Sistema, Garçom, Cozinha, Bar)
  - Uso consistente dos enums StatusMesa
  - Fluxo detalhado para diferentes formas de pagamento

### 3. ⏩ **Diagrama de Sequência - Registrar Pedido** [`DiagramaDeSequencia_RegistrarPedido.puml`]
- **Descrição:** Mostra a interação entre Cliente, Garçom, Sistema, Estoque, Cozinha e Bar no processo de registro de um pedido.
- **Destaques:**
  - Verificação de disponibilidade de itens no estoque
  - Atualização de status do pedido e da mesa
  - Envio automático de pedidos para cozinha e bar

### 4. ⏩ **Diagrama de Sequência - Confirmação Automática de Reserva** [`DiagramaDeSequencia_ConfirmacaoReserva.puml`]
- **Descrição:** Detalha o processo de confirmação automática de reservas (UC14), incluindo verificação de disponibilidade e atualização do status da reserva.
- **Destaques:**
  - Fluxo alternativo para reservas pendentes quando não há mesas disponíveis
  - Uso do enum StatusReserva

### 5. 👤 **Diagrama de Casos de Uso** [`diagrama de caso de uso.wsd`]
- **Descrição:** Apresenta os principais atores do sistema e suas interações com os casos de uso.
- **Destaques:**
  - Cobertura de todos os requisitos funcionais principais
  - Relações `<<include>>` entre casos de uso

### 6. 🔁 **Diagramas de Estado**
- **Status do Pedido** [`StatusPedido_Estados.puml`]:
  - Mostra o ciclo de vida do pedido, do registro ao pagamento/cancelamento.
- **Status da Reserva** [`StatusReserva_Estados.puml`]:
  - Mostra o ciclo de vida da reserva, incluindo confirmação, check-in, no-show e cancelamentos.

---

## 📝 Observações Importantes
- Todos os diagramas utilizam enums e nomes padronizados para garantir **consistência** e **rastreabilidade** entre requisitos e modelagem.
- Os arquivos `.puml` e `.wsd` podem ser abertos no PlantUML ou no Visual Studio Code com a extensão PlantUML.
- Versões SVG dos diagramas estão disponíveis na pasta `diagramas/` para visualização rápida.

---

## 👨‍💻 Autores

- <img src="https://github.com/FernandoAlves049.png" width="32" height="32" style="vertical-align:middle; border-radius:50%;" /> **Fernando Alves de Souza** - [FernandoAlves049](https://github.com/FernandoAlves049)
- <img src="https://github.com/TempestOFC.png" width="32" height="32" style="vertical-align:middle; border-radius:50%;" /> **Victor Hugo Marques Leite** - [TempestOFC](https://github.com/TempestOFC)
- <img src="https://github.com/Felipemonrod.png" width="32" height="32" style="vertical-align:middle; border-radius:50%;" /> **Felipe Montalvão Rodrigues** - [Felipemonrod](https://github.com/Felipemonrod)
- <img src="https://github.com/Kobayashys.png" width="32" height="32" style="vertical-align:middle; border-radius:50%;" /> **Henrique Ferreira da Silva** - [Kobayashys](https://github.com/Kobayashys)