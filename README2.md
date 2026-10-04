# Vision Engine Discovery

Repositório criado para registrar a atividade de *Discovery Arquitetural* do Vision Engine, utilizando engenharia de prompts para obtenção e refinamento de artefatos arquiteturais baseados em IA.

O objetivo do trabalho é transformar uma descrição inicial do sistema em artefatos arquiteturais estruturais e comportamentais progressivamente refinados, passando por identificação de lacunas, definição de premissas, modelagem de containers, validação de dependências e modelagem de fluxos de interação.

---

# Objetivos

- Estruturar o conhecimento inicial do produto.
- Identificar lacunas arquiteturais e decisões ainda não tomadas.
- Consolidar premissas e limites do sistema.
- Gerar diagramas arquiteturais estruturais e comportamentais.
- Comparar diferentes formas de representação arquitetural.
- Produzir artefatos reutilizáveis para etapas posteriores de arquitetura.

---

# Estrutura do Repositório

```text
.
├── docs
│   ├── roteiro-revisado.md
│   └── vision-engine-description.md
│
├── outputs
│   ├── 01-structural-discovery-result.md
│   ├── 02-container-diagram.md
│   ├── 02-diagram-mermaid.mmd
│   ├── 02-plant-uml-diagram.puml
│   ├── 02-plant-uml-diagram.png
│   ├── 03-diagram_sequence_recipe.md
│   └── 03-plant-uml-sequence-diagram.puml
│
└── prompts
    ├── prompt-01.md
    ├── prompt-02.md
    └── prompt-03.md
```

---

# Processo Executado

## Etapa 1 - Discovery Estrutural

A partir da descrição inicial do Vision Engine foi executado um processo de descoberta arquitetural com foco em:

- escopo do sistema;
- limites arquiteturais;
- responsabilidades;
- integrações externas;
- restrições;
- lacunas e ambiguidades.

Como resultado foram identificadas perguntas de esclarecimento e decisões arquiteturais pendentes.

Artefato gerado:

```text
outputs/01-structural-discovery-result.md
```

---

## Etapa 2 - Refinamento do Escopo

Após responder às principais dúvidas identificadas pelo processo de discovery, foi elaborado um roteiro consolidado contendo:

- objetivos do sistema;
- premissas arquiteturais;
- responsabilidades;
- integrações;
- restrições;
- lacunas remanescentes.

Artefato utilizado:

```text
docs/roteiro-revisado.md
```

---

## Etapa 3 - Modelagem de Containers

A partir do roteiro revisado foi gerado um diagrama arquitetural de containers representando:

- Vision Engine UI
- Vision Engine Core
- Processing Engine
- Configuration Database
- Local Storage
- CLP
- Aplicação Supervisória
- Câmeras Industriais

O objetivo foi demonstrar os principais relacionamentos e dependências do sistema sem detalhar aspectos internos de implementação.

Artefatos gerados:

```text
outputs/02-container-diagram.md
outputs/02-diagram-mermaid.mmd
outputs/02-plant-uml-diagram.puml
```

---

## Etapa 4 - Modelagem Comportamental

Após a definição estrutural da arquitetura, foi criado um diagrama de sequência representando um fluxo típico de execução de uma receita de inspeção.

O objetivo desta etapa foi complementar a visão estática dos containers com uma visão dinâmica das interações entre os principais elementos do sistema.

Artefatos gerados:

```text
outputs/03-diagram_sequence_recipe.md
outputs/03-plant-uml-sequence-diagram.puml
```

---

# Diagramas

## Diagramas Estruturais

### Container Diagram (Mermaid)

Arquivo fonte:

```text
outputs/02-diagram-mermaid.mmd
```

### Container Diagram (PlantUML)

Arquivos:

```text
outputs/02-plant-uml-diagram.puml
outputs/02-plant-uml-diagram.png
```

Foi criada também uma versão em PlantUML para comparar legibilidade, organização visual e manutenção em relação à versão Mermaid.

---

## Diagramas Comportamentais

### Sequence Diagram (Mermaid)

Arquivo:

```text
outputs/03-diagram_sequence_recipe.md
```

Representa o fluxo principal de execução de uma receita de inspeção no Vision Engine.

### Sequence Diagram (PlantUML)

Arquivo:

```text
outputs/03-plant-uml-sequence-diagram.puml
```

Foi mantido para comparação entre as notações e para documentação arquitetural complementar.

---

# Decisões e Ajustes Realizados

## Definição da Implantação

Foi definido que o Vision Engine será executado localmente em equipamentos industriais Windows, sem considerar neste momento mecanismos centralizados de atualização ou gerenciamento remoto.

## Suporte a Múltiplas Câmeras

Uma única instância do sistema pode operar simultaneamente com múltiplas câmeras industriais.

## Separação entre Core e Processamento

A arquitetura foi dividida em dois containers principais:

- Vision Engine Core
- Processing Engine

Essa divisão visa desacoplar atividades administrativas e de orquestração das rotinas computacionalmente intensivas de visão computacional.

## Interface Própria de Configuração

Foi assumida a existência de uma interface dedicada para:

- configuração de receitas;
- configuração de pipelines;
- monitoramento;
- diagnóstico.

## Persistência de Configurações

Receitas e configurações foram modeladas em um banco de dados local integrado à aplicação.

A tecnologia específica não foi definida nesta etapa.

## Persistência de Imagens

A gravação de imagens e resultados foi considerada opcional e realizada através do sistema de arquivos local.

## Integração Industrial

A comunicação com CLPs foi representada como bidirecional:

- acionamento de inspeções;
- leitura de resultados;
- consulta de status.

Os protocolos específicos permaneceram fora do escopo.

## Comparação entre Notações

Durante a atividade foram produzidas versões equivalentes dos diagramas utilizando Mermaid e PlantUML.

Observações registradas:

- Para diagramas de containers, a versão PlantUML apresentou melhor organização visual.
- Para diagramas de sequência, Mermaid e PlantUML apresentaram resultados equivalentes em clareza.
- Mermaid facilita a visualização direta em plataformas compatíveis com Markdown.
- PlantUML foi mantido como alternativa para documentação arquitetural.

---

# Lacunas Permanecem em Aberto

As seguintes decisões ainda exigem aprofundamento em etapas futuras:

- tecnologia da interface de configuração;
- tecnologia do banco de dados;
- protocolos de comunicação industrial;
- protocolos de integração com aplicações externas;
- estratégia de retenção de imagens;
- versionamento de pipelines;
- mecanismo de distribuição de configurações;
- monitoramento e observabilidade.

---

# Próximos Passos

As próximas etapas de evolução arquitetural deverão incluir:

1. Discovery de Componentes.
2. Modelagem de Componentes.
3. Fluxos comportamentais adicionais.
4. Modelagem de Integrações.
5. Definição de Persistência.
6. Modelagem de Implantação.
7. Definição de Requisitos Não Funcionais.
8. Estratégia de Observabilidade e Operação 24x7.
9. Evolução para uma arquitetura de referência do produto.

---
