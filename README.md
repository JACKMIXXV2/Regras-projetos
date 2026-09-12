# Regras-projetos — Lei Universal dos Projetos

Este repositório é a **fonte canônica de governança** para todos os projetos atuais e futuros de Jack/Midrato.

Ele não pertence a Mid Pogo, Humo Negro, Walten, WinterWonder nem a qualquer projeto específico. Esses projetos são apenas cidadãos desta lei. Projetos que ainda nem existem também passam a obedecê-la quando forem criados.

A finalidade é simples: qualquer chat, agente, Codex ou ferramenta que entre em um projeto deve saber **como continuar, atacar, validar, persistir e reportar trabalho** sem inventar um método diferente a cada conversa.

## Princípio central

```text
Regras-projetos = lei universal
repos dos projetos = cidadãos
regras locais = regulamentos permitidos
estado/checkpoints/builds = fatos atuais de cada cidadão
chat = contexto auxiliar
frontend/spinner = nunca fonte de verdade
```

Não existe lista fechada de projetos cobertos.

Se um projeto pertence ao conjunto de projetos do usuário, esta governança se aplica por padrão, mesmo que o nome do projeto nunca tenha aparecido neste repositório.

## Leitura obrigatória

Para qualquer projeto, atual ou futuro:

1. `CONSTITUTION.md`
2. `GLOBAL_RULES.md`
3. `GITHUB_PROTOCOL.md`
4. `AGENTS.md`
5. então o repositório do projeto: entrypoint, regras locais, HEAD, estado, checkpoint, evidências e fila atual

O repositório do projeto pode definir detalhes próprios, como branches, gates, barras, versão, build, hardware-alvo, arquivos de boot ou ordem técnica. Ele **não pode contradizer a lei universal**.

## Hierarquia de autoridade operacional

```text
1. Regras universais deste repositório
2. Regras locais compatíveis do projeto
3. HEAD + estado/checkpoint/evidências persistidas do projeto
4. resultados de CI/build/runtime
5. histórico de conversa
6. estado visual do frontend/spinner
```

Quando houver conflito real entre uma regra local e a lei universal, a lei universal vence. Quando não houver conflito, a regra local especializa a lei para aquele projeto.

Informações voláteis como versão, porcentagem, estágio, fila, commit, build, próximo alvo e gate permanecem no próprio projeto. Este repositório não deve virar um mural de números velhos.

## `ataca`

Em qualquer projeto governado por esta lei, `ataca` significa uma passagem **longa, autônoma, profunda e produtiva** no alvo atual.

Não significa fazer uma tentativa curta e pedir outro `continua`.

O ataque atravessa subtarefas, correções, testes, commits, builds, checkpoints e pivôs úteis enquanto houver trabalho executável e permitido. As condições formais de parada estão em `GLOBAL_RULES.md`.

## GitHub é persistência

Mudança material que existe apenas no chat ou em workspace efêmero não está concluída.

O protocolo universal de leitura, escrita, SHA, branch, commit, CI, conflito, bug, artefato, migração e recuperação está em `GITHUB_PROTOCOL.md`.

## Completude

Palavras como `tudo`, `completo`, `1:1`, `inteiro`, `absoluto`, `full`, `total` e equivalentes são literais. Se faltar qualquer parte do escopo pedido, o resultado é `INCOMPLETE` e deve dizer exatamente o que falta.

## Eficiência de ferramentas

Use a ferramenta mais direta capaz de executar o trabalho. Para GitHub, prefira o conector GitHub e scripts do próprio projeto. Não consuma Work/Codex só para operações simples que já podem ser feitas diretamente.

## Projetos futuros

Um projeto novo não precisa ser adicionado a uma lista neste repositório para ser governado.

Ele deve apenas:

1. reconhecer `Regras-projetos` como lei superior de governança;
2. manter suas regras locais apenas para especializações necessárias;
3. persistir estado real no próprio repositório;
4. nunca copiar para cá estado efêmero que envelhece a cada versão;
5. seguir o contrato universal de adoção definido em `CONSTITUTION.md`.

## Emenda da lei

Mudanças nesta governança devem ser universais por natureza. Uma necessidade exclusiva de um único projeto normalmente pertence ao repositório daquele projeto, não aqui.

Este repositório deve permanecer pequeno, estável, genérico e reutilizável. A lei não precisa saber o nome de cada cidadão para continuar sendo lei.
