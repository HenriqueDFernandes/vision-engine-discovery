## Roteiro Revisado

**Escopo**
- Vision Engine responsável pela aquisição de imagens, processamento, inspeção, medição e disponibilização de resultados.
- Suporte a múltiplas câmeras simultaneamente em uma mesma instância.
- Integração bidirecional com CLPs para acionamento de inspeções e disponibilização de resultados.
- Integração com aplicação supervisória para configuração, monitoramento e consumo dos resultados.
- Inclusão apenas dos containers principais e integrações externas relevantes.

**Nível**
- Visão de Containers inspirada no modelo C4.

**Limites do Sistema**
- O Vision Engine não é responsável por sistemas corporativos, rastreabilidade empresarial ou gerenciamento da produção.
- A aplicação supervisória permanece responsável pela operação do processo e pela experiência principal do usuário.
- Rotinas de atualização automática e gerenciamento centralizado de versões estão fora do escopo atual.

**Responsabilidades**
- Abstrair a comunicação com diferentes modelos de câmeras.
- Gerenciar receitas e configurações de inspeção.
- Disponibilizar interface própria para configuração e manutenção dos pipelines.
- Executar pipelines de visão computacional, medições, inspeções e modelos de IA.
- Disponibilizar resultados, imagens e status operacional para sistemas consumidores.
- Permitir armazenamento opcional de imagens e resultados em disco local.

**Integrações**
- Câmeras industriais.
- CLPs e dispositivos industriais.
- Aplicação supervisória.
- Banco de dados local para receitas e configurações.
- Sistema de arquivos local para persistência opcional de imagens e resultados.

**Restrições**
- Implantação local (on-premise) em equipamentos industriais Windows.
- Operação contínua 24x7.
- Apenas uma receita ativa por instância em determinado momento.
- Não assumir tecnologias específicas de banco de dados, comunicação ou framework.
- Não detalhar componentes internos, classes, algoritmos ou estruturas de dados.
- Representar apenas responsabilidades, limites e relacionamentos entre containers.

**Premissas**
- Uma instância pode atender múltiplas câmeras simultaneamente.
- Configurações e receitas serão armazenadas em banco de dados integrado à aplicação.
- Imagens e resultados podem ser armazenados em diretórios locais do Windows.
- CLPs podem tanto iniciar inspeções quanto consumir resultados.
- Escalabilidade horizontal entre equipamentos não faz parte do escopo atual.

**Lacunas Remanescentes**
- Tecnologia da interface de configuração.
- Tecnologia do banco de dados.
- Protocolos de comunicação com CLPs.
- Protocolos de comunicação com a aplicação supervisória.
- Estratégia de retenção e limpeza de imagens armazenadas.
- Estratégia interna de execução e versionamento dos pipelines.