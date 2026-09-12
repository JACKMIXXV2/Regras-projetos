# GITHUB_PROTOCOL.md — protocolo universal de GitHub

Este arquivo define como qualquer projeto governado por `Regras-projetos` deve ler, alterar, validar e persistir estado no GitHub.

Ele é universal. Branches, workflows, nomes de arquivos e políticas de release podem variar por projeto. Exceções locais ao protocolo também podem existir quando autorizadas explicitamente pelo usuário e registradas no projeto.

## 1. Antes de escrever

Sempre que possível:

1. confirmar o repositório correto;
2. confirmar a branch correta;
3. ler HEAD e estado atual;
4. buscar o arquivo atual e seu SHA quando a operação for update/delete;
5. verificar regras locais, exceções autorizadas, checkpoint e estado canônico do projeto;
6. só então escrever.

Nunca sobrescrever um arquivo com base em cópia antiga do chat se o GitHub possui versão mais nova.

## 2. Branch não é detalhe

Cada projeto pode definir papéis próprios para suas branches.

Regras universais:

- não fazer merge cego entre branches com papéis diferentes;
- não assumir que `main` contém laboratório, provenance ou estado experimental;
- não mover ref à força para resolver divergência sem entender o que seria perdido;
- se HEAD mudou durante o trabalho, reler e reconciliar antes de atualizar o mesmo caminho;
- obedecer regras locais de branch e exceções explicitamente autorizadas.

## 3. Commits

Um commit deve representar mudança material coerente.

Não usar commit vazio apenas para simular progresso.

## 4. Ataque relevante termina persistido

Se um ataque altera código, regra local, estado, evidência, ferramenta, teste ou artefato reproduzível, a mudança deve chegar ao repositório oficial correspondente.

Um resultado que só existe no chat, `/tmp`, workspace efêmero ou memória do agente não conta como fechado.

## 5. Checkpoints preventivos

Ataques longos devem proteger progresso antes do final quando houver risco real de perda.

Criar checkpoint ou commit seguro quando aplicável:

- após avanço material significativo;
- antes de operação destrutiva;
- antes de grande refatoração;
- antes de alteração estrutural de estado;
- quando reconstruir o trabalho em caso de falha seria caro.

Checkpoint não significa encerramento do ataque.

## 6. CI, build e runtime

Quando a mudança toca código compilável ou contrato testável:

- executar CI, build ou teste aplicável quando disponível;
- distinguir `código escrito` de `build passou`;
- distinguir `build passou` de `runtime real comprovado`;
- distinguir `runtime real` de `aprovação humana/perceptual`, quando houver;
- registrar run, artifact e hash quando o projeto usa isso como evidência.

Se CI falhar por erro corrigível do projeto, corrigir e retestar dentro do mesmo ataque sempre que possível.

## 7. Artefatos

- Não tratar artifact expirado de CI como perda do código-fonte.
- Se o projeto permite reconstrução reproduzível, recompile pelo workflow ou build oficial.
- Binário, JAR, APK, EXE, WAV, modelo ou outro artefato só conta como evidência quando realmente foi produzido ou obtido.
- Não inventar hash nem afirmar conteúdo de binário não inspecionado.

## 8. Bug -> correção -> nova validação

Quando o usuário reportar bug em artefato testável:

```text
bug reportado
-> evidência associada à versão testada
-> diagnóstico
-> correção
-> teste/contrato quando possível
-> commit/checkpoint
-> CI/build quando aplicável
-> novo artefato identificável quando necessário
-> novo teste
```

Não reutilizar silenciosamente o mesmo número ou artefato se a política local exige nova versão.

## 9. Regressão e rollback

Se uma alteração quebrar estado ou comportamento previamente validado:

1. preservar evidência da regressão;
2. identificar o último commit/checkpoint conhecido como bom;
3. avaliar correção direta versus rollback;
4. evitar empilhar mudanças não relacionadas sobre o estado quebrado;
5. restaurar ou corrigir;
6. executar novamente a validação aplicável;
7. registrar a causa e o resultado.

## 10. Conflitos e concorrência

Se outra mudança chegar primeiro:

- não force overwrite;
- recarregue o arquivo e HEAD;
- preserve mudanças independentes;
- reconcilie semanticamente;
- só então faça novo commit.

Em atualização sequencial do mesmo arquivo, usar o SHA retornado pela leitura ou update mais recente.

## 11. Operações destrutivas

Delete, force-update, reset, merge destrutivo ou substituição ampla exigem certeza sobre escopo e provenance.

Antes de apagar:

- confirmar que o arquivo realmente foi substituído ou ficou obsoleto;
- verificar se histórico ou compatibilidade exige preservação;
- evitar remover baseline validado por conveniência;
- criar checkpoint preventivo quando a operação puder afetar estado difícil de reconstruir.

## 12. Migração e espelho 1:1

Quando o pedido for `migração completa`, `espelho 1:1`, `workspace inteiro` ou equivalente:

- inventariar origem inteira;
- incluir código, docs, assets, scripts, ferramentas, wrappers, manifests, evidências e demais classes pedidas;
- comparar contagem e caminhos;
- verificar o que ficou de fora;
- nunca declarar `COMPLETE` se houver item requerido ausente.

Quando a tarefa for adaptação para a governança universal, obedecer também `ADAPTATION_PROTOCOL.md`.

Nesse caso, não substituir cegamente a organização local pela central. Reconciliar as duas e preservar o que cada uma tem de melhor.

## 13. Regras locais e exceções de Git

Um projeto pode ter regras próprias de branch, release, versionamento, CI, commit, artifact ou fluxo de validação.

Por padrão, elas especializam este protocolo.

Se o usuário autorizar explicitamente uma exceção que contradiga uma regra universal deste arquivo, a exceção pode prevalecer naquele projeto e naquele escopo.

Exceções duradouras devem ser registradas localmente.

## 14. Definition of Done no GitHub

A presença de commit não prova, sozinha, conclusão.

Quando a tarefa exige validação, um estado só deve ser tratado como concluído depois de cumprir a Definition of Done de `GLOBAL_RULES.md`.

## 15. Fonte de verdade quando a interface falha

Ordem de confiança padrão:

```text
GitHub HEAD / objetos persistidos
> estado/checkpoint/evidência do repo
> resultados de CI/build/runtime
> histórico de conversa
> spinner / frontend
```

Uma regra local ou exceção autorizada pode refinar fontes adicionais, mas a interface visual isolada não deve fazer o projeto voltar para trás.

Se a interface parecer parada mas o commit existe, o commit existe. Pixels ansiosos não anulam SHA.