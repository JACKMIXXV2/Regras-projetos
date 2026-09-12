# ADOPTION_PROTOCOL.md — Portabilidade para a Governança Universal

Este protocolo define como projetos novos e, principalmente, projetos que **já existiam antes de `Regras-projetos`** adotam a governança universal sem perder continuidade, identidade técnica, histórico ou regras locais válidas.

## 1. Princípio de não reescrita histórica

Projetos legados não são considerados errados por terem sido criados antes desta Constituição.

A adoção do novo sistema não exige:

- reescrever toda a documentação antiga;
- renomear branches sem necessidade;
- reorganizar toda a árvore de arquivos;
- apagar sistemas anteriores de continuidade;
- alterar versionamento já estabelecido;
- descartar regras locais válidas;
- recriar checkpoints, evidências ou histórico já persistidos.

A migração deve preservar o que já funciona e apenas criar uma camada clara de integração com a governança universal.

## 2. Estado legado é patrimônio

Durante a adoção:

- preservar código, assets, ferramentas, evidências, histórico, checkpoints e regras locais existentes;
- não reduzir progresso ou apagar estado válido apenas para encaixar o projeto em um formato novo;
- não converter automaticamente regras antigas em obsoletas;
- não tratar ausência de arquivos modernos de governança como ausência de continuidade.

O objetivo é **portar a organização**, não recomeçar o projeto.

## 3. Inventário de governança existente

Antes de reorganizar um projeto legado, localizar quando existirem:

- README e entrypoints;
- AGENTS, handoffs, bootstraps e arquivos START_HERE;
- regras de continuidade;
- regras de ataque;
- regras de Git/branch/release;
- checkpoints;
- arquivos de estado/progresso;
- filas e NEXT;
- manifests e provenance;
- convenções de barras/relatórios;
- regras especiais já autorizadas pelo usuário.

Não substituir esse conjunto por uma nova estrutura sem primeiro entender qual função cada parte já cumpre.

## 4. Classificação das regras antigas

Ao adaptar um projeto legado, classificar regras antigas em quatro classes:

### `UNIVERSAL_ALREADY`
A regra antiga já expressa um princípio agora coberto por `Regras-projetos`.

Ela pode continuar documentada localmente por compatibilidade, mas a fonte universal passa a ser esta governança.

### `LOCAL_SPECIALIZATION`
A regra trata apenas daquele projeto e continua pertencendo ao repositório local.

Exemplos: branch específica, hardware-alvo, formato de release, gate técnico, ordem de arquivos, categorias de progresso.

### `AUTHORIZED_EXCEPTION`
A regra local contradiz uma regra universal, mas o usuário autorizou explicitamente a exceção para aquele projeto ou contexto.

Ela deve permanecer local, registrada como exceção autorizada e com escopo claro.

### `LEGACY_CONFLICT_UNREVIEWED`
A regra antiga contradiz a lei universal e ainda não existe autorização explícita do usuário para tratá-la como exceção.

Nesse caso:

- não apagar a regra antiga silenciosamente;
- não aplicá-la como exceção presumida;
- registrar o conflito;
- continuar todo o restante não afetado;
- obter autorização do usuário quando o conflito precisar ser resolvido para avançar.

## 5. Adoção mínima de um projeto legado

Uma migração mínima e válida deve:

1. reconhecer `Regras-projetos` como governança universal;
2. manter o estado real no próprio projeto;
3. preservar suas regras locais e sistemas antigos ainda úteis;
4. criar ou atualizar um ponto de entrada local que indique onde estão estado, regras e continuidade;
5. adicionar uma ponte para `Regras-projetos`, preferencialmente `PROJECT_GOVERNANCE.md` quando fizer sentido;
6. registrar exceções autorizadas localmente;
7. não duplicar desnecessariamente toda a Constituição dentro do projeto.

## 6. Migração incremental é válida

Projetos grandes podem adotar a nova governança em etapas.

Não é obrigatório interromper desenvolvimento, recuperação, pesquisa ou testes até toda a documentação antiga ter sido reorganizada.

Durante a transição:

- a Constituição já se aplica;
- regras locais existentes continuam válidas quando compatíveis;
- exceções autorizadas continuam válidas;
- conflitos ainda não revisados ficam marcados sem serem apagados;
- trabalho técnico produtivo pode continuar normalmente nas áreas não bloqueadas pelo conflito.

## 7. Sem migração cosmética

Não declarar um projeto “migrado” apenas porque ganhou `PROJECT_GOVERNANCE.md`.

Quando a adoção completa for solicitada, verificar também:

- se o entrypoint local aponta para o estado correto;
- se regras antigas importantes continuam encontráveis;
- se conflitos foram classificados;
- se exceções autorizadas estão registradas;
- se referências quebradas ou antigas foram corrigidas quando necessário;
- se nenhum checkpoint ou evidência foi perdido.

## 8. Compatibilidade com agentes antigos

Se o projeto possui arquivos antigos usados por Codex, chats ou scripts, preservar esses entrypoints enquanto forem úteis.

É permitido fazer os arquivos antigos apontarem para a nova organização em vez de apagá-los.

Preferir compatibilidade por encaminhamento a uma quebra abrupta que obrigue todas as ferramentas e conversas antigas a conhecer imediatamente a nova estrutura.

## 9. Projetos novos

Projetos criados depois desta governança não precisam passar por migração histórica.

Devem simplesmente:

- reconhecer a lei universal desde o início;
- guardar estado e regras específicas localmente;
- registrar qualquer exceção autorizada pelo usuário;
- criar um entrypoint de continuidade apropriado ao tamanho do projeto.

## 10. Critério de conclusão da portabilidade

Uma portabilidade para esta organização está concluída quando:

- a governança universal é reconhecida;
- o projeto continua retomável sem depender de memória informal;
- suas regras específicas permanecem preservadas;
- conflitos relevantes estão resolvidos ou explicitamente classificados;
- exceções autorizadas estão registradas;
- estado e evidências anteriores continuam acessíveis;
- nenhuma funcionalidade ou continuidade foi perdida por causa da migração.

A nova organização deve diminuir confusão, não produzir arqueologia adicional.