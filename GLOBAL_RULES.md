# GLOBAL_RULES.md — regras universais dos projetos

Estas regras valem para **todos os projetos atuais e futuros** governados por `Regras-projetos`.

Não existe lista fechada de projetos. Um projeto novo não precisa ser cadastrado aqui para passar a obedecer estas regras.

## 1. Continuidade acima de conversa

- O repositório oficial do projeto é a fonte persistente de verdade sobre seu estado.
- Não reiniciar trabalho validado porque o chat mudou, o frontend perdeu contexto ou um spinner voltou para estado antigo.
- Antes de agir, ler HEAD, estado atual, último checkpoint, evidências e filas existentes quando aplicável.
- Histórico de conversa é contexto auxiliar, não autoridade superior ao estado persistido.

## 2. `ataca` = autorização contínua

Quando o usuário disser `ataca`, interpretar como autorização para uma passagem longa, autônoma, profunda e produtiva no estágio/alvo atual.

O ataque continua através de:

- subtarefas dependentes;
- correções e retestes;
- commits intermediários;
- builds e CI;
- hipóteses falsificadas;
- rotas que retornam `+0`;
- checkpoints;
- pivôs para outras rotas úteis.

Não transformar `ataca` em uma tentativa curta seguida de pedido de novo `continua`.

### Condições válidas de parada

1. estágio/alvo concluído de forma verificável;
2. bloqueio externo real que impede todo o trabalho útil restante daquele alvo;
3. decisão indispensável que somente o usuário pode fornecer;
4. artefato, hardware, credencial ou validação externa indispensável que não está acessível.

Antes de parar por bloqueio, concluir tudo que ainda for possível sem ele.

## 3. Anti-lite

Não encerrar um ataque inteiro porque:

- uma rota falhou;
- uma hipótese morreu;
- um job falhou;
- um arquivo não existia;
- uma operação deu `+0`;
- um checkpoint foi criado;
- uma subtarefa específica ficou bloqueada.

Enquanto existir outra rota produtiva e permitida, continuar.

## 4. Anti-stall

- Não deixar uma etapa opaca monopolizar indefinidamente o ataque sem nova evidência.
- Após tentativas realmente equivalentes e cegas sem avanço, registrar `STALLED` e pivotar.
- Evidência nova, parâmetro novo, arquivo novo, comportamento novo ou hipótese materialmente diferente justificam nova tentativa.
- Um frontend parado não prova que o backend ou o GitHub também pararam.

## 5. Completude literal

`all`, `everything`, `tudo`, `completo`, `full`, `total`, `1:1`, `inteiro`, `absoluto`, `entire workspace`, `entire project` e equivalentes significam o conjunto integral solicitado.

Para declarar `COMPLETE`:

- inventariar o conjunto de origem;
- incluir todos os tipos de artefato pertencentes ao escopo;
- comparar origem e destino;
- validar contagens, caminhos e hashes quando aplicável;
- listar exceções explicitamente.

Se um único item requerido não puder ser transferido ou verificado, declarar `INCOMPLETE` e dizer o que falta.

## 6. Baseline é patrimônio

- Comportamento validado não deve ser removido, degradado ou reescrito silenciosamente.
- Refatoração estética não justifica regressão funcional.
- Se uma nova evidência exigir mudança incompatível, registrar a razão e preservar rastreabilidade.
- Não repetir trabalho fechado apenas para “ter certeza” sem evidência de regressão ou contradição.

## 7. Evidência antes de pontuação

Nunca inventar:

- hash;
- arquivo;
- build;
- valor técnico;
- identidade;
- resultado de teste;
- áudio;
- firmware;
- URL ou resposta de API;
- progresso;
- conclusão.

Use `NOT_PROVEN`, `UNKNOWN`, `CANDIDATE`, `BLOCKED` ou equivalente em vez de preencher lacunas com suposição.

## 8. Barras e progresso

Quando um projeto usa barras:

- preservar todas as categorias definidas localmente entre relatórios;
- `>>>` somente em linha que realmente avançou;
- mostrar `anterior -> novo` quando houver avanço;
- nova versão, commit ou documentação não sobe barra por si só;
- percentual geral deve derivar do estado persistido, não de estética;
- evidência nova pode reduzir uma barra superestimada.

## 9. Regra de 100% por estágio

Quando um projeto define estágios com gate:

- 85%, 90% ou 99% ainda significam estágio aberto;
- não abandonar estágio aberto para começar o seguinte apenas porque a parte restante é difícil ou inconveniente;
- se a parte final depende de hardware, humano ou ambiente externo, concluir primeiro todo o pré-gate executável e registrar exatamente o gate restante;
- não usar trabalho do estágio seguinte para fingir que o anterior estava completo.

## 10. Correção de bug

Quando o usuário reporta bug de build, EXE, APK, JAR, runtime, serviço ou outro artefato testável:

1. tratar log, print ou comportamento como evidência da versão testada;
2. diagnosticar a causa;
3. corrigir no produto quando a correção pertence ao produto;
4. adicionar teste ou contrato quando possível;
5. criar nova versão/build identificável quando a política local exigir versionamento por mudança;
6. persistir em commit;
7. executar build, CI ou teste aplicável;
8. entregar o novo artefato, não fingir que o artefato antigo mudou magicamente.

## 11. Estado volátil pertence ao projeto

Este repositório central não deve guardar cópias congeladas de versão, porcentagem, estágio, fila, commit, build ou próximo alvo de projetos individuais.

A lei fica aqui. O estado atual fica no repositório do cidadão.

## 12. Regras locais podem especializar, não revogar

Um projeto pode criar regras próprias para sua realidade técnica.

Essas regras podem definir:

- branches;
- versionamento;
- ordem de leitura;
- estruturas de pasta;
- categorias de progresso;
- hardware-alvo;
- gates;
- testes;
- CI;
- formato de release;
- contratos técnicos.

Elas não podem cancelar regras universais deste repositório.

Se houver conflito verdadeiro, a regra universal vence. Se não houver conflito, a regra local especializa a aplicação.

## 13. Segurança e isolamento de operações

- Componentes próprios ou autorizados podem ser analisados, depurados, instrumentados e testados normalmente.
- Não criar nem aprimorar mecanismos destinados a contornar controles externos de pagamento, licença, autenticação, integridade, anti-cheat ou equivalentes de terceiros.
- Se uma operação específica estiver limitada, bloquear só aquela operação e continuar as demais rotas independentes.

## 14. Eficiência e uso de ferramentas

- Preferir a ferramenta mais direta que execute o trabalho corretamente.
- Preferir GitHub direto para leitura e escrita de repositório.
- Preferir scripts e automações já existentes no projeto.
- Não consumir Work/Codex quando ferramentas diretas resolvem o mesmo trabalho.
- Não fazer micro-relatórios no lugar de executar ações disponíveis.
- Não prometer trabalho futuro em background; execute o máximo possível na passagem atual.

## 15. Relatório consolidado

Ao final de um ataque substancial, o relatório deve separar claramente:

- o que foi descoberto;
- o que foi alterado;
- o que foi validado;
- o que apenas foi preparado;
- commit, build ou artefato correspondente;
- avanço real de barras, se houver;
- bloqueio externo restante, se houver.

Atividade não é progresso. Evidência é progresso.
