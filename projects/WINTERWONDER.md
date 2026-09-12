# WinterWonder — regras de continuidade e desenvolvimento

Repositório: `JACKMIXXV2/WinterWonder`

WinterWonder é um mod Minecraft 1.21.1 com implementações independentes para Fabric, Forge e NeoForge.

## Boot obrigatório

Leia nesta ordem:

1. `README.md`
2. `VERSIONING.md`
3. `CHANGELOG.md`
4. `docs/PORT_STATUS.md`
5. `docs/PORT_PARITY.md`
6. `docs/FABRIC_INVENTORY.md`
7. documentação específica do alvo atual em `docs/`
8. histórico relevante em `version-history/` quando a tarefa exigir comparação/regressão

Depois confira a árvore do loader que será alterada e compile/teste somente esse loader, salvo tarefa explícita de paridade multi-loader.

## Loaders são independentes

- `fabric/`, `forge/` e `neoforge/` são árvores independentes.
- Não misturar loaders na mesma instalação ou no mesmo JAR.
- Cada loader possui bootstrap, dependências, wrapper e instância de teste próprios.
- Forge e NeoForge mantêm cópias locais de código comum de propósito. A duplicação é intencional para preservar builds independentes.
- Não “otimizar” essa duplicação criando dependência cruzada silenciosa entre árvores.

## Portabilidade

`docs/PORT_PARITY.md` é o inventário de paridade. Port não significa copiar cegamente mixins/payloads de outro loader.

Quando um hook não existe no loader alvo:

- adaptar para evento/API nativa equivalente;
- documentar `ADAPTADO`, `REESCRITO`, `LIMITADO` ou outro estado real;
- manter fallback seguro quando a API/mapping exige isso;
- não declarar paridade se a função ainda não possui equivalente funcional.

A verificação final de paridade deve usar ferramentas/scripts existentes do projeto quando aplicável, incluindo validação do conteúdo dos JARs.

## Build

Requisito principal: JDK 21.

Cada loader usa seu próprio Gradle Wrapper. Build comum deve ser executado na árvore correspondente.

Build comum **não deve alterar versão**.

## Versionamento

A política oficial usa `MAJOR.MINOR.PATCH`.

- `content`: recurso novo disponível ao jogador -> aumenta `MINOR`, zera `PATCH`;
- `patch`: correção, desempenho, balanceamento, tradução ou refatoração -> aumenta `PATCH`;
- `major`: mudança incompatível ou grande fase -> aumenta `MAJOR` e zera os demais;
- conteúdo + correções na mesma atualização = `content`.

Para releases Fabric, usar a tarefa `release`; não editar o número manualmente como rotina.

Build comum sem `-PreleaseType` nunca muda a versão.

## Instalação externa

Release não deve alterar instalação externa por padrão.

Instalação em instância CurseForge só acontece quando pedida explicitamente pelo parâmetro do projeto. Fechar Minecraft antes de substituir versão instalada.

Não transformar uma simples compilação em mutação silenciosa da instalação do usuário.

## Histórico

- `CHANGELOG.md` é o changelog consolidado.
- `version-history/` preserva versões históricas curadas conforme a política do projeto.
- backups locais não precisam virar commit apenas por existirem.
- não apagar histórico útil para “limpar” o repo sem motivo claro.

## Conteúdo incompleto

Hooks, bosses, dimensões dinâmicas ou outros sistemas que o README/estado marcam como base técnica não devem ser anunciados como finalizados.

Implementação parcial, scaffold ou contrato preparado não equivale a feature concluída.

## Registries e conteúdo

Quando alterar itens/blocos/entidades/comandos:

- preservar a fonte única/registries reais usados pelo projeto;
- evitar listas paralelas divergentes;
- manter conteúdo técnico de desenvolvimento fora de superfícies jogáveis quando essa for a regra atual;
- validar IDs e paridade no JAR final quando aplicável.

## Atmosfera e referências externas

Mods/projetos externos usados como referência de estudo não devem virar dependência obrigatória silenciosa se o WinterWonder mantém implementação própria.

Referência visual/técnica não significa dependência de runtime.

## Baseline e regressão

Comportamento validado de portal, dimensão, inventário, clima, UI, multiplayer e demais sistemas deve ser preservado durante refatorações.

Não quebrar uma árvore funcional para “igualar” outra sem primeiro entender a diferença de API/loader.

## `ataca`

WinterWonder herda integralmente `GLOBAL_RULES.md`.

Se o alvo for uma feature/bug específico, `ataca` significa trabalhar continuamente nessa frente através de implementação, correção, build, testes e commit até conclusão verificável ou bloqueio real.

Se a tarefa tocar mais de um loader, validar cada árvore afetada separadamente e não declarar sucesso global com base em um único loader.

## GitHub

- persistir mudança material em commit;
- não sobrescrever HEAD mais novo;
- usar mensagens coerentes com feature/fix/port/release;
- validar build antes de chamar mudança compilável de pronta;
- seguir `GITHUB_PROTOCOL.md`.

## Retomada rápida

Se o usuário fornecer apenas o link do WinterWonder e pedir continuidade:

1. leia README/versioning/status/parity;
2. identifique loader e alvo atual;
3. confira histórico relevante;
4. trabalhe no loader correto;
5. valide a árvore afetada;
6. persista no GitHub;
7. não peça explicações que já estejam documentadas.

Este projeto **não é exclusivo do Codex**: se o conector GitHub possui acesso ao repositório, leitura e escrita podem ser feitas diretamente por ele quando a tarefa permitir.
