# GITHUB_PROTOCOL.md — protocolo universal de GitHub

Este arquivo define como qualquer projeto governado por `Regras-projetos` deve ler, alterar, validar e persistir estado no GitHub.

Ele é universal. Branches, workflows, nomes de arquivos e políticas de release podem variar por projeto, mas o comportamento operacional abaixo continua válido.

## 1. Antes de escrever

Sempre que possível:

1. confirmar o repositório correto;
2. confirmar a branch correta;
3. ler HEAD e estado atual;
4. buscar o arquivo atual e seu SHA quando a operação for update/delete;
5. verificar regras locais, checkpoint e estado canônico do projeto;
6. só então escrever.

Nunca sobrescrever um arquivo com base em cópia antiga do chat se o GitHub possui versão mais nova.

## 2. Branch não é detalhe

Cada projeto pode definir papéis próprios para suas branches.

Regras universais:

- não fazer merge cego entre branches com papéis diferentes;
- não assumir que `main` contém laboratório, provenance ou estado experimental;
- não mover ref à força para “resolver” divergência sem entender o que seria perdido;
- se HEAD mudou durante o trabalho, reler e reconciliar antes de atualizar o mesmo caminho;
- regras locais de branch são válidas desde que não contradigam este protocolo.

## 3. Commits

Um commit deve representar mudança material coerente.

Preferir mensagens que revelem a intenção, por exemplo:

```text
fix: corrigir falha de inicialização
feat: adicionar validação do novo fluxo
recovery: registrar nova evidência
chore: atualizar manifesto de artefatos
rules: atualizar governança universal
```

Não usar commit vazio apenas para simular progresso.

## 4. Ataque relevante termina persistido

Se um ataque altera código, regra local, estado, evidência, ferramenta, teste ou artefato reproduzível, a mudança deve chegar ao repositório oficial correspondente.

Um resultado que só existe no chat, `/tmp`, workspace efêmero ou memória do agente não conta como fechado.

## 5. CI, build e runtime

Quando a mudança toca código compilável ou contrato testável:

- executar CI, build ou teste aplicável quando disponível;
- distinguir `código escrito` de `build passou`;
- distinguir `build passou` de `runtime real comprovado`;
- distinguir `runtime real` de `aprovação humana/perceptual`, quando houver;
- registrar run, artifact e hash quando o projeto usa isso como evidência.

Se CI falhar por erro corrigível do projeto, corrigir e retestar dentro do mesmo ataque sempre que possível.

## 6. Artefatos

- Não tratar artifact expirado de CI como perda do código-fonte.
- Se o projeto permite reconstrução reproduzível, recompile pelo workflow ou build oficial.
- Binário, JAR, APK, EXE, WAV, modelo ou outro artefato só conta como evidência quando realmente foi produzido ou obtido.
- Não inventar hash nem afirmar conteúdo de binário não inspecionado.

## 7. Bug -> correção -> nova validação

Quando o usuário reportar bug em artefato testável:

```text
bug reportado
-> evidência associada à versão testada
-> diagnóstico
-> correção
-> teste/contrato quando possível
-> commit
-> CI/build quando aplicável
-> novo artefato identificável quando necessário
-> novo teste
```

Não reutilizar silenciosamente o mesmo número ou artefato se a política local exige nova versão.

## 8. Conflitos e concorrência

Se outra mudança chegar primeiro:

- não force overwrite;
- recarregue o arquivo e HEAD;
- preserve mudanças independentes;
- reconcilie semanticamente;
- só então faça novo commit.

Em atualização sequencial do mesmo arquivo, usar o SHA retornado pela leitura ou update mais recente.

## 9. Operações destrutivas

Delete, force-update, reset, merge destrutivo ou substituição ampla exigem certeza sobre escopo e provenance.

Antes de apagar:

- confirmar que o arquivo realmente foi substituído ou ficou obsoleto;
- verificar se histórico ou compatibilidade exige preservação;
- evitar remover baseline validado por conveniência.

## 10. Migração e espelho 1:1

Quando o pedido for `migração completa`, `espelho 1:1`, `workspace inteiro` ou equivalente:

- inventariar origem inteira;
- incluir código, docs, assets, scripts, ferramentas, wrappers, manifests, evidências e demais classes pedidas;
- comparar contagem e caminhos;
- verificar o que ficou de fora;
- nunca declarar `COMPLETE` se houver item requerido ausente.

## 11. Relação com a lei universal

Mudanças específicas de um projeto pertencem ao próprio projeto.

Mudanças universais de governança pertencem a `Regras-projetos`.

Um projeto pode ter regras Git próprias de branch, release, versionamento ou CI, mas elas funcionam como especializações deste protocolo, nunca como revogação.

Estado volátil como versão, porcentagem, fila, checkpoint, build e próximo alvo permanece no projeto.

## 12. Fonte de verdade quando a interface falha

Ordem de confiança:

```text
GitHub HEAD / objetos persistidos
> estado/checkpoint/evidência do repo
> resultados de CI/build/runtime
> histórico de conversa
> spinner / frontend
```

Se a interface parecer parada mas o commit existe, o commit existe. Pixels ansiosos não anulam SHA.
