# GOVERNANCE_SYNC.md — sincronização obrigatória da lei

Este arquivo define como projetos governados por `Regras-projetos` detectam, revisam e incorporam mudanças da lei universal depois que este repositório é atualizado.

A regra existe para impedir que um projeto continue trabalhando com uma versão antiga da governança sem perceber.

## 1. Princípio

Todo projeto governado por `Regras-projetos` deve verificar se a lei universal mudou desde a última revisão conhecida antes de iniciar trabalho substancial em uma nova retomada, sessão, ataque ou passagem operacional.

A lei central não precisa manter uma lista de projetos nem fazer push ativo para cada repositório.

Cada projeto é responsável por conferir a fonte canônica na próxima vez em que for tocado.

## 2. Marcador local de sincronização

Sempre que possível, o projeto deve registrar localmente o último commit de `JACKMIXXV2/Regras-projetos` que foi efetivamente revisado e incorporado.

O marcador pode ficar em `PROJECT_GOVERNANCE.md` ou em outro arquivo local de governança claramente identificado.

Formato recomendado:

```text
GOVERNANCE_LAST_CHECKED: <commit-sha-de-Regras-projetos>
```

Esse SHA não significa que o projeto copiou toda a lei. Significa apenas que o projeto revisou a lei até aquele commit e tratou as mudanças aplicáveis.

## 3. Verificação na retomada

Antes de trabalho substancial no projeto:

1. ler o marcador local de governança, quando existir;
2. consultar o HEAD atual de `JACKMIXXV2/Regras-projetos`;
3. comparar o commit registrado com o HEAD central;
4. se forem iguais, considerar a governança sincronizada e seguir normalmente;
5. se forem diferentes, revisar as mudanças entre os dois pontos antes de continuar trabalho material dependente da governança.

Se o projeto não possuir marcador local, tratá-lo como `UNSYNCED` e realizar uma revisão inicial da lei atual antes de criar o primeiro marcador.

## 4. Revisão por diff, não releitura burra

Quando houver um commit anterior conhecido, preferir comparar os commits e ler os arquivos de governança que realmente mudaram.

Não reler toda a Constituição e todos os protocolos do zero a cada retomada se o diff mostra que nada relevante mudou.

Se a mudança estrutural alterar dependências entre arquivos, ler também os arquivos afetados indiretamente.

## 5. Classificação de impacto

Cada mudança central relevante deve ser tratada como uma destas classes:

- `APPLICABLE`: aplica-se diretamente ao projeto e deve ser incorporada;
- `NO_LOCAL_CHANGE`: a lei mudou, mas o projeto já cumpre a regra ou nenhuma alteração local é necessária;
- `LOCAL_SPECIALIZATION`: a lei exige interpretação específica já coberta por regra local válida;
- `AUTHORIZED_EXCEPTION`: existe exceção local explicitamente autorizada pelo usuário;
- `CONFLICT_TO_RECONCILE`: há conflito real ainda não resolvido entre lei central e regra local.

Não marcar o novo commit como revisado antes de classificar e tratar as mudanças relevantes.

## 6. Aplicação local

Se a atualização central exigir mudança no projeto:

- atualizar bootstrap, ponte, regras locais, fluxo, documentação ou estado de governança necessário;
- preservar baseline e continuidade válidos;
- não reescrever organização local sem necessidade;
- seguir `ADAPTATION_PROTOCOL.md` quando a mudança exigir convergência entre lei central e sistema local;
- registrar exceções autorizadas quando existirem.

Uma atualização da lei não autoriza apagar regras locais úteis, estado, evidências, ferramentas ou decisões técnicas válidas.

## 7. Atualização do marcador

O marcador local só deve avançar para o novo commit central depois que:

1. o diff central foi revisado;
2. o impacto foi classificado;
3. mudanças locais necessárias foram aplicadas ou conflitos foram explicitamente registrados;
4. a revisão foi persistida no projeto.

Depois disso, atualizar:

```text
GOVERNANCE_LAST_CHECKED: <novo-commit-central>
```

## 8. Mudanças centrais durante um ataque

Se `Regras-projetos` mudar enquanto um ataque longo já está em andamento:

- não descartar trabalho válido já realizado;
- criar checkpoint quando necessário;
- verificar o novo diff central antes da próxima decisão material que possa ser afetada pela mudança;
- incorporar a nova lei sem reiniciar o projeto do zero;
- continuar o ataque depois da reconciliação.

Mudança de governança não é desculpa para perder progresso.

## 9. Atualização global imediata

Por padrão, projetos verificam a lei quando forem retomados.

Se o usuário ordenar uma propagação imediata global, então todos os projetos acessíveis dentro do escopo indicado devem ser verificados e sincronizados na mesma operação, respeitando suas regras locais e exceções autorizadas.

Isso não cria uma lista central permanente de projetos.

## 10. Falha de acesso

Se o agente não conseguir acessar `Regras-projetos` ou o histórico necessário para comparar commits:

- não fingir que a governança está atualizada;
- marcar o estado como `GOVERNANCE_SYNC_UNKNOWN` ou equivalente local;
- continuar apenas trabalho que não dependa da mudança desconhecida, quando seguro e permitido;
- realizar a sincronização assim que a fonte canônica estiver acessível.

## 11. Regra de eficiência

Sincronização deve impedir desatualização sem virar burocracia inútil.

O fluxo normal é:

```text
ler marcador local
-> ler HEAD central
-> iguais? continua
-> diferentes? compara diff
-> aplica/reconcilia o que mudou
-> persiste
-> atualiza marcador
-> continua o trabalho
```

## 12. Princípio final

Projeto governado por lei mutável não pode assumir que a lei continua igual por memória.

Se a lei mudou, o projeto verifica.

Se a mudança se aplica, o projeto adapta.

Se não se aplica, registra a revisão e segue.

Nenhum cidadão continua obedecendo uma Constituição velha só porque ninguém teve a curiosidade de olhar o SHA.