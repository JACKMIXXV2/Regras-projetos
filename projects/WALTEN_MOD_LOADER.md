# Walten Mod Loader / Recovery Lab — regras de continuidade

Repositório: `JACKMIXXV2/walten-mod-loader`

Este projeto é uma investigação/recovery contínua. Nunca reiniciar do zero quando o laboratório já contém estado persistido.

## Boot obrigatório

Leia primeiro `AGENTS.md` do repositório Walten. Depois, na ordem atual:

1. `LAB/CURRENT_STATE.md`
2. `LAB/RULES.md`
3. `LAB/RECOVERY_PROGRESS.md`
4. `LAB/AURAFIT_FORENSICS.md`
5. handoff master apontado pelo estado atual
6. `LAB/ARTIFACT_MANIFEST.md`
7. `LAB/MIGRATION_STATUS.md`
8. evidência específica do alvo atual

Se os nomes/versionamentos do handoff mudarem, siga o arquivo apontado pelo `CURRENT_STATE`/`AGENTS.md` mais recente.

## Fonte de verdade

- GitHub/repo = workspace canônico.
- Não refazer experimentos fechados apenas para reconfirmar observação antiga.
- Evidência offline vem antes de teste físico no G6 quando a mesma pergunta pode ser respondida por source, captures, APK/DEX, sandbox root, snapshots ou documentação já existente.

## Evidência antes de hipótese

Nunca inventar:

- `firmwareFlag`;
- firmware/resource;
- URL;
- resposta de API;
- endereço de bootloader;
- estado de protocolo;
- resultado de flash/recovery.

Valor não comprovado permanece `NOT_PROVEN`. Candidato permanece candidato até provenance direta.

## Gates de segurança do recovery

O gate ativo é definido por `LAB/CURRENT_STATE.md` + `LAB/RULES.md` e deve ser obedecido literalmente.

Não destravar reboot forçado, `startOTA`, serving de firmware, flash/write ou operação destrutiva enquanto o gate ativo não tiver evidência nova que o satisfaça.

Não reescrever checkpoint estabelecido apenas para encaixar hipótese nova.

Se um endereço/valor foi classificado apenas como candidato, não tratá-lo como identidade confirmada.

## Trabalho já fechado

Experimentos marcados como fechados pelo estado atual não devem ser repetidos por hábito. Reabertura exige nova evidência, nova variável material ou contradição real.

## Completude absoluta

No Walten, `all`, `everything`, `complete`, `full`, `total`, `absolute`, `1:1`, `entire project`, `entire workspace` e equivalentes são especialmente vinculantes.

Uma migração GitHub completa inclui tudo que pertença ao escopo pedido: source, binários, assets, libs, wrappers, ferramentas, docs, testes, snapshots, configs, manifests, evidências e demais artefatos.

Antes de declarar `COMPLETE`:

- inventariar a origem;
- contar/verificar;
- comparar destino;
- confirmar que nada requerido ficou fora.

Se faltar um item, declarar `INCOMPLETE` e listar o restante.

## Barras G6

Cada nova versão/relatório de Recovery deve preservar o ledger completo de progresso.

- notas em `X/10`;
- `>>>` em toda linha que realmente avançou;
- quando houver avanço, mostrar `anterior -> novo`;
- sem `>>>` em linha estável;
- porcentagem geral só muda por avanço técnico real, não por novo ZIP, nova versão ou novo commit documental.

Exemplo:

```text
>>> Bootloader identity       █████░░░░░ 5/10  (3/10 -> 5/10)
```

## Registro mínimo de evidência

Quando aplicável, preservar:

- nome do artefato;
- hash;
- caminho/chave/tabela/método/offset/linha;
- valor bruto ou decodificado;
- interpretação;
- confiança/status `PROVEN` vs `CANDIDATE`.

Ausência de evidência = `NOT_PROVEN`, não palpite.

## `ataca`

Herdar `GLOBAL_RULES.md`: passagem contínua, profunda e autônoma no estágio atual.

Se uma frente física está bloqueada, esgotar primeiro rotas offline permitidas. Um bloqueio em operação destrutiva não interrompe análise documental, provenance, comparação, parsing, testes não destrutivos ou outras rotas independentes.

## GitHub

- Cada mudança real de regra/estado/evidência deve ser persistida consistentemente.
- Novas versões de source devem atualizar handoff/current state/tests/guards quando aplicável.
- Não declarar migração completa sem verificação 1:1.
- Seguir `GITHUB_PROTOCOL.md`.

## Retomada rápida

Se o usuário fornecer apenas o link do Walten e pedir continuidade:

1. leia `AGENTS.md`;
2. siga a ordem de boot do LAB;
3. identifique stage/gate/checkpoint atuais;
4. continue a investigação daquele ponto;
5. não peça recapitulação já presente no repositório.
