# Lacunas Identificadas e Suposições Adotadas

1. Tecnologia da interface de configuração

    - Suposição S1: A interface será modelada como um container independente chamado Vision Engine UI, sem assumir tecnologia específica.

2. Tecnologia do banco de dados

    - Suposição S2: Existe um único container de persistência para receitas e configurações denominado Configuration Database.

3. Protocolos de comunicação com CLPs

    - Suposição S3: A comunicação é abstraída pelo Vision Engine Core, sem representar protocolos específicos.

4. Protocolos de comunicação com a aplicação supervisória

    - Suposição S4: A integração ocorre através do Vision Engine Core, sem detalhamento tecnológico.

5. Estratégia de retenção de imagens

    - Suposição S5: O armazenamento local é opcional e gerenciado pelo sistema de forma transparente.

6. Versionamento e execução dos pipelines

    - Suposição S6: O gerenciamento dos pipelines é responsabilidade do Vision Engine Core e sua execução do Processing Engine.

# Suposições

- S1: Existe uma interface dedicada para configuração e monitoramento do Vision Engine.
- S2: Configurações e receitas são armazenadas em um banco de dados local integrado ao sistema.
- S3: O Core centraliza toda comunicação industrial com CLPs.
- S4: O Core centraliza toda comunicação com aplicações consumidoras de resultados.
- S5: O armazenamento de imagens e resultados é opcional e persistido em disco local.
- S6: O processamento de visão computacional é desacoplado da orquestração do sistema.

# Mermaid
```
flowchart LR
    USER["Analista / Integrador"]
    UI["Vision Engine UI"]
    CORE["Vision Engine Core"]
    PROC["Processing Engine"]

    DB[("Configuration Database")]
    STORAGE["Local Storage"]

    CAMERAS["Câmeras Industriais"]
    PLC["CLP"]
    SUPERVISORY["Aplicação Supervisória"]

    USER -->|Configuração e Monitoramento| UI

    UI -->|Gerencia receitas, configurações e pipelines| CORE

    CORE -->|Ler/Gravar configurações| DB

    CORE -->|Solicita inspeções e executa pipelines| PROC

    PROC -->|Aquisição de imagens| CAMERAS

    PLC -->|Comandos de inspeção| CORE
    CORE -->|Resultados e status operacional| PLC

    SUPERVISORY -->|Solicitações| CORE
    CORE -->|Resultados e status| SUPERVISORY

    CORE -->|Persistência opcional| STORAGE
    PROC -->|Imagens e evidências| STORAGE
```

# Checklist de Revisão Estrutural
 
 
 - [ ] Todos os elementos representados são containers ou sistemas externos.
 - [ ] Não há mistura entre níveis C4 (Container, Componente ou Classe).
 - [ ] O Vision Engine Core está claramente identificado como orquestrador central.
 - [ ] O Processing Engine possui responsabilidade exclusiva de processamento de visão.
 - [ ] A interface do usuário não acessa diretamente banco de dados ou câmeras.
 - [ ] O banco de dados é utilizado apenas para receitas e configurações.
 - [ ] O armazenamento local é tratado como persistência opcional.
 - [ ] Câmeras industriais aparecem apenas como fonte de imagens.
 - [ ] A integração com CLPs ocorre exclusivamente através do Core.
 - [ ] A aplicação supervisória consome resultados através do Core.
 - [ ] Dependências seguem direção lógica de responsabilidade.
 - [ ] Nenhuma dependência tecnológica específica foi assumida no modelo.