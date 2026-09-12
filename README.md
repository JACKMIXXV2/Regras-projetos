# Regras-projetos — Lei Universal dos Projetos

Este repositório é a **fonte canônica de governança** para todos os projetos atuais e futuros de Jack/Midrato.

Ele não pertence a nenhum projeto específico. Projetos atuais e futuros são cidadãos desta lei.

A finalidade é simples: qualquer chat, agente, Codex ou ferramenta que entre em um projeto deve saber **como continuar, atacar, validar, persistir e reportar trabalho** sem inventar um método diferente a cada conversa.

## Princípio central

```text
Regras-projetos = lei-base universal
repos dos projetos = cidadãos autônomos
regras locais = leis específicas de cada cidadão
exceções autorizadas pelo usuário = podem prevalecer localmente
estado/checkpoints/builds = fatos atuais de cada cidadão
chat = contexto auxiliar
frontend/spinner = nunca fonte isolada de verdade
```

Não existe lista fechada de projetos cobertos.

Se um projeto pertence ao conjunto de projetos do usuário, esta governança se aplica por padrão, mesmo que seu nome nunca tenha aparecido neste repositório.

## Leitura obrigatória

Para qualquer projeto, atual ou futuro:

1. `CONSTITUTION.md`
2. `GLOBAL_RULES.md`
3. `GITHUB_PROTOCOL.md`
4. `AGENTS.md`
5. então o repositório do projeto: entrypoint, regras locais, HEAD, estado, checkpoint, evidências e fila atual
6. se o projeto for anterior a esta governança ou usar sistema legado, aplicar também `ADOPTION_PROTOCOL.md`

## Lei universal, regras locais e exceções

A lei universal é o comportamento padrão.

Cada projeto **pode e deve** possuir regras locais quando precisar de branches, gates, workflows, hardware, versionamento, relatórios, segurança, estrutura, releases ou qualquer outra especialização própria.

Uma regra local normalmente especializa a lei universal.

Ela também pode contrariar uma regra universal quando o usuário autorizar explicitamente a exceção para aquele projeto ou contexto. Nesse caso, a exceção deve ter escopo claro e, se for persistente, ficar registrada no próprio projeto.

Sem exceção autorizada, vale a regra universal.

## Hierarquia operacional padrão

```text
1. Regras universais deste repositório
2. Regras locais e exceções autorizadas do projeto
3. HEAD + estado/checkpoint/evidências persistidas do projeto
4. resultados de CI/build/runtime
5. histórico de conversa
6. estado visual do frontend/spinner
```

Uma instrução posterior do usuário pode substituir uma anterior sobre o mesmo assunto sem apagar fatos e evidências já produzidos.

Informações voláteis como versão, porcentagem, estágio, fila, commit, build, próximo alvo e gate permanecem no próprio projeto. Este repositório não deve virar um mural de números velhos.

## `ataca`

Em qualquer projeto governado por esta lei, `ataca` significa uma passagem **longa, autônoma, profunda e produtiva** no alvo atual.

Não significa fazer uma tentativa curta e pedir outro `continua`.

O ataque atravessa subtarefas, correções, testes, commits, builds, checkpoints e pivôs úteis enquanto houver trabalho executável e permitido. Checkpoints preventivos protegem progresso e não encerram o ataque.

## Continuidade, rollback e conclusão

A governança universal exige:

- checkpoints preventivos em trabalho longo quando houver risco de perda;
- preservação do último estado bom;
- rollback ou correção rastreável quando uma mudança causar regressão;
- proibição de remover trabalho válido apenas para simplificar a tarefa;
- Definition of Done baseada em implementação real + persistência + validação + evidência, não apenas em “código escrito”.

Detalhes estão em `GLOBAL_RULES.md` e `GITHUB_PROTOCOL.md`.

## GitHub é persistência

Mudança material que existe apenas no chat ou em workspace efêmero não está concluída.

O protocolo universal de leitura, escrita, SHA, branch, commit, CI, conflito, bug, artifact, checkpoint, rollback e migração está em `GITHUB_PROTOCOL.md`.

## Completude

Palavras como `tudo`, `completo`, `1:1`, `inteiro`, `absoluto`, `full`, `total` e equivalentes são literais, salvo redução explícita de escopo autorizada pelo usuário.

Se faltar qualquer parte do escopo pedido, o resultado é `INCOMPLETE` e deve dizer exatamente o que falta.

## Projetos legados

Projetos que nasceram antes desta governança não precisam fingir que sempre usaram este sistema.

`ADOPTION_PROTOCOL.md` define a portabilidade:

- preservar sistemas antigos úteis;
- preservar estado, evidências, checkpoints e regras locais;
- classificar conflitos em vez de apagá-los;
- registrar exceções autorizadas;
- migrar incrementalmente;
- manter compatibilidade com entrypoints antigos quando necessário;
- não interromper trabalho técnico produtivo apenas para reorganizar documentação.

A nova organização deve envolver a história existente, não apagá-la.

## Eficiência de ferramentas

Use a ferramenta mais direta capaz de executar o trabalho. Para GitHub, prefira o conector GitHub e scripts do próprio projeto. Não consuma Work/Codex só para operações simples que já podem ser feitas diretamente.

## Projetos futuros

Um projeto novo não precisa ser adicionado a uma lista neste repositório para ser governado.

Ele deve apenas:

1. reconhecer `Regras-projetos` como lei-base universal;
2. manter suas regras locais no próprio projeto;
3. registrar localmente exceções autorizadas pelo usuário;
4. persistir estado real no próprio repositório;
5. seguir os contratos universais aplicáveis.

## Emenda da lei

Mudanças nesta governança devem ser universais por natureza. Uma necessidade exclusiva de um único projeto normalmente pertence ao repositório daquele projeto, não aqui.

Este repositório deve permanecer pequeno, estável, genérico e reutilizável. A lei não precisa saber o nome de cada cidadão para continuar sendo lei.