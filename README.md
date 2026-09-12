# Regras dos Projetos — fonte central de governança

Este repositório é o **manual canônico de comportamento, continuidade, ataque e persistência** dos projetos ativos de Jack/Midrato.

Ele existe para que um novo chat/agente possa receber este link, ler as regras e continuar o projeto correto **sem reiniciar do zero, sem depender da memória de uma conversa antiga e sem transformar cada subetapa em um novo pedido de autorização**.

## Projetos cobertos

| Projeto | Repositório de trabalho | Perfil de regras |
|---|---|---|
| Mid Pogo | `JACKMIXXV2/mid-pogo` | `projects/MID_POGO.md` |
| Humo Negro / Radio Rebelión VoiceLab | `JACKMIXXV2/radio-rebelion` | `projects/HUMO_NEGRO.md` |
| Walten Mod Loader / Recovery Lab | `JACKMIXXV2/walten-mod-loader` | `projects/WALTEN_MOD_LOADER.md` |
| WinterWonder | `JACKMIXXV2/WinterWonder` | `projects/WINTERWONDER.md` |

## Leitura obrigatória em uma nova conversa

1. `AGENTS.md`
2. `GLOBAL_RULES.md`
3. `GITHUB_PROTOCOL.md`
4. o arquivo do projeto em `projects/`
5. os entrypoints atuais apontados pelo próprio repositório do projeto
6. HEAD/estado/checkpoint/evidências atuais do projeto

**Não substitua essa ordem por histórico de chat.** O chat ajuda a interpretar; o GitHub persistido decide o estado real.

## Separação importante: regras x estado

Este repositório centraliza **regras estáveis e a ordem de retomada**.

O estado volátil de cada projeto — versão atual, porcentagem, estágio, fila, checkpoint, build, commit, gate e próximo alvo — continua pertencendo ao repositório do próprio projeto. Não congele aqui uma porcentagem como se ela fosse eterna.

Hierarquia geral:

```text
regras de segurança/plataforma aplicáveis
> Regras-projetos/AGENTS.md + GLOBAL_RULES.md
> perfil central do projeto
> HEAD + arquivos canônicos atuais do repositório do projeto
> checkpoints/evidências/provenance
> histórico de conversa
> spinner/estado visual do frontend
```

Se o perfil central e o estado atual do projeto divergirem em uma informação **volátil**, vale o estado atual do projeto. Se divergirem em uma **regra/invariante**, não faça alteração silenciosa: preserve a regra mais restritiva e registre a inconsistência.

## Palavra-chave `ataca`

Em todos os projetos cobertos, salvo regra específica mais restritiva, `ataca` significa:

> executar uma passagem longa, autônoma, profunda e produtiva no estágio/alvo atual, continuando por subtarefas, correções, testes, commits e pivôs úteis sem exigir novo `continua` a cada microetapa.

As condições de parada e o protocolo completo estão em `GLOBAL_RULES.md`.

## GitHub é persistência, não decoração

Mudança material que só existe no chat ou em workspace efêmero **não está concluída**. Ataques relevantes devem persistir código, documentação, evidência ou checkpoint no repositório oficial correspondente quando houver mudança real.

O protocolo de leitura, escrita, commits, CI, bugs, conflitos e artefatos está em `GITHUB_PROTOCOL.md`.

## Regra de completude

Palavras como `tudo`, `completo`, `1:1`, `inteiro`, `absoluto`, `full`, `total` e equivalentes são literais. Uma seleção dos “arquivos importantes” não é o todo. Se faltar algo do escopo solicitado, o resultado é `INCOMPLETE` e deve dizer exatamente o que falta.

## Eficiência de ferramentas

Para tarefas de GitHub, prefira o conector GitHub, scripts do próprio repositório e ferramentas diretas. **Não consuma Work/Codex apenas para fazer operações que o fluxo direto já resolve.** Use ambientes mais pesados somente quando forem realmente necessários ou explicitamente pedidos.

## Manutenção deste repositório

Quando uma regra estável de projeto mudar:

1. atualize primeiro a fonte canônica do projeto, quando aplicável;
2. atualize o perfil correspondente aqui;
3. não copie estado efêmero desnecessário;
4. mantenha links/ordem de boot válidos;
5. registre a mudança em commit claro.

Objetivo final: **um link para colocar qualquer chat nos trilhos antes que ele invente seu próprio folclore operacional.**
