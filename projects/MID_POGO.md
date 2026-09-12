# Mid Pogo — regras de continuidade

Repositório: `JACKMIXXV2/mid-pogo`

Este perfil centraliza as invariantes. O estado atual continua pertencendo ao próprio repositório Mid Pogo.

## Branches e autoridade

- `main` = source + resultados consolidados.
- `lab` = laboratório reproduzível + recuperação + provenance.
- Nunca fazer merge cego `lab -> main`.
- GitHub é fonte persistente de verdade; frontend/chat não podem fazer o projeto regredir.

## Boot obrigatório

Primeiro leia `PROJECT_BOOTSTRAP.md` em `main`.

Depois, na branch `lab`, leia nesta ordem:

1. `workspace/PROJECT_INVARIANTS.md`
2. `workspace/CURRENT_STATE.md`
3. `workspace/LAST_GOOD_CHECKPOINT.md`
4. `workspace/RECOVERY_LEDGER.json`
5. `workspace/ATTACK_QUEUE.md`
6. `workspace/GLOBAL_100_GATE.md`
7. `workspace/NEXT.md`
8. provenance/documentação específica do alvo atual

Só depois confira o trabalho a executar.

Não carregar automaticamente toda a história antiga se o estado atual já resolve a retomada.

## Semântica de `ataca`

Herdar `GLOBAL_RULES.md` integralmente.

No Mid Pogo, `ataca` significa passagem longa, autônoma e profunda na recuperação atual. Não parar em `+0`, commit, checkpoint, hipótese falsa ou rota esgotada quando ainda existe outra frente útil.

## Anti-stall

- Uma etapa opaca não pode dominar a passagem indefinidamente.
- Após tentativas realmente equivalentes e cegas, marcar `STALLED` e pivotar.
- Evidência nova permite novo aprofundamento.
- HEAD/checkpoint vence spinner antigo.

## Não inflação

- Não inventar identidade histórica.
- Não ajustar contagem para alcançar meta.
- Não promover hipótese a artefato.
- Não substituir objeto físico histórico por equivalente genérico de terceiro apenas porque o nome parece combinar.
- `>>>` só em avanço material real.
- documentação/provenance sozinha não altera score material.
- objeto fechado só reabre com evidência histórica nova ou contradição material.

## Barras

Relatórios substanciais devem manter as barras exigidas pelo estado atual do projeto e o `GLOBAL FINAL`.

Toda linha que avança usa `>>>` e mostra `anterior -> novo`. Linha que não mudou não recebe `>>>`.

## Gate absoluto de recuperação

O gate definido pelo laboratório prevalece sobre vontade de “já começar a próxima versão”.

Enquanto o `GLOBAL FINAL` estiver abaixo de 100%, a recuperação continua. Ao alcançar 100%, executar a auditoria de fechamento do denominador. Somente com 100% e auditoria fechada o laboratório 1:1 é considerado completo.

A abertura de uma nova fase/versionamento bloqueado pelo gate só ocorre em conversa dedicada e com autorização explícita quando as regras do próprio projeto exigirem isso.

## Hierarquia interna

```text
1. GitHub HEAD / objetos materializados
2. workspace/CURRENT_STATE.md
3. workspace/LAST_GOOD_CHECKPOINT.md
4. workspace/RECOVERY_LEDGER.json
5. workspace/ATTACK_QUEUE.md
6. workspace/NEXT.md / provenance específico
7. histórico de conversa
8. frontend / spinner
```

## Baseline e camada de compatibilidade

Comportamento previamente validado faz parte do baseline e não deve ser removido, reescrito ou degradado silenciosamente.

Se existir camada de compatibilidade já funcional, preservar o comportamento conhecido enquanto se trabalha em aspectos permitidos como estabilidade, integração, observabilidade, tratamento de erro e compatibilidade. Não criar nem aprimorar mecanismos destinados a contornar controles externos de terceiros, como pagamento, licença, autenticação, integridade ou anti-cheat.

Uma limitação específica nessa área não autoriza apagar componentes existentes nem abandonar o restante do projeto; isole a operação limitada e continue as rotas independentes.

## Completude

Pedidos de `1:1`, `workspace completo`, `tudo`, `inteiro` ou equivalentes seguem a regra literal global: inventário integral, comparação origem/destino e `INCOMPLETE` se faltar qualquer item solicitado.

## GitHub

- Toda mudança material deve chegar à branch/repositório correto.
- Não confiar no chat como armazenamento.
- Antes de editar, reler HEAD e o SHA atual.
- Não fechar ataque de código sem persistência reproduzível.
- Seguir `GITHUB_PROTOCOL.md`.

## Regra de retomada rápida

Se o usuário fornecer apenas o link do Mid Pogo e disser para continuar:

1. abrir `PROJECT_BOOTSTRAP.md`;
2. seguir o boot da `lab`;
3. identificar o alvo atual no estado persistido;
4. continuar desse ponto;
5. não pedir uma recapitulação que o repositório já contém.
