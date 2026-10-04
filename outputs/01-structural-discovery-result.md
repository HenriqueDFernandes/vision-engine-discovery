# Structural Discovery Result

## Lacunas e Ambiguidades Identificadas

1. Não está definido onde serão armazenadas receitas, configurações de inspeção e parâmetros dos pipelines.
2. Não está claro se a persistência de imagens e resultados será responsabilidade do Vision Engine ou da aplicação web supervisória.
3. Não foi definido o modelo de implantação (edge industrial, servidor local, estação dedicada ou ambiente distribuído).
4. Não está especificado como ocorrerá a comunicação com CLPs e dispositivos industriais (protocolos, direção da comunicação e responsabilidades).
5. Não está definido se múltiplas câmeras poderão operar simultaneamente em uma mesma instância do sistema.
6. Não está claro se o Vision Engine deverá suportar múltiplas inspeções ou produtos em paralelo.
7. Não foi definido o mecanismo de configuração e versionamento dos pipelines de visão computacional.
8. Não existem requisitos explícitos de disponibilidade, tolerância a falhas ou recuperação após falhas.
9. Não está claro quais informações de status devem ser disponibilizadas aos sistemas consumidores.
10. Não foi definido se o acesso às imagens deve ocorrer em tempo real, sob demanda ou por meio de armazenamento persistente.

---

## Perguntas de Esclarecimento

1. Onde devem ser armazenadas receitas, configurações e parâmetros de inspeção?
2. O Vision Engine será implantado em um único equipamento industrial ou deverá suportar implantação distribuída?
3. O sistema deve suportar múltiplas câmeras simultaneamente na mesma instância?
4. A persistência de imagens e resultados é responsabilidade do Vision Engine ou da aplicação supervisória?
5. Como os CLPs irão interagir com o sistema: comando de inspeção, leitura de resultados ou ambos?
6. Existe necessidade de execução simultânea de múltiplas receitas ou produtos?
7. Como os pipelines de visão serão configurados e atualizados pelos usuários?
8. Existem requisitos mínimos de disponibilidade, redundância ou tempo máximo de parada?

---

## Decisões Arquiteturais Ainda em Aberto

- Estratégia de persistência de dados e imagens.
- Modelo de implantação (local, distribuído ou híbrido).
- Estratégia de gerenciamento de receitas.
- Modelo de configuração e execução dos pipelines.
- Estratégia de integração industrial.
- Requisitos de escalabilidade horizontal e vertical.
- Necessidade de armazenamento histórico dentro do Vision Engine.
- Definição dos contratos de comunicação entre Vision Engine e aplicação supervisória.

---

## Roteiro Revisado

**Escopo**
- Vision Engine responsável pela aquisição de imagens, processamento, inspeção, medição e disponibilização de resultados.
- Integração com câmeras industriais, CLPs e aplicação web supervisória.
- Inclusão apenas dos containers principais e integrações externas relevantes.

**Nível**
- Visão de Containers inspirada no modelo C4.

**Limites do Sistema**
- O Vision Engine não é responsável pela operação corporativa, rastreabilidade, cadastro de produtos ou experiência final do operador.
- A aplicação web supervisória permanece responsável pela interação principal com usuários.

**Responsabilidades**
- Abstrair comunicação com diferentes câmeras.
- Executar pipelines configuráveis de visão computacional.
- Realizar inspeções, medições e validações de conformidade.
- Disponibilizar resultados, status operacional e acesso às imagens.

**Integrações**
- Câmeras industriais.
- CLPs e dispositivos industriais.
- Aplicação web supervisória.
- Eventuais mecanismos de persistência ainda não definidos.

**Restrições**
- Não assumir tecnologias específicas, fabricantes, bancos de dados, brokers ou provedores cloud.
- Não detalhar componentes internos, classes, algoritmos ou estruturas de dados.
- Representar apenas responsabilidades, limites e relacionamentos entre containers.

**Lacunas Identificadas**
- Persistência.
- Implantação.
- Gerenciamento de receitas.
- Configuração dos pipelines.
- Escalabilidade.
- Disponibilidade.
- Contratos de integração industrial.