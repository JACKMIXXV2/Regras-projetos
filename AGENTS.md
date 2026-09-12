# AGENTS.md — bootstrap universal obrigatório

Este arquivo é a porta de entrada operacional para qualquer chat, agente, Codex ou ferramenta que trabalhe em qualquer projeto governado por `Regras-projetos`.

Não existe perfil central por projeto. A lei é universal; o estado, as especializações e as exceções autorizadas pertencem ao próprio repositório do projeto.

## Antes de agir

Leia, nesta ordem:

1. `CONSTITUTION.md`
2. `GLOBAL_RULES.md`
3. `GITHUB_PROTOCOL.md`
4. identifique o repositório real do projeto
5. leia os arquivos locais de bootstrap, regras e estado existentes nesse projeto
6. confirme HEAD, branch, checkpoint, evidências, filas e builds atuais quando aplicável
7. se o projeto for anterior a esta governança ou usar organização legada, aplique `ADOPTION_PROTOCOL.md`

Não peça ao usuário para reexplicar informação que já está persistida e acessível.

## Relação entre lei universal e regras locais

Regras locais são parte normal da arquitetura e podem definir:

- branches;
- versionamento;
- ordem de boot;
- categorias de progresso;
- hardware-alvo;
- workflows;
- testes;
- gates;
- estrutura interna;
- políticas específicas do projeto.

Por padrão, elas especializam a lei universal.

Uma regra local também pode contrariar uma regra universal quando houver **autorização explícita do usuário** para essa exceção. Exceção persistente deve ser registrada no próprio projeto e vale somente no escopo autorizado.

Nunca invente uma exceção local nem suponha que a exceção de um projeto vale para outro.

## Instrução mais recente

Quando o usuário corrigir ou substituir uma instrução anterior sobre o mesmo assunto, siga a instrução mais recente a partir daquele ponto.

Preserve evidências, histórico, commits e artefatos anteriores; mude a direção operacional, não os fatos já ocorridos.

## Fonte de verdade

GitHub e artefatos persistidos vencem memória parcial, conversa antiga e frontend/spinner.

Nunca reinicie investigação, recuperação, portabilidade, build, reconstrução ou implementação do zero se o projeto já possui estado válido persistido.

## Semântica universal de `ataca`

`ataca` autoriza uma passagem longa e autônoma no alvo atual.

Enquanto houver trabalho útil, permitido e executável:

- continue após commit;
- continue após checkpoint;
- continue após teste;
- continue após hipótese falsificada ou `+0`;
- corrija falhas corrigíveis e reteste no mesmo ataque;
- pivote quando uma rota morrer;
- use outra frente produtiva enquanto uma dependência externa roda;
- não peça novo `continua` para cada subetapa.

Pare somente pelas condições universais definidas em `GLOBAL_RULES.md`.

## Anti-lite / anti-stall

Uma rota falhar não encerra o ataque inteiro.

Não deixe uma única etapa opaca consumir indefinidamente a passagem sem checkpoint ou evidência. Após tentativas realmente equivalentes e cegas sem avanço, marque a rota como `STALLED`, preserve o diagnóstico e pivote.

## Checkpoint preventivo

Não espere o fim de uma passagem longa para proteger trabalho material.

Crie checkpoint ou commit seguro depois de avanço significativo e antes de operações arriscadas quando isso reduzir risco de perda. O checkpoint protege continuidade e **não encerra o ataque**.

## Persistência obrigatória

Mudança material não termina no chat.

Quando houver alteração real, persistir no repositório oficial correspondente e registrar evidência/checkpoint compatível com aquele projeto.

Não sobrescrever estado mais novo sem antes reler HEAD e o arquivo atual.

## Completude literal

Se o pedido disser `tudo`, `completo`, `1:1`, `inteiro`, `full`, `total` ou equivalente:

- inventarie o conjunto solicitado;
- compare origem e destino;
- verifique contagem/caminhos quando aplicável;
- não substitua o todo por resumo, amostra ou “arquivos importantes”;
- se faltar qualquer item do escopo, marque `INCOMPLETE`.

## Evidência e progresso

Não invente artefato, valor, identidade, hash, build, resultado, porcentagem ou conclusão.

`>>>` só aparece quando houve avanço material comprovável. Nova versão, novo commit ou documentação isolada não sobe barra automaticamente.

Evidência nova pode inclusive reduzir uma pontuação antiga se mostrar que ela estava superestimada.

## Preservação e não sabotagem

Comportamento previamente validado é baseline.

Não remover, reescrever, degradar ou “corrigir” silenciosamente baseline funcional só porque outra implementação parece mais conveniente.

Também não remover evidência, ferramenta, checkpoint, compatibilidade, arquivo ou estado útil para simplificar trabalho, reduzir escopo ou contornar limitação do agente.

## Regressão e rollback

Se uma mudança quebrar comportamento validado:

1. preserve a evidência da falha;
2. identifique o último estado bom;
3. corrija a regressão ou restaure o estado bom;
4. valide novamente;
5. persista o resultado.

Não empilhe mudanças cegamente sobre um estado conhecido como quebrado.

## Definition of Done

Não declarar uma tarefa concluída apenas porque código foi escrito ou um commit existe.

Aplicar a Definition of Done de `GLOBAL_RULES.md`: resultado realizado, persistido quando necessário, validado, sem regressão conhecida no escopo e sustentado por evidência suficiente.

## Projetos legados

Projetos anteriores a esta Constituição mantêm sua história e seus sistemas locais.

Use `ADOPTION_PROTOCOL.md` para portar a organização de forma incremental. Não apague regras antigas úteis nem reinicie o projeto para fazê-lo “caber” no modelo novo.

## Segurança e escopo

Trabalhar normalmente em componentes próprios/autorizados. Em controles externos de terceiros, não criar nem aprimorar mecanismos destinados a contornar pagamento, licença, autenticação, integridade/anti-cheat ou outros controles externos.

Se uma operação específica estiver fora de escopo, isole apenas essa operação e continue o restante permitido do projeto.

Regras adicionais de segurança, publicação e distribuição podem ser definidas localmente por projeto.

## Eficiência

Use primeiro a ferramenta mais direta que resolva a tarefa.

Para GitHub, prefira o conector GitHub e scripts existentes. Não abra Work/Codex por hábito para operações que podem ser feitas diretamente. Preserve ferramentas mais pesadas para trabalho que realmente precise delas.

## Relatório

Relatórios substanciais devem ser consolidados, objetivos e baseados no estado persistido. Quando o projeto usa barras, preserve todas as barras definidas localmente e marque somente avanços reais.

Ao concluir uma passagem, informe o que mudou, o que foi validado, o commit/build relevante e o bloqueio real restante, se existir.