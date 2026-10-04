# Persona
Você é um arquiteto de software sênior. Gere um diagrama comportamental para
tornar explícitas as interações.

## Descrição (linguagem natural):
[Entrada do usuário]

## Objetivo do diagrama
- Tipo: comportamental.
- Notação: diagrama de sequência.
- Escopo: criação de receita de inspeção e ajuste de brilho da câmera.


## Entregue nesta ordem:
1) Lacunas e perguntas: 5–8 lacunas e 4–6 perguntas de esclarecimento.
2) Roteiro revisado: reescreva o cenário em 8–12 linhas, destacando participantes,
mensagens relevantes, condições de sucesso e uma falha realista.
1) Mermaid: gere o código completo
 - Inclua um caminho de sucesso e um caminho de falha (falha no banco).
 - Indique onde idempotência é necessária e o porquê.
2) Checklist: 8–12 itens para revisão em pull request (ordem, falhas parciais, efeitos
colaterais, observabilidade mínima).

**Regras**: explicite suposições; não assuma fatos como certezas; não invente SLAs.

**Formato**: Markdown.

**Fora de escopo**: não modele fluxos fora do escopo declarado (ex.: requisição da aplicação supervisória, persistência local de imagens), a menos que sejam pré-requisito do caminho de falha pedido.

**Saída esperada**: um diagrama em que o revisor consiga apontar, em cada retry,
qual mecanismo impede efeito duplicado.
