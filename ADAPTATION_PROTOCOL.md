# ADAPTATION_PROTOCOL.md — Adaptação e Convergência de Governança

Este protocolo define como qualquer projeto ativo se adapta à governança universal de `Regras-projetos` sem perder identidade técnica, continuidade, histórico ou boas práticas locais.

Ele existe especialmente para projetos que já possuíam regras, handoffs, checkpoints, branches, workflows e sistemas próprios antes de a governança universal ser criada.

Nenhum desses projetos é tratado como ultrapassado, abandonado ou inferior. Todos continuam sendo projetos ativos.

## 1. Princípio de convergência

A adaptação não funciona pela regra “o mais novo manda” nem pela regra “o mais antigo manda”.

O objetivo é produzir a melhor organização resultante da combinação entre:

- lei universal;
- regras locais já comprovadas;
- sistemas de continuidade existentes;
- evidências acumuladas;
- necessidades técnicas específicas;
- exceções autorizadas pelo usuário;
- práticas que possam ser generalizadas para outros projetos.

Em resumo:

```text
lei universal
+
boas práticas locais
+
história operacional válida
+
adaptação consciente
=
governança convergente
```

## 2. Nenhuma precedência por idade

A idade de uma regra, arquivo, projeto ou sistema não decide sua autoridade por si só.

Não vale:

```text
novo > antigo só por ser novo
```

nem:

```text
antigo > novo só por já existir há mais tempo
```

O critério é função, evidência, utilidade, abrangência e autorização do usuário.

## 3. Projetos com sistemas próprios devem se adaptar

A existência de um sistema anterior não isenta o projeto da nova governança.

O objetivo é adaptar o projeto à organização universal, porém sem destruir mecanismos locais que já funcionam.

Isso significa:

- incorporar os princípios universais aplicáveis;
- preservar regras locais úteis;
- reconciliar duplicações;
- eliminar contradições desnecessárias;
- registrar exceções reais;
- melhorar entrypoints e continuidade;
- manter estado técnico e histórico no próprio projeto.

A adaptação deve produzir integração real, não apenas adicionar um arquivo de ponte e declarar missão cumprida.

## 4. Inventário antes da adaptação

Antes de alterar a organização de um projeto, localizar quando existirem:

- README e entrypoints;
- AGENTS, START_HERE, handoffs e bootstraps;
- regras de continuidade;
- semântica de palavras-chave;
- regras de ataque;
- regras de Git, branch e release;
- checkpoints;
- estado e progresso;
- filas e NEXT;
- manifests e provenance;
- barras e relatórios;
- regras especiais autorizadas pelo usuário;
- workflows e scripts que dependam desses arquivos.

Não reorganizar antes de entender a função do que já existe.

## 5. Classificação para convergência

Durante a adaptação, cada regra ou mecanismo existente deve ser classificado pelo papel que exerce.

### `SHARED_BASE`

A regra local já corresponde a um princípio universal.

Pode continuar localmente por compatibilidade ou clareza, mas sua função também é coberta pela lei universal.

### `LOCAL_SPECIALIZATION`

A regra é válida e necessária apenas para aquele projeto.

Exemplos: branch específica, hardware-alvo, loader, workflow, ordem de arquivos, gates técnicos, formato de release ou categorias próprias de progresso.

Ela permanece local.

### `AUTHORIZED_EXCEPTION`

A regra local contraria uma regra universal, mas o usuário autorizou explicitamente essa exceção naquele projeto ou escopo.

Ela permanece local, documentada e limitada ao escopo autorizado.

### `UNIVERSAL_CANDIDATE`

A prática nasceu em um projeto, funciona bem, não depende de características exclusivas daquele projeto e pode melhorar a governança dos demais.

Ela deve ser considerada para promoção a `Regras-projetos` quando o usuário aprovar sua universalização.

### `CONFLICT_TO_RECONCILE`

Existe conflito real entre sistema local e universal e ainda não há decisão suficiente para classificá-lo como especialização ou exceção autorizada.

Nesse caso:

- não apagar nenhum dos lados silenciosamente;
- entender a função de ambos;
- continuar trabalho não afetado;
- resolver pela evidência, objetivo atual ou autorização do usuário quando necessário.

## 6. Aprendizado bidirecional

A adaptação não acontece somente do repositório central para os projetos.

Projetos também podem ensinar a governança universal.

Se uma prática local provar ser:

- útil em vários projetos;
- independente de tecnologia específica;
- melhor do que a regra universal existente;
- consistente com os objetivos gerais;

essa prática pode virar `UNIVERSAL_CANDIDATE` e ser incorporada à lei universal com autorização do usuário.

Assim, a Constituição evolui a partir da experiência real dos cidadãos em vez de existir isolada deles.

## 7. Mix, não substituição cega

Durante a adaptação, preferir síntese.

Exemplos:

```text
lei universal define checkpoint preventivo
+
projeto já possui checkpoint com formato próprio
=
manter o formato local e reconhecer sua função universal
```

```text
projeto possui regra de ataque mais detalhada
+
lei universal define ataca/tudo
=
manter detalhes locais e herdar a semântica universal
```

```text
projeto criou uma prática excelente aplicável aos demais
=
marcar como UNIVERSAL_CANDIDATE
```

Não duplicar a mesma regra em cinco arquivos sem necessidade, mas também não apagar documentação local útil apenas porque existe uma formulação universal.

## 8. Adaptação incremental

Projetos ativos não precisam parar seu desenvolvimento, pesquisa, reconstrução ou testes para reorganizar toda a governança de uma vez.

A adaptação pode ocorrer em etapas enquanto o trabalho técnico continua.

Prioridade:

1. garantir continuidade;
2. criar referência para a governança universal;
3. mapear regras locais existentes;
4. resolver conflitos que realmente afetem trabalho atual;
5. convergir estruturas gradualmente;
6. promover boas práticas universais quando apropriado.

## 9. Compatibilidade com entrypoints existentes

Arquivos existentes usados por chats, Codex, scripts ou workflows devem continuar funcionando enquanto forem úteis.

Pode-se:

- mantê-los como entrypoints;
- fazê-los apontar para a governança universal;
- consolidar conteúdo aos poucos;
- remover duplicação somente quando não houver perda de continuidade.

A nova organização não deve quebrar deliberadamente rotas de retomada que já funcionam.

## 10. Palavras-chave durante a adaptação

Projetos que já usam `ataca`, `tudo` ou aliases locais devem convergir com `KEYWORDS.md`.

Se a semântica local já for compatível, ela permanece e apenas passa a herdar formalmente a regra universal.

Se houver comportamento adicional útil apenas naquele projeto, ele continua como especialização local.

Se houver diferença real, classificá-la como `AUTHORIZED_EXCEPTION`, `UNIVERSAL_CANDIDATE` ou `CONFLICT_TO_RECONCILE`, conforme o caso.

## 11. Critério de adaptação concluída

Um projeto está adaptado quando:

- reconhece `Regras-projetos` como lei-base;
- continua plenamente retomável;
- suas regras locais úteis estão preservadas e encontráveis;
- as regras universais aplicáveis foram incorporadas à operação real;
- conflitos relevantes foram reconciliados ou classificados;
- exceções autorizadas estão registradas;
- boas práticas locais universalizáveis foram identificadas quando existirem;
- nenhum estado, evidência, funcionalidade ou continuidade foi perdido durante a adaptação.

## 12. Princípio final

Adaptação não é apagar o passado nem congelá-lo.

É fazer os sistemas convergirem.

A lei melhora os projetos e os projetos melhoram a lei.