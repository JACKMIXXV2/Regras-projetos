# KEYWORDS.md — Palavras-chave operacionais universais

Este arquivo define palavras que, quando usadas pelo usuário no contexto de um projeto, possuem significado operacional estável em todos os projetos governados por `Regras-projetos`.

As palavras-chave não substituem regras locais, estado atual, gates ou critérios técnicos do projeto. Elas definem **como o agente deve interpretar a autorização de trabalho**.

## 1. `ataca`

`ataca` é um comando de execução.

Quando o usuário disser `ataca`, o agente deve iniciar ou retomar um ataque contínuo no alvo atual do projeto.

Isso significa:

- avançar materialmente no projeto;
- continuar do estado/checkpoint atual;
- atravessar subtarefas dependentes;
- corrigir e retestar falhas corrigíveis;
- continuar após commits, checkpoints e builds intermediários;
- pivotar quando uma rota se esgotar;
- não encerrar em uma tentativa curta só para pedir outro `continua`;
- persistir trabalho material conforme as regras do projeto;
- obedecer anti-lite, anti-stall, Definition of Done e demais regras universais e locais aplicáveis.

`ataca` não significa apenas analisar, listar possibilidades ou escrever um plano quando existem ações executáveis que podem avançar o projeto naquele momento.

## 2. `tudo`

`tudo` possui dois efeitos simultâneos: **comando de ataque** e **quantificador absoluto**.

Quando usado operacionalmente, sozinho ou em frases como `faz tudo`, `manda tudo`, `vai em tudo`, `continua tudo` ou equivalentes claros, deve ser interpretado como autorização para atacar continuamente o escopo atual **até cobrir integralmente tudo que pertence a esse escopo**.

Portanto:

```text
ataca = ataque contínuo no alvo atual

tudo = ataque contínuo + escopo absoluto dentro do alvo atual

ataca tudo = ataque contínuo e exaustivo de todo o escopo atual
```

`tudo` nunca deve ser reduzido silenciosamente a:

- principais arquivos;
- partes mais importantes;
- amostra representativa;
- subset conveniente;
- itens fáceis;
- primeira etapa;
- resumo do que ainda precisaria ser feito.

Se o escopo contém 100 itens e 99 foram tratados, `tudo` ainda não foi concluído.

## 3. Como determinar o escopo de `tudo`

A ordem de interpretação é:

1. objeto explicitamente indicado na mesma instrução;
2. alvo/estágio atualmente ativo;
3. tarefa atual claramente estabelecida no contexto;
4. projeto atual, quando o usuário claramente usa `tudo` para abranger o projeto inteiro.

`tudo` é absoluto **dentro do escopo aplicável**. Ele não expande automaticamente para trabalhos completamente alheios ao projeto ou ao alvo atual.

Exemplos:

```text
"analisa tudo desta pasta"
-> todos os itens da pasta pertencentes ao escopo

"ataca tudo do estágio atual"
-> ataque contínuo até esgotar integralmente o estágio

"faz tudo no projeto"
-> todo o conjunto de trabalho pertencente ao projeto, respeitando gates e dependências
```

## 4. `tudo` como requisito de completude

Quando `tudo` qualifica um conjunto, aplica-se também a regra de completude literal de `GLOBAL_RULES.md`.

Antes de declarar conclusão, o agente deve, quando aplicável:

- inventariar o conjunto;
- conferir cobertura;
- comparar origem e destino;
- verificar contagens, caminhos ou evidências;
- declarar `INCOMPLETE` se algo requerido estiver faltando.

Não é permitido interpretar `tudo` parcialmente porque o conjunto é grande, trabalhoso ou inconveniente.

## 5. Relação com continuidade

`ataca` e `tudo` herdam integralmente as regras universais de continuidade.

Troca de chat, checkpoint, commit, build, erro corrigível, `+0`, rota esgotada ou falha de uma subtarefa não transformam o comando em encerrado enquanto ainda houver trabalho útil e executável no escopo autorizado.

## 6. Palavras-chave locais

Cada projeto pode definir palavras-chave e aliases adicionais nas suas regras locais.

Essas palavras podem:

- ser sinônimos de `ataca`;
- representar um tipo específico de ataque;
- selecionar estágio, workflow ou modo de trabalho;
- combinar-se com `tudo`.

Uma palavra-chave local não altera o significado universal de `ataca` ou `tudo` salvo exceção explicitamente autorizada pelo usuário.

## 7. Instrução específica vence interpretação genérica

Se o usuário disser algo como:

```text
"ataca, mas só o módulo X"
```

ou:

```text
"faz tudo desta pasta, não do projeto inteiro"
```

a delimitação explícita define o escopo.

A palavra-chave continua tendo seu significado operacional, mas dentro do limite especificado pelo usuário.

## 8. Princípio final

Palavra-chave operacional existe para evitar o padrão inútil de transformar autorização clara em uma sequência de microperguntas.

Se o usuário disser `ataca`, avance.

Se disser `tudo`, avance e cubra o conjunto inteiro.

Se disser `ataca tudo`, faça ambos ao mesmo tempo.