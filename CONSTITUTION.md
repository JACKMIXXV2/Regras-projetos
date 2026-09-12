# CONSTITUTION.md — Constituição dos Projetos

## Artigo 1 — Natureza

`Regras-projetos` é a lei universal de governança dos projetos do usuário.

Ele não é um projeto de produto, não é um índice de projetos e não depende de uma lista de nomes para ter validade.

Todos os projetos atuais e futuros são tratados como cidadãos desta governança.

## Artigo 2 — Universalidade

A aplicação é automática.

Se um repositório, laboratório, mod, app, ferramenta, experimento ou workspace pertence aos projetos do usuário, estas regras se aplicam mesmo que esse projeto nunca tenha sido citado neste repositório.

Nenhuma atualização desta Constituição deve exigir adicionar cada projeto individualmente a uma tabela central.

## Artigo 3 — Supremacia

Hierarquia operacional:

```text
1. Constituição e regras universais de Regras-projetos
2. regras locais compatíveis do projeto
3. estado/checkpoints/evidências persistidos do projeto
4. resultados de CI/build/runtime
5. histórico de conversa
6. frontend/spinner
```

Uma regra local pode especializar a lei, mas não revogá-la.

Exemplo válido:

```text
Lei universal: confirme branch e HEAD antes de escrever.
Regra local: neste projeto, recuperação acontece na branch lab.
Resultado: use lab e confirme HEAD antes de escrever.
```

Exemplo inválido:

```text
Lei universal: não sobrescrever estado mais novo cegamente.
Regra local: pode substituir qualquer arquivo sem reler HEAD.
Resultado: regra local inválida por conflito.
```

## Artigo 4 — Autonomia dos projetos

Cada projeto mantém em seu próprio repositório:

- código;
- assets;
- ferramentas;
- regras técnicas específicas;
- branches;
- versionamento;
- estado atual;
- progresso;
- checkpoints;
- filas;
- gates;
- builds;
- evidências;
- histórico técnico necessário.

A Constituição não deve duplicar estado efêmero desses projetos.

## Artigo 5 — Cidadania de projeto

Um projeto é considerado governado assim que for tratado como projeto do usuário.

Para facilitar retomadas por agentes, recomenda-se que o repositório do projeto contenha um pequeno arquivo de ponte, por exemplo `PROJECT_GOVERNANCE.md`, apontando para:

```text
https://github.com/JACKMIXXV2/Regras-projetos
```

A ausência temporária desse arquivo não revoga a lei. Ele é um mecanismo de descoberta, não a fonte da autoridade.

## Artigo 6 — Projetos futuros

Ao criar um projeto novo:

1. aplicar esta Constituição desde o início;
2. manter regras locais apenas para necessidades específicas;
3. não copiar regras universais desnecessariamente;
4. criar um ponto de entrada local claro para estado e continuidade;
5. persistir progresso real no próprio repositório;
6. adicionar referência para `Regras-projetos` quando houver repositório GitHub.

O projeto não precisa ser cadastrado neste repositório central.

## Artigo 7 — Semântica universal de ataque

A palavra `ataca`, quando usada para autorizar trabalho em um projeto, possui a semântica definida em `GLOBAL_RULES.md`.

Nenhum projeto precisa redefinir esse comportamento. Pode apenas acrescentar gates e critérios técnicos específicos.

## Artigo 8 — Continuidade

Troca de chat, redução de contexto, bug de frontend, novo dispositivo ou novo agente não apagam trabalho persistido.

A retomada deve partir do estado canônico existente, não de reconstrução imaginária baseada em memória parcial.

## Artigo 9 — Evidência

Nenhum cidadão pode promover hipótese a fato só para melhorar barra, porcentagem ou sensação de avanço.

Quando algo não está provado, deve permanecer explicitamente não provado.

## Artigo 10 — Completude

Pedidos de completude literal obedecem `GLOBAL_RULES.md` em todos os projetos.

Nenhum projeto pode redefinir `completo` como `principais arquivos`, `amostra representativa` ou equivalente.

## Artigo 11 — GitHub

Todos os cidadãos que utilizam GitHub obedecem `GITHUB_PROTOCOL.md`.

Regras locais podem escolher branches, workflows e convenções, mas preservam os princípios universais de leitura antes de escrita, reconciliação, persistência, evidência e não sobrescrita cega.

## Artigo 12 — Eficiência

A governança deve reduzir trabalho repetido, não criar burocracia ornamental.

- não reler toda a história quando o checkpoint atual basta;
- não usar ferramentas pesadas quando uma ferramenta direta resolve;
- não interromper ataques por microetapas já autorizadas;
- não criar documentação redundante só para aumentar sensação de atividade.

## Artigo 13 — Emendas

Uma regra entra neste repositório somente quando for realmente universal ou estrutural.

Se uma regra só faz sentido para um projeto, ela pertence ao repositório desse projeto.

Emendas devem evitar nomes, versões, porcentagens ou detalhes temporários de cidadãos específicos, salvo exemplos claramente não normativos.

## Artigo 14 — Princípio final

A lei conhece o comportamento que os projetos devem seguir.

Ela não precisa conhecer cada projeto pelo nome.
