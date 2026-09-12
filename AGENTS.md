# AGENTS.md — bootstrap obrigatório

Este arquivo é a porta de entrada operacional para qualquer chat/agente que trabalhe nos projetos governados por este repositório.

## Antes de agir

Leia, nesta ordem:

1. `GLOBAL_RULES.md`
2. `GITHUB_PROTOCOL.md`
3. o perfil correto em `projects/`
4. os arquivos de boot/estado apontados pelo perfil no repositório real do projeto
5. HEAD/checkpoint/evidências atuais

Não peça ao usuário para reexplicar informação que já está persistida e acessível no GitHub.

## Fonte de verdade

O GitHub persistido vence memória parcial, conversa antiga e frontend/spinner.

Nunca recomece investigação, recuperação, portabilidade, build ou reconstrução do zero se o repositório já documenta estado válido.

## Semântica de `ataca`

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

Pare somente por conclusão verificável, bloqueio externo real ou decisão indispensável que só o usuário pode fornecer.

## Anti-lite / anti-stall

Uma rota falhar não encerra o ataque inteiro.

Não deixe uma única etapa opaca consumir indefinidamente a passagem sem checkpoint ou evidência. Após tentativas realmente equivalentes e cegas sem avanço, marque a rota como `STALLED`, preserve o diagnóstico e pivote.

## Persistência obrigatória

Mudança material não termina no chat.

Quando houver alteração real, persistir no repositório oficial correspondente e registrar evidência/checkpoint compatível com o projeto.

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

Se uma operação específica estiver fora de escopo, isole apenas essa operação e continue o restante permitido do projeto. Não use uma limitação pontual como desculpa para abandonar tarefas independentes.

## Eficiência

Para GitHub, prefira o conector GitHub e os scripts existentes nos repositórios.

Não abra Work/Codex por hábito para operações que podem ser feitas diretamente. Preserve o limite dessas ferramentas para trabalho que realmente precise delas.

## Relatório

Relatórios substanciais devem ser consolidados, objetivos e baseados no estado persistido. Quando o projeto usa barras, preserve todas as barras obrigatórias e marque somente avanços reais.

Ao concluir uma passagem, informe o que mudou, o que foi validado, o commit/build relevante e o único bloqueio real restante, se existir.
