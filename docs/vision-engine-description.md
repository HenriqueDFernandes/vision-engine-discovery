r# Vision Engine

## Descrição

O Vision Engine é um sistema voltado para inspeção e medição industrial por visão computacional. Seu objetivo é executar processos de aquisição de imagens, processamento, inspeção e validação de resultados, disponibilizando essas informações para sistemas externos responsáveis pela operação e gestão do processo produtivo.

O sistema deve abstrair a comunicação com câmeras de diferentes fabricantes, executar pipelines configuráveis de visão computacional, realizar medições e verificações de conformidade com tolerâncias definidas e fornecer interfaces padronizadas de comunicação para integração com equipamentos e sistemas industriais.

O Vision Engine não possui responsabilidade sobre a interface de usuário final, fornecendo apenas uma interface mínima para configuração e operação básica de suas funcionalidades de inspeção e medição. A gestão de ensaios, cadastro de produtos, rastreabilidade corporativa ou integração direta com sistemas empresariais, são funções delegadas a uma aplicação web externa já existente, que atua como camada de supervisão e interação com operadores.

Entre as integrações previstas estão câmeras industriais, CLPs e um sistema web responsável pela configuração, monitoramento e armazenamento de informações corporativas. O Vision Engine deve disponibilizar resultados de inspeção, informações de status e acesso às imagens capturadas, permitindo que sistemas consumidores apresentem essas informações aos usuários finais.

A solução é destinada a ambientes industriais e deve priorizar modularidade, escalabilidade, interoperabilidade com diferentes dispositivos e independência em relação às aplicações consumidoras.

O sistema está em fase inicial de definição arquitetural e alguns aspectos, como estratégia de persistência, modelo de implantação, gerenciamento de receitas, mecanismo de configuração de pipelines e requisitos de disponibilidade, ainda dependem de detalhamento.

## Escopo

- Vision Engine
- Aplicação Web Supervisória
- Câmeras Industriais
- PLCs e dispositivos industriais
- Bancos de dados eventualmente necessários
- Serviços ou componentes internos relevantes para a execução das inspeções