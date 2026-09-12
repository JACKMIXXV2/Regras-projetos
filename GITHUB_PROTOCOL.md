# GITHUB_PROTOCOL.md — protocolo canônico de GitHub

Este arquivo define como os projetos devem ler, alterar, validar e persistir estado no GitHub.

## 1. Antes de escrever

Sempre que possível:

1. confirmar o repositório correto;
2. confirmar a branch correta;
3. ler HEAD/estado atual;
4. buscar o arquivo atual e seu SHA quando a operação for update/delete;
5. verificar checkpoint/estado canônico do projeto;
6. só então escrever.

Nunca sobrescrever um arquivo com base em cópia antiga do chat se o GitHub possui versão mais nova.

## 2. Branch não é detalhe

Cada projeto pode ter regras próprias de branch. Obedecer o perfil correspondente.

Regras gerais:

- não fazer merge cego entre branches com papéis diferentes;
- não assumir que `main` contém laboratório/provenance se o projeto documenta outra branch;
- não mover ref à força para “resolver” divergência sem entender o que seria perdido;
- se HEAD mudou durante o trabalho, reler e reconciliar antes de atualizar o mesmo caminho.

## 3. Commits

Um commit deve representar mudança material coerente.

Preferir mensagens que revelem a intenção:

```text
fix: corrigir bootstrap do worker local
feat: adicionar validação do portal 5x5
recovery: registrar nova evidência do bootloader
chore: atualizar manifesto de artefatos
rules: consolidar protocolo de continuidade
```

Não usar commit vazio apenas para simular progresso.

## 4. Ataque relevante termina persistido

Se um ataque altera código, regras, estado, evidência, ferramenta, teste ou artefato reproduzível, a mudança deve chegar ao repositório oficial.

Um resultado que só existe no chat, `/tmp`, workspace efêmero ou memória do agente não conta como fechado.

## 5. CI/build

Quando a mudança toca código compilável ou contrato testável:

- executar CI/build/teste aplicável quando disponível;
- distinguir `código escrito` de `build passou`;
- distinguir `build passou` de `runtime real comprovado`;
- distinguir `runtime real` de `aprovação humana/perceptual`, quando houver;
- registrar run/artifact/hash quando o projeto usa isso como evidência.

Se CI falhar por erro corrigível do projeto, corrigir e retestar dentro do mesmo ataque sempre que possível.

## 6. Artefatos

- Não tratar artifact expirado de CI como perda de código-fonte.
- Se o projeto permite reconstrução reproduzível, recompile pelo workflow/build oficial.
- Binário/JAR/APK/EXE/WAV/modelo só conta como evidência quando realmente foi produzido/obtido.
- Não inventar hash ou afirmar conteúdo de binário não inspecionado.

## 7. Bug -> correção -> nova build

Quando o usuário reportar bug em artefato testável:

```text
bug reportado
-> evidência associada à versão testada
-> diagnóstico
-> correção
-> teste/contrato quando possível
-> commit
-> CI/build
-> novo artefato identificável
-> novo teste do usuário
```

Não reutilizar silenciosamente o mesmo número/artefato se a política do projeto exige nova versão.

## 8. Conflitos e concorrência

Se outra mudança chegar primeiro:

- não force overwrite;
- recarregue o arquivo/HEAD;
- preserve mudanças independentes;
- reconcilie semanticamente;
- só então faça novo commit.

Em atualização sequencial do mesmo arquivo, usar o SHA retornado pela leitura/update mais recente.

## 9. Operações destrutivas

Delete, force-update, reset, merge destrutivo ou substituição ampla exigem certeza sobre escopo e provenance.

Antes de apagar:

- confirmar que o arquivo realmente foi substituído ou ficou obsoleto;
- verificar se histórico/compatibilidade exige preservação;
- evitar remover baseline validado por conveniência.

## 10. Migração e espelho 1:1

Quando o pedido for `migração completa`, `espelho 1:1`, `workspace inteiro` ou equivalente:

- inventariar origem inteira;
- incluir código, docs, assets, scripts, ferramentas, wrappers, manifests, evidências e demais classes pedidas;
- comparar contagem/caminhos;
- verificar o que ficou de fora;
- nunca declarar `COMPLETE` se houver item requerido ausente.

## 11. Regras e estado

Mudança de regra estável:

1. atualizar a fonte canônica do projeto, quando existir;
2. atualizar `Regras-projetos` quando a regra também for central;
3. manter o estado volátil no repo do projeto.

Mudança de versão/porcentagem/fila/checkpoint normalmente **não** exige copiar o número para este repo central.

## 12. Fonte de verdade em caso de frontend bugado

Ordem de confiança:

```text
GitHub HEAD / objetos persistidos
> estado/checkpoint/evidência do repo
> resultados de CI/build
> histórico de conversa
> spinner / frontend
```

Se a interface parecer parada mas o commit existe, o commit existe. A humanidade sobreviveu a indicadores de carregamento piores.
