# KEYWORDS.md — Palavras-chave operacionais universais

Este arquivo define palavras que, quando usadas pelo usuário no contexto de um projeto, possuem significado operacional estável em todos os projetos governados por `Regras-projetos`.

As palavras-chave não substituem regras locais, estado atual, gates ou critérios técnicos do projeto. Elas definem **como o agente deve interpretar a autorização de trabalho**.

## 1. `ataca`

`ataca` é um comando de execução **contínuo, absoluto e exaustivo dentro do escopo aplicável**.

Quando o usuário disser `ataca`, o agente deve iniciar ou retomar o trabalho no alvo atual e tentar cobrir **todo o escopo desse alvo**, não apenas uma primeira etapa, uma amostra ou as partes consideradas mais importantes.

Isso significa:

- avançar materialmente no projeto;
- continuar do estado/checkpoint atual;
- cobrir exaustivamente tudo que pertence ao escopo aplicável;
- atravessar subtarefas dependentes;
- corrigir e retestar falhas corrigíveis;
- continuar após commits, checkpoints e builds intermediários;
- pivotar quando uma rota se esgotar;
- explorar outras rotas úteis quando ainda houver lacunas no escopo;
- não encerrar em uma tentativa curta só para pedir outro `continua`;
- persistir trabalho material conforme as regras do projeto;
- obedecer anti-lite, anti-stall, Definition of Done e demais regras universais e locais aplicáveis.

`ataca` já contém a exigência de completude operacional do escopo atual.

Portanto, não é permitido interpretar `ataca` como:

- "faça uma parte";
- "tente uma rota";
- "avance um pouco";
- "analise os principais arquivos";
- "faça uma etapa e pare";
- "escreva um plano e aguarde" quando há ações executáveis.

Se o escopo contém 100 itens tratáveis e apenas 99 foram cobertos, o ataque ainda não esgotou o escopo.

## 2. Como determinar o escopo de `ataca`

A ordem de interpretação é:

1. objeto ou limite explicitamente indicado na mesma instrução;
2. alvo/estágio atualmente ativo;
3. tarefa atual claramente estabelecida no contexto;
4. projeto inteiro, quando o contexto deixa claro que o alvo atual é o projeto como um todo.

`ataca` é absoluto e exaustivo **dentro desse escopo aplicável**. Ele não expande automaticamente para trabalhos completamente alheios ao alvo atual.

Exemplos:

```text
"ataca o módulo X"
-> cobrir exaustivamente o módulo X dentro do objetivo atual

"ataca o estágio atual"
-> continuar até esgotar integralmente o estágio, respeitando gates reais

"ataca"
-> retomar o alvo atual e cobrir todo o escopo dele
```

## 3. `tudo`

`tudo` também é uma palavra-chave operacional e, ao mesmo tempo, um **quantificador absoluto**.

Quando usado operacionalmente, sozinho ou em frases como `faz tudo`, `manda tudo`, `vai em tudo`, `continua tudo` ou equivalentes claros, autoriza ataque contínuo e exige cobertura integral de tudo que pertence ao escopo indicado.

Como `ataca` já é absoluto e exaustivo, `tudo` **não torna `ataca` mais forte**. Ele apenas pode expressar ou delimitar explicitamente o conjunto que deve ser coberto.

`tudo` nunca deve ser reduzido silenciosamente a:

- principais arquivos;
- partes mais importantes;
- amostra representativa;
- subset conveniente;
- itens fáceis;
- primeira etapa;
- resumo do que ainda precisaria ser feito.

Se o escopo contém 100 itens e 99 foram tratados, `tudo` ainda não foi concluído.

## 4. `ataca tudo` não é uma terceira palavra-chave

`ataca tudo` **não possui semântica própria e não deve ser tratado como um comando especial separado**.

É apenas uma combinação natural das palavras `ataca` e `tudo`.

Como `ataca` sozinho já significa ataque contínuo, absoluto e exaustivo de todo o escopo aplicável, a presença de `tudo` nessa frase é redundante quanto à intensidade do ataque.

Nunca criar uma hierarquia do tipo:

```text
ataca = parcial
ataca tudo = completo
```

Isso é incorreto.

A regra correta é:

```text
ataca = ataque contínuo + absoluto + exaustivo do escopo aplicável

tudo = ataque contínuo quando operacional + quantificador absoluto do conjunto indicado
```

## 5. `tudo` como requisito de completude

Quando `tudo` qualifica um conjunto, aplica-se também a regra de completude literal de `GLOBAL_RULES.md`.

Antes de declarar conclusão, o agente deve, quando aplicável:

- inventariar o conjunto;
- conferir cobertura;
- comparar origem e destino;
- verificar contagens, caminhos ou evidências;
- declarar `INCOMPLETE` se algo requerido estiver faltando.

Não é permitido interpretar `tudo` parcialmente porque o conjunto é grande, trabalhoso ou inconveniente.

## 6. Relação com continuidade

`ataca` e `tudo` herdam integralmente as regras universais de continuidade.

Troca de chat, checkpoint, commit, build, erro corrigível, `+0`, rota esgotada ou falha de uma subtarefa não encerram o comando enquanto ainda houver trabalho útil e executável dentro do escopo autorizado.

## 7. Palavras-chave locais

Cada projeto pode definir palavras-chave e aliases adicionais nas suas regras locais.

Essas palavras podem:

- ser sinônimos de `ataca`;
- representar um tipo específico de ataque;
- selecionar estágio, workflow ou modo de trabalho;
- usar `tudo` como quantificador.

Uma palavra-chave local não altera o significado universal de `ataca` ou `tudo` salvo exceção explicitamente autorizada pelo usuário.

## 8. Instrução específica vence interpretação genérica

Se o usuário disser:

```text
"ataca, mas só o módulo X"
```

então o módulo X é o escopo, e o ataque deve ser absoluto e exaustivo **dentro dele**.

Se disser:

```text
"faz tudo desta pasta, não do projeto inteiro"
```

então a pasta é o conjunto absoluto, não o projeto inteiro.

A delimitação explícita define o escopo; a palavra-chave define a profundidade e continuidade dentro dele.

## 9. Princípio final

Palavra-chave operacional existe para impedir que uma autorização clara vire uma sequência de microperguntas.

Se o usuário disser `ataca`, avance até esgotar todo o escopo atual que puder ser executado.

Se disser `tudo`, cubra integralmente o conjunto indicado e avance de forma contínua.

Não existe nível superior escondido que precise da expressão `ataca tudo`.