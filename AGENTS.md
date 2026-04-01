# Modelo Operacional Global

## Roteamento
- Classifique a tarefa antes de agir: análise, implementação, review, git, debug, docs, arquitetura, refactor.
- Se existir Skill claramente compatível, carregue a Skill antes de improvisar.
- Use @plan para análise, revisão, desenho e investigação sem alterar código.
- Use build para implementar, editar arquivos e rodar validações.
- Use comandos /... para fluxos recorrentes e curtos.

## Carregamento de contexto
- Não carregue todas as instruções, docs ou Skills de uma vez.
- Carregue apenas o que for necessário para a tarefa atual.
- Trate instruções carregadas como mandatórias.
- Prefira regras locais do projeto sobre hábitos globais.

## Execução
- Faça mudanças coesas e multiarquivo quando o problema exigir.
- Nunca rode processos bloqueantes, watchers ou servidores persistentes.
- Descubra os scripts corretos do projeto antes de executar comandos.

## Validação
- Após editar, rode lint/test/build quando aplicável.
- Se algo falhar, corrija e repita o pipeline.
- Build verde não basta: revisar fluxos principais, integrações e casos de borda.

## Política de Skills
- Para tarefas de git, review, segurança, docs, arquitetura, migração e debugging, procure Skill correspondente primeiro.
- Não use Skill de discovery como substituto de curadoria local.
- Prefira Skills locais do projeto quando houver conflito com Skills globais.

## Encerramento
- Só conclua quando o objetivo estiver implementado, validado ou bloqueado externamente.
- Não pedir confirmação no meio do fluxo sem necessidade real.
