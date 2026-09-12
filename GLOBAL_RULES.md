# GLOBAL_RULES.md — regras universais dos projetos

Estas regras valem para **todos os projetos atuais e futuros** governados por `Regras-projetos`.

Não existe lista fechada de projetos. Um projeto novo não precisa ser cadastrado aqui para passar a obedecer estas regras.

## 1. Continuidade acima de conversa

- O repositório oficial do projeto é a fonte persistente de verdade sobre seu estado.
- Não reiniciar trabalho validado porque o chat mudou, o frontend perdeu contexto ou um spinner voltou para estado antigo.
- Antes de agir, ler HEAD, estado atual, último checkpoint, evidências e filas existentes quando aplicável.
- Histórico de conversa é contexto auxiliar, não autoridade superior ao estado persistido.

## 2. Palavras-chave operacionais

As palavras-chave universais são definidas em `KEYWORDS.md`.

Regras mínimas obrigatórias:

```text
ataca = ataque contínuo no alvo atual

tudo = ataque contínuo + escopo absoluto dentro do alvo atual

ataca tudo = ataque contínuo e exaustivo do escopo atual
```

Quando o usuário disser `ataca`, interpretar como autorização para uma passagem longa, autônoma, profunda e produtiva no estágio/alvo atual.

Quando o usuário disser `tudo` operacionalmente, interpretar também como comando de ataque, mas exigindo cobertura integral de tudo que pertence ao escopo aplicável.

Não transformar nenhum dos dois em tentativa curta seguida de pedido de novo `continua`.

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

`tudo` possui regra adicional: além de ser quantificador absoluto, também funciona como comando de ataque contínuo conforme `KEYWORDS.md`.

Para declarar `COMPLETE`:

- inventariar o conjunto de origem;
- incluir todos os tipos de artefato pertencentes ao escopo;
- comparar origem e destino;
- validar contagens, caminhos e hashes quando aplicável;
- listar exceções explicitamente.

Se um único item requerido não puder ser transferido, analisado ou verificado, declarar `INCOMPLETE` e dizer o que falta.

Nunca reduzir silenciosamente `tudo` para “o importante”, “os principais”, “uma amostra” ou “o que deu tempo”.

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

## 12. Regras locais e exceções autorizadas

Regras locais **podem e devem existir** sempre que um projeto possuir necessidades próprias.

Elas podem definir, entre outras coisas:

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
- contratos técnicos;
- regras de segurança específicas;
- convenções próprias de continuidade;
- palavras-chave e aliases adicionais.

Por padrão, regras locais especializam a lei universal sem contradizê-la.

Entretanto, uma regra local pode contrariar uma regra universal quando o usuário autorizar explicitamente essa exceção.

Nesse caso:

- a exceção vale somente no escopo autorizado;
- deve ser persistida no projeto se for duradoura;
- não altera os demais projetos;
- não pode ser inventada ou presumida pelo agente;
- instrução posterior do usuário pode alterá-la ou revogá-la.

Sem exceção autorizada, prevalece a regra universal.

## 13. Segurança e isolamento de operações

- Componentes próprios ou autorizados podem ser analisados, depurados, instrumentados e testados normalmente.
- Não criar nem aprimorar mecanismos destinados a contornar controles externos de pagamento, licença, autenticação, integridade, anti-cheat ou equivalentes de terceiros.
- Se uma operação específica estiver limitada, bloquear só aquela operação e continuar as demais rotas independentes.
- Regras adicionais de segurança, privacidade, publicação ou distribuição podem ser definidas localmente por projeto.

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

## 16. Instrução mais recente prevalece

Quando o usuário altera, corrige ou substitui uma instrução anterior sobre o mesmo assunto, a instrução mais recente passa a reger o trabalho a partir daquele ponto.

Isso não significa apagar o passado:

- evidências anteriores continuam existindo;
- histórico técnico continua rastreável;
- commits e artefatos antigos continuam sendo fatos;
- apenas a direção operacional atual muda.

Não continuar executando uma ordem antiga depois de ela ter sido explicitamente substituída.

## 17. Checkpoint preventivo

Ataques longos não devem depender de um único salvamento no final.

Sempre que aplicável, criar checkpoint ou commit seguro:

- após avanço material significativo;
- antes de operação destrutiva ou arriscada;
- antes de grande refatoração;
- antes de alterar estruturas centrais de estado;
- quando uma longa passagem já produziu trabalho que seria caro reconstruir.

Checkpoint não encerra ataque. Ele existe para proteger continuidade.

O formato do checkpoint pode ser definido localmente pelo projeto.

## 18. Regra explícita de não sabotagem

É proibido remover deliberadamente funcionalidade válida, evidência, ferramenta, arquivo, compatibilidade, checkpoint ou estado útil apenas para:

- simplificar o trabalho do agente;
- reduzir artificialmente o escopo;
- evitar uma parte difícil;
- contornar uma limitação de ferramenta;
- fazer uma barra parecer mais completa;
- substituir um sistema funcional por outro mais conveniente sem necessidade técnica.

Quando uma remoção for tecnicamente necessária, ela deve ser justificada, rastreável e respeitar baseline, regras locais e autorizações do usuário.

## 19. Rollback e último estado bom

Se uma alteração nova quebrar comportamento previamente validado:

1. preservar evidência da falha;
2. identificar o último estado conhecido como bom;
3. decidir entre corrigir a regressão ou restaurar o estado bom;
4. evitar empilhar novas mudanças cegamente sobre um estado quebrado;
5. validar novamente depois da correção ou rollback;
6. registrar o resultado no projeto.

Rollback não deve apagar a evidência que explicou por que ele foi necessário.

## 20. Definition of Done universal

Salvo critério local mais específico ou exceção autorizada, `DONE`, `FEITO`, `CONCLUÍDO` ou equivalente exige, dentro do escopo da tarefa:

1. implementação, análise ou alteração realmente realizada;
2. resultado persistido quando houver mudança material;
3. validação aplicável concluída;
4. ausência de regressão conhecida dentro do escopo validado;
5. evidência suficiente registrada para sustentar a conclusão;
6. bloqueios restantes explicitamente separados do que foi concluído.

`código escrito`, `arquivo criado`, `commit feito` ou `build iniciada` não significam automaticamente `DONE` quando ainda falta validação exigida pelo próprio trabalho.

## 21. Adaptação por convergência

Projetos ativos que já possuem sistemas próprios se adaptam à governança universal conforme `ADAPTATION_PROTOCOL.md`.

A adaptação não usa idade como critério de supremacia:

- o sistema novo não vence só por ser novo;
- o sistema existente não vence só por estar há mais tempo em uso.

O objetivo é combinar o melhor de ambos.

Durante a adaptação:

- incorporar princípios universais aplicáveis;
- preservar especializações locais úteis;
- reconciliar duplicações e conflitos;
- registrar exceções autorizadas;
- manter continuidade e estado válidos;
- identificar práticas locais que possam virar `UNIVERSAL_CANDIDATE`;
- melhorar a lei universal quando a experiência dos projetos revelar uma prática melhor e o usuário autorizar sua promoção.

Adaptação significa convergência real, não substituição cega em nenhuma direção.