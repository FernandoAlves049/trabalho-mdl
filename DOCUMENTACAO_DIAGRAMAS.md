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

## 🗂️ Resumo dos Diagramas

### 1. **Diagrama de Classes** [`diagrama_classes.puml`]
- **Descrição:** Modela as principais entidades do sistema, seus atributos e relacionamentos.
- **Destaques:**
  - Uso de enums para status e tipos (StatusPedido, StatusMesa, StatusReserva, TipoMesa, UnidadeMedida)
  - Modelagem de permissões (Permissao, CargoPermissao)
  - Estrutura para escalas de trabalho e turnos (EscalaFuncionario, Turno)
  - Ficha técnica de itens do cardápio (ComponenteItemCardapio)
  - Recursos para eventos (RecursoEvento)

### 2. **Diagrama de Atividade** [`Diagrama de Atividade.puml`]
- **Descrição:** Representa o fluxo completo de atendimento ao cliente, desde a recepção até o pagamento e liberação da mesa.
- **Destaques:**
  - Raias para cada ator/setor (Recepcionista, Sistema, Garçom, Cozinha, Bar)
  - Uso consistente dos enums StatusMesa
  - Fluxo detalhado para diferentes formas de pagamento

### 3. **Diagrama de Sequência - Registrar Pedido** [`DiagramaDeSequencia_RegistrarPedido.puml`]
- **Descrição:** Mostra a interação entre Cliente, Garçom, Sistema, Estoque, Cozinha e Bar no processo de registro de um pedido.
- **Destaques:**
  - Verificação de disponibilidade de itens no estoque
  - Atualização de status do pedido e da mesa
  - Envio automático de pedidos para cozinha e bar

### 4. **Diagrama de Sequência - Confirmação Automática de Reserva** [`DiagramaDeSequencia_ConfirmacaoReserva.puml`]
- **Descrição:** Detalha o processo de confirmação automática de reservas (UC14), incluindo verificação de disponibilidade e atualização do status da reserva.
- **Destaques:**
  - Fluxo alternativo para reservas pendentes quando não há mesas disponíveis
  - Uso do enum StatusReserva

### 5. **Diagrama de Casos de Uso** [`diagrama de caso de uso.wsd`]
- **Descrição:** Apresenta os principais atores do sistema e suas interações com os casos de uso.
- **Destaques:**
  - Cobertura de todos os requisitos funcionais principais
  - Relações `<<include>>` entre casos de uso

### 6. **Diagramas de Estado**
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

- **Fernando Alves de Souza** - [FernandoAlves049](https://github.com/FernandoAlves049)
- **Victor Hugo Marques Leite** - [TempestOFC](https://github.com/TempestOFC)
- **Felipe Montalvão Rodrigues** - [Felipemonrod](https://github.com/Felipemonrod)
- **Henrique Ferreira da Silva** - [Kobayashys](https://github.com/Kobayashys)