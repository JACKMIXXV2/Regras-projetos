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

## Leitura obrigatória

Para qualquer projeto:

1. `CONSTITUTION.md`
2. `GLOBAL_RULES.md`
3. `KEYWORDS.md`
4. `GITHUB_PROTOCOL.md`
5. `AGENTS.md`
6. `ADAPTATION_PROTOCOL.md` quando o projeto já possuir sistema próprio de governança/continuidade
7. então o repositório do projeto: entrypoint, regras locais, HEAD, estado, checkpoint, evidências e fila atual

## Palavras-chave universais

`KEYWORDS.md` define comandos operacionais estáveis.

```text
ataca = ataque contínuo + absoluto + exaustivo de todo o escopo aplicável

tudo = ataque contínuo quando usado operacionalmente + quantificador absoluto do conjunto indicado
```

`ataca` sozinho já significa cobrir integralmente o alvo atual, atravessando subtarefas, correções, checkpoints, testes, commits e pivôs úteis até esgotar o escopo executável.

Não existe uma palavra-chave especial `ataca tudo`. Essa expressão é apenas linguagem natural combinando duas palavras já definidas. Ela não ativa um nível superior de ataque, porque `ataca` já é exaustivo.

`tudo` também é quantificador literal. Não significa “os principais”, “o importante” ou “uma parte representativa”.

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

Informações voláteis como versão, porcentagem, estágio, fila, commit, build, próximo alvo e gate permanecem no próprio projeto.

## Continuidade, rollback e conclusão

A governança universal exige:

- checkpoints preventivos em trabalho longo quando houver risco de perda;
- preservação do último estado bom;
- rollback ou correção rastreável quando uma mudança causar regressão;
- proibição de remover trabalho válido apenas para simplificar a tarefa;
- Definition of Done baseada em implementação real + persistência + validação + evidência.

## Adaptação e convergência

Projetos ativos que já possuem sistemas próprios se adaptam segundo `ADAPTATION_PROTOCOL.md`.

Não existe regra “o mais novo manda” nem “o mais antigo manda”.

O objetivo é misturar o que existe de melhor:

- princípios universais;
- boas práticas locais já comprovadas;
- sistemas de continuidade existentes;
- necessidades específicas;
- exceções autorizadas;
- práticas locais que possam melhorar a própria lei universal.

Um projeto pode gerar uma prática classificada como `UNIVERSAL_CANDIDATE`. Com autorização do usuário, ela pode subir para a governança universal.

Assim, a adaptação é bidirecional: **a lei melhora os projetos e os projetos melhoram a lei**.

## GitHub é persistência

Mudança material que existe apenas no chat ou em workspace efêmero não está concluída.

O protocolo universal de leitura, escrita, SHA, branch, commit, CI, conflito, bug, artifact, checkpoint, rollback e migração está em `GITHUB_PROTOCOL.md`.

## Completude

Palavras como `tudo`, `completo`, `1:1`, `inteiro`, `absoluto`, `full`, `total` e equivalentes são literais, salvo redução explícita de escopo autorizada pelo usuário.

`ataca` também exige cobertura exaustiva do escopo atual mesmo quando nenhuma dessas palavras aparece.

Se faltar qualquer parte do escopo pedido, o resultado é `INCOMPLETE` e deve dizer exatamente o que falta.

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

## Evolução da lei

Mudanças nesta governança devem ser universais por natureza.

Uma necessidade exclusiva de um único projeto normalmente pertence ao próprio projeto.

Uma boa prática local que funcione para vários projetos pode ser promovida a regra universal com autorização do usuário.

Este repositório deve permanecer pequeno, estável, genérico e reutilizável.