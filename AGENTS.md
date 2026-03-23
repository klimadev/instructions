# AGENTS.md

## Objetivo
Maximizar velocidade de entrega com segurança, resolvendo a causa raiz com o menor custo total de iteração.

## Princípio Central
Não priorize o maior diff.
Priorize o menor diff suficiente para corrigir completamente o problema.
A mudança pode ser multi-arquivo se isso reduzir retrabalho.

## Política de Escopo
Escolha o escopo antes de editar:

### Use patch localizado quando:
- a causa raiz estiver clara e isolada
- a mudança afetar 1 módulo, componente ou função
- não houver contrato compartilhado sendo alterado

### Use edição multi-arquivo quando:
- houver tipos, schemas, serviços, rotas, hooks ou contratos cruzados
- corrigir só um arquivo criar inconsistência
- a mudança exigir atualização de chamadas, testes ou tipos relacionados

### Reescreva arquivo inteiro apenas quando:
- o arquivo for pequeno
- mais de 30% do arquivo precisar mudar
- a estrutura atual impedir uma correção segura e legível

## Limites Operacionais
- Prefira 1 a 4 arquivos por iteração
- 5 a 8 arquivos apenas se houver dependência real
- Evite mudanças amplas sem necessidade arquitetural
- Não faça refactor oportunista fora do escopo

## Preflight Obrigatório
Antes de editar:
1. Identifique a causa raiz
2. Localize os arquivos diretamente afetados
3. Verifique contratos, tipos e imports relacionados
4. Descubra os scripts reais do projeto
5. Escolha o menor escopo suficiente

## Estratégia de Edição
- Aplique mudanças relacionadas na mesma iteração
- Preserve padrões já usados no repositório
- Não renomeie APIs públicas sem necessidade
- Não altere arquivos não relacionados
- Prefira mudanças reversíveis e fáceis de validar

## Validação por Nível de Risco

### Baixo risco
Ex.: texto, markup, estilo local, ajuste pequeno de UI
- revisão lógica local
- lint/typecheck local se disponível

### Médio risco
Ex.: lógica de componente, hook, service isolado
- lint
- testes direcionados se existirem
- build apenas se necessário

### Alto risco
Ex.: contratos compartilhados, schema, rotas, auth, estado global, config, build
- lint
- testes
- build completo

## Comandos Proibidos
- dev servers persistentes
- watchers
- comandos interativos ou bloqueantes

## Comandos Permitidos
- lint
- typecheck
- testes direcionados
- build
- comandos equivalentes da stack

## Loop de Correção
Se falhar:
1. corrija a causa principal
2. corrija erros relacionados do mesmo escopo
3. revalide no menor escopo suficiente
4. só rode validação completa quando o risco justificar

## Budget de Iteração
- Até 2 tentativas amplas por tarefa
- Se falhar, reduza escopo
- Não entre em refactor em cascata

## Anti-padrões
- mudar arquivos demais sem necessidade
- corrigir sintoma sem causa raiz
- usar build verde como prova suficiente
- esperar o usuário testar algo obviamente verificável
- fazer refactor cosmético fora do escopo


Based on analysis of 100+ rules from PromptHub and GitHub repos:

Modular Code: "Prefer functional components; break into <300-line files with named exports."

Error Handling: "Wrap async calls in try-catch; surface user-friendly messages via toast."

TypeScript: "Use strict mode; define explicit interfaces for all props and API responses."

Testing: "Co-locate .test files; aim for >80% coverage on business logic."

Comments: "Explain the 'why', not the 'what'. Use JSDoc for public APIs."

State Management: "Colocate state; lift only when 2+ siblings need it. Prefer React Query for server state."

Performance: "Lazy-load routes; memoize expensive computations; virtualize long lists."

Accessibility: "Semantic HTML first; ARIA only when necessary; test with screen reader."

Security: "Sanitize inputs; use parameterized queries; never trust client data."

Git Hygiene: "Atomic commits; conventional commit messages; squash before merge."
