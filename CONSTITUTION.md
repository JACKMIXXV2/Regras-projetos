# CONSTITUTION.md — Constituição dos Projetos

## Artigo 1 — Natureza

`Regras-projetos` é a lei universal de governança dos projetos do usuário.

Ele não é um projeto de produto, não é um índice de projetos e não depende de uma lista de nomes para ter validade.

Todos os projetos atuais e futuros são tratados como cidadãos desta governança.

## Artigo 2 — Universalidade

A aplicação é automática.

Se um repositório, laboratório, mod, app, ferramenta, experimento ou workspace pertence aos projetos do usuário, estas regras se aplicam mesmo que esse projeto nunca tenha sido citado neste repositório.

Nenhuma atualização desta Constituição deve exigir adicionar cada projeto individualmente a uma tabela central.

## Artigo 3 — Hierarquia e regras locais

A lei universal é a base padrão de todos os projetos, mas **regras locais são esperadas e necessárias** quando um projeto possui necessidades próprias.

Hierarquia operacional normal:

```text
1. Constituição e regras universais de Regras-projetos
2. regras locais do projeto
3. estado/checkpoints/evidências persistidos do projeto
4. resultados de CI/build/runtime
5. histórico de conversa
6. frontend/spinner
```

Uma regra local pode especializar a aplicação da lei para aquele projeto.

Exemplo:

```text
Lei universal: confirme branch e HEAD antes de escrever.
Regra local: neste projeto, recuperação acontece na branch lab.
Resultado: use lab e confirme HEAD antes de escrever.
```

## Artigo 4 — Exceções locais autorizadas pelo usuário

Uma regra local **pode contrariar ou substituir uma regra universal** quando o usuário autorizar explicitamente essa exceção para aquele projeto, contexto ou operação.

Uma exceção autorizada:

- deve ter escopo claro;
- deve ser registrada no próprio projeto quando for persistente;
- não altera a Constituição para os demais projetos;
- não deve ser presumida por semelhança com outro projeto;
- pode ser revogada ou modificada por instrução posterior do usuário;
- vale apenas dentro dos limites da autorização concedida.

Sem autorização explícita para a exceção, vale a regra universal.

A instrução mais recente do usuário sobre o mesmo assunto prevalece sobre uma instrução anterior, preservando-se fatos, evidências e histórico já produzidos.

## Artigo 5 — Autonomia dos projetos

Cada projeto mantém em seu próprio repositório:

- código;
- assets;
- ferramentas;
- regras técnicas específicas;
- exceções autorizadas;
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

## Artigo 6 — Cidadania de projeto

Um projeto é considerado governado assim que for tratado como projeto do usuário.

Para facilitar retomadas por agentes, recomenda-se que o repositório do projeto contenha um pequeno arquivo de ponte, por exemplo `PROJECT_GOVERNANCE.md`, apontando para:

```text
https://github.com/JACKMIXXV2/Regras-projetos
```

A ausência temporária desse arquivo não revoga a lei. Ele é um mecanismo de descoberta, não a fonte da autoridade.

## Artigo 7 — Projetos futuros

Ao criar um projeto novo:

1. aplicar esta Constituição desde o início;
2. manter regras locais para necessidades específicas;
3. registrar localmente exceções autorizadas pelo usuário;
4. não copiar regras universais desnecessariamente;
5. criar um ponto de entrada local claro para estado e continuidade;
6. persistir progresso real no próprio repositório;
7. adicionar referência para `Regras-projetos` quando houver repositório GitHub.

O projeto não precisa ser cadastrado neste repositório central.

## Artigo 8 — Projetos legados e portabilidade

Projetos criados antes desta Constituição não devem ser reestruturados cegamente nem tratados como incorretos por utilizarem sistemas antigos de regras, handoff, continuidade, branches ou checkpoints.

Sua adoção deve obedecer `ADOPTION_PROTOCOL.md`.

Princípios obrigatórios da portabilidade:

- preservar continuidade e estado já validado;
- preservar regras locais úteis;
- classificar conflitos em vez de apagá-los;
- registrar exceções autorizadas;
- adaptar a organização sem reiniciar o projeto;
- permitir migração incremental sem congelar trabalho técnico produtivo.

A nova governança deve envolver o projeto existente, não destruir sua história para fingir que ele nasceu hoje.

## Artigo 9 — Semântica universal de ataque

A palavra `ataca`, quando usada para autorizar trabalho em um projeto, possui a semântica definida em `GLOBAL_RULES.md`.

Nenhum projeto precisa redefinir esse comportamento. Pode acrescentar gates, critérios técnicos e exceções locais autorizadas.

## Artigo 10 — Continuidade

Troca de chat, redução de contexto, bug de frontend, novo dispositivo ou novo agente não apagam trabalho persistido.

A retomada deve partir do estado canônico existente, não de reconstrução imaginária baseada em memória parcial.

## Artigo 11 — Evidência

Nenhum cidadão pode promover hipótese a fato só para melhorar barra, porcentagem ou sensação de avanço.

Quando algo não está provado, deve permanecer explicitamente não provado.

## Artigo 12 — Completude

Pedidos de completude literal obedecem `GLOBAL_RULES.md` em todos os projetos, salvo exceção específica de escopo autorizada pelo usuário.

Nenhum agente pode redefinir sozinho `completo` como `principais arquivos`, `amostra representativa` ou equivalente.

## Artigo 13 — GitHub

Todos os cidadãos que utilizam GitHub obedecem `GITHUB_PROTOCOL.md`.

Regras locais podem escolher branches, workflows, convenções e políticas próprias. Exceções ao protocolo universal também podem existir quando autorizadas explicitamente pelo usuário e registradas no projeto.

## Artigo 14 — Eficiência

A governança deve reduzir trabalho repetido, não criar burocracia ornamental.

- não reler toda a história quando o checkpoint atual basta;
- não usar ferramentas pesadas quando uma ferramenta direta resolve;
- não interromper ataques por microetapas já autorizadas;
- não criar documentação redundante só para aumentar sensação de atividade.

## Artigo 15 — Não sabotagem

Nenhum agente deve remover deliberadamente funcionalidade válida, evidência, ferramenta, arquivo, compatibilidade ou estado útil apenas para simplificar o trabalho, reduzir o escopo ou contornar uma limitação própria.

Mudanças que removem comportamento validado exigem motivo técnico real, rastreabilidade e, quando forem incompatíveis com o objetivo estabelecido, autorização do usuário.

## Artigo 16 — Emendas

Uma regra entra neste repositório somente quando for realmente universal ou estrutural.

Se uma regra só faz sentido para um projeto, ela pertence ao repositório desse projeto.

Emendas devem evitar nomes, versões, porcentagens ou detalhes temporários de cidadãos específicos, salvo exemplos claramente não normativos.

## Artigo 17 — Princípio final

A lei conhece o comportamento-base que os projetos devem seguir.

Ela não precisa conhecer cada projeto pelo nome, nem impedir que cada cidadão tenha suas próprias leis locais e exceções autorizadas.