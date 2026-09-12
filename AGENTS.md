# AGENTS.md — bootstrap universal obrigatório

Este arquivo é a porta de entrada operacional para qualquer chat, agente, Codex ou ferramenta que trabalhe em qualquer projeto governado por `Regras-projetos`.

Não existe perfil central por projeto. A lei é universal; o estado e as especializações pertencem ao próprio repositório do projeto.

## Antes de agir

Leia, nesta ordem:

1. `CONSTITUTION.md`
2. `GLOBAL_RULES.md`
3. `GITHUB_PROTOCOL.md`
4. identifique o repositório real do projeto
5. leia os arquivos locais de bootstrap/regras/estado existentes nesse projeto
6. confirme HEAD, branch, checkpoint, evidências, filas e builds atuais quando aplicável

Não peça ao usuário para reexplicar informação que já está persistida e acessível.

## Relação entre lei universal e regras locais

Regras locais podem especializar detalhes como:

- branches;
- versionamento;
- ordem de boot;
- categorias de progresso;
- hardware-alvo;
- workflows;
- testes;
- gates;
- estrutura interna.

Elas não podem cancelar princípios universais deste repositório.

Quando houver conflito verdadeiro, a lei universal prevalece. Quando houver apenas especialização, as duas valem simultaneamente.

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

## Preservação de baseline

Comportamento previamente validado é baseline.

Não remover, reescrever, degradar ou “corrigir” silenciosamente baseline funcional só porque uma implementação diferente parece mais elegante. Mudança incompatível exige motivo, evidência e registro.

## Segurança e escopo

Trabalhar normalmente em componentes próprios/autorizados. Em controles externos de terceiros, não criar nem aprimorar mecanismos destinados a contornar pagamento, licença, autenticação, integridade/anti-cheat ou outros controles externos.

Se uma operação específica estiver fora de escopo, isole apenas essa operação e continue o restante permitido do projeto.

## Eficiência

Use primeiro a ferramenta mais direta que resolva a tarefa.

Para GitHub, prefira o conector GitHub e scripts existentes. Não abra Work/Codex por hábito para operações que podem ser feitas diretamente. Preserve ferramentas mais pesadas para trabalho que realmente precise delas.

## Relatório

Relatórios substanciais devem ser consolidados, objetivos e baseados no estado persistido. Quando o projeto usa barras, preserve todas as barras definidas localmente e marque somente avanços reais.

Ao concluir uma passagem, informe o que mudou, o que foi validado, o commit/build relevante e o bloqueio real restante, se existir.
