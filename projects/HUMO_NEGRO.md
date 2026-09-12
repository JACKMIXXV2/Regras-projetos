# Humo Negro / Radio Rebelión VoiceLab — regras de continuidade

Repositório: `JACKMIXXV2/radio-rebelion`

Produto: **Humo Negro Voice Lab**. Projeto técnico: **Radio Rebelión VoiceLab**.

## Boot obrigatório

Leia nesta ordem:

1. `START_HERE_CHATGPT.md`
2. `CONTINUITY_RULES.md`
3. `VERSION.json`
4. `PLATFORM_PROGRESS.json`
5. `PLATFORM_STAGES.json`
6. evidência de build/runtime apontada pela versão atual
7. `PROGRESS.json`
8. `CANONICAL_REMAINDER.json`
9. `RUNTIME_PROOF_V24.json` ou gate canônico que o projeto vier a substituir oficialmente
10. documentação histórica/legacy apontada pelo handoff atual

Depois disso, continuar do estágio ativo. Não pedir ao usuário para explicar de novo o que já está documentado.

## Identidades vocais

As identidades oficiais são separadas. Jhonny, Sirius e Ara não podem receber fallback cruzado silencioso.

- falta de referência dedicada = erro explícito;
- pitch shift não substitui identidade;
- AM/DSP não pode ser usado para esconder voz seca ruim;
- take que falhou gate não é promovido;
- áudio inexistente não pode ser tratado como evidência.

## `ataca`

`ataca` herda a regra global de ataque contínuo e leva o **estágio atual até 100% verificável** antes de migrar para o seguinte, salvo bloqueio externo real.

Ciclo esperado quando aplicável:

1. ler estado/evidência atuais;
2. identificar gap real;
3. implementar avanço;
4. validar;
5. corrigir e retestar se falhar;
6. persistir no repo;
7. rodar CI/build quando aplicável;
8. produzir artefato real quando o gate exigir;
9. registrar evidência;
10. fechar estágio apenas quando o gate objetivo estiver satisfeito.

Código escrito não equivale automaticamente a build válida; build válida não equivale automaticamente a runtime real; runtime real não equivale automaticamente a aprovação perceptual.

## Barra canônica de voz

A régua canônica e seu denominador pertencem aos arquivos persistidos do projeto. Não inventar categorias novas dentro do denominador histórico para facilitar 100%.

- `>>>` somente com avanço comprovado;
- porcentagem só sobe com evidência exigida pela categoria;
- categorias perceptuais exigem validação perceptual quando o gate assim define;
- documentação/readiness não ganha ponto de qualidade vocal sozinha;
- barra de plataforma e barra canônica de voz são sistemas separados.

## Baseline

Preservar baseline aprovado, hashes, referências, contratos e decisões canônicas.

Não abrir nova versão apenas para esconder estágio incompleto. Nova versão deve corresponder a mudança material identificável conforme as regras do projeto.

## Fluxo de bug

Quando o usuário reportar bug de EXE/APK/build:

```text
bug/log/print
-> diagnóstico
-> correção no produto
-> teste/contrato quando possível
-> nova versão/build identificável
-> commit
-> CI/build
-> novo artefato
-> usuário testa a nova build
```

Correção discutida no chat mas não persistida não está concluída.

## Plataforma

A família inclui Worker, Studio Windows e Mobile Android.

- progresso de plataforma não altera automaticamente a barra canônica de voz;
- artefato real é necessário para gates de build;
- runtime real é necessário para gates E2E;
- endpoints expostos fora de localhost exigem autenticação;
- segredo/token de execução não deve ser commitado;
- IP LAN não deve ser hardcodado como verdade permanente.

## Mobile

Enquanto o contrato atual do projeto permanecer vigente, **Humo Negro Mobile deve ser capaz de executar a função principal localmente sem depender do PC ligado**.

LAN/Worker pode existir como modo adicional de offload, sincronização ou controle remoto, mas não substitui o gate local do Mobile Lite.

Não promover Android local/E2E com base apenas em build, mocks ou geração feita no PC.

## Transição entre estágios

- não abandonar estágio em 85/90/99%;
- se o próximo estágio depende de hardware/GPU/navegador/ambiente externo, fechar primeiro todo pré-gate executável;
- não usar runtime posterior para maquiar estágio anterior incompleto;
- a ordem de estágios atual é lida de `PLATFORM_STAGES.json` e do handoff, não deste arquivo.

## GitHub e artefatos

Cada ataque relevante termina em commit quando houve mudança material.

Artifacts de Actions podem expirar. Se o projeto é reproduzível, artifact expirado deve ser recompilado pelo workflow em vez de ser tratado como perda do projeto.

Scripts, manifests, hashes, contratos e fontes necessárias à reprodução devem permanecer persistidos conforme a política do repo.

## Relatório

Relatório substancial deve separar:

- código escrito;
- build validada;
- runtime comprovado;
- aprovação perceptual;
- avanço de barras com `>>>`;
- commit/build/artifact;
- bloqueio externo restante.

Muita atividade sem áudio/evidência não é promoção de qualidade.
