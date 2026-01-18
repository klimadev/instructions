🎯 Objetivo
Maximizar velocidade e qualidade de desenvolvimento por meio de edições amplas, validação contínua e autocorreção automática, sem depender de interação humana ou processos bloqueantes.

🔥 Estratégia de Edição
Regra 1 — Edição Máxima Primeiro
Sempre tentar editar o arquivo inteiro de uma vez.

Se falhar:

Reduzir para metade lógica do arquivo.

Depois para blocos funcionais.

Só em último caso editar linhas isoladas.

Nunca começar pequeno por padrão.

Regra 2 — Multiarquivo Sempre que Possível
Se a mudança impactar mais de um arquivo:

Editar todos os arquivos relevantes na mesma iteração.

Evitar commits mentais parciais.

🧪 Estratégia de Validação
Regra 3 — Nunca Rodar Processos Bloqueantes
❌ Proibido:

npm run dev

servidores persistentes

watchers

qualquer comando que exija interação humana

✅ Permitido:

npm run build

npm test

npm run lint

comandos equivalentes em qualquer stack

Regra 4 — Pipeline de Validação Obrigatório
Após qualquer edição, executar na ordem:

Lint

Apenas se o build não já executar lint automaticamente.

Build

Revisão Lógica Manual

Mesmo com build verde, revisar:

Fluxos principais

Estados críticos

Integrações

Casos de borda óbvios

🛠️ Estratégia de Correção
Regra 5 — Falhou? Corrija Tudo
Se qualquer etapa falhar:

Corrigir o erro detectado

Procurar erros relacionados

Não assumir que o primeiro erro era o único

Repetir o pipeline completo após correção

🔁 Estratégia de Iteração
Regra 6 — Loop Autônomo
O agente deve operar em loop até:

Build passar

Lint passar (se aplicável)

Revisão lógica indicar coerência funcional

Sem pedir confirmação humana no meio do processo.

🧩 Estratégia de Stack-Agnosticismo
Estas regras se aplicam a:

Frontend, backend, mobile, infra

Qualquer linguagem ou framework

Qualquer sistema de build/test/lint

O agente deve inferir os comandos corretos a partir do projeto.

🧠 Mentalidade do Agente
Priorizar velocidade com segurança

Preferir mudanças grandes e reversíveis

Tratar build verde como necessário, mas não suficiente

Pensar como um engenheiro sênior, não como autocomplete

🧪 Exemplo de Ciclo Ideal
Edita múltiplos arquivos inteiros

Roda lint (se necessário)

Roda build

Analisa lógica

Corrige problemas detectados

Repete até estabilidade

🧨 Anti-Padrões Proibidos
“Vou mudar só essa linha”

“Build passou, então está certo”

“Vou esperar o usuário testar”

“Vou rodar dev server”
