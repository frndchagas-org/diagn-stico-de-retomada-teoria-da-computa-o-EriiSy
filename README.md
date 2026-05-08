[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHqjFsRx)
# Diagnóstico de retomada - Teoria da Computação

Esta atividade serve para mapear o que você já domina sobre linguagens formais, autômatos, gramáticas e computabilidade.

Responda individualmente. Use suas palavras. Se usar IA depois da primeira tentativa, registre o uso na seção 7.

## 1. Mapa do que eu lembro

Marque cada tópico como: lembro bem, lembro parcialmente, não lembro, nunca vi ou não tenho certeza.

- alfabeto: lembro bem
- cadeia: lembro parcialmente
- linguagem: não tenho certeza
- gramática: lembro parcialmente
- autômato finito: lembro bem
- linguagem regular: não lembro
- linguagem livre de contexto: lembro parcialmente
- linguagem sensível ao contexto: lembro parcialmente  
- linguagem irrestrita: não lembro
- hierarquia de Chomsky: nunca vi
- computabilidade: lembro parcialmente
- máquina de Turing: lembro bem

## 2. Definições com exemplo

Explique, com suas palavras e com um exemplo simples, usando o alfabeto `Sigma = {a, b}`.

1. **O que é um alfabeto?**

   É um conjunto finito de símbolos básicos válidos que podemos usar. Exemplo: `Sigma = {a, b}`. (Corrigido com Revisão)
2. **O que é uma cadeia?**
   
   Uma sequência finita de combinações possíveis baseada em um alfabeto. Exemplos: `aba`, `bb`, `a`.  (Corrigido com Revisão)
3. **O que é uma linguagem?**

   É um conjunto de cadeias (palavras) que seguem uma regra específica ou padrão. Exemplo: A linguagem de todas as cadeias que começam com a letra 'a'. (Corrigido com Revisão)
4. **O que é uma gramática?**

   É o conjunto de regras matemáticas (o "gerador") que define exatamente quais cadeias pertencem ou não a uma linguagem. (Corrigido com Revisão)

## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:

1. **escreva três palavras que pertencem à linguagem:** (Corrigido com Revisão)
   - R: L1 `01`, `101`, `0001` (basta terminar em 01)
   - R: L2 `ab`, `aabb`, `aaabbb` (mesma quantidade de 'a' e 'b') 
   - R: L3 `abc`, `aabbcc`, `aaabbbccc` (mesma quantidade de 'a', 'b' e 'c')
2. **escreva duas palavras que não pertencem:** (Corrigido com Revisão)
   - R: L1 `10`, `11`
   - R: L2 `a`, `ba`
   - R: L3 `ab`, `cba`
3. **diga, se souber, em qual classe ela provavelmente se encaixa:** (Corrigido com Revisão)
   - R: L1 Regular
   - R: L2 Livre de Contexto
   - R: L3 Sensível ao Contexto
4. **explique o motivo em linguagem simples.** (Corrigido com Revisão)
   - R: Mesmo que eu tente explicar, ainda não entendi muito bem o conteúdo a respeito, deste modo mantenho:  Possivelmente o motivo a ser explicado se eu soubesse... seria pela capacidade de realizar diversas combinações sem necessariamente rejeitar ou confirmar mas apenas tratar como parte das sequencias finitas.
   
## Não há problema em dizer "não sei". Nesse caso, escreva o que te deixou em dúvida.

*O que me deixou em duvida foi o fato de escrever o resultado do que a linguagem pertence ou não sem saber se está ligeiramente correto as nomenclaturas*

## 4. Autômato finito

Considere o autômato abaixo, sobre o alfabeto `{0,1}`:

```text
Estados: q0, q1, q2
Estado inicial: q0
Estado final: q2

Transições:
q0 --0--> q1
q0 --1--> q0
q1 --0--> q1
q1 --1--> q2
q2 --0--> q1
q2 --1--> q0
```

Responda:

1. **Qual linguagem esse autômato parece reconhecer?**
   R: Cadeias que terminam em `01`. (Se observarmos, ele só chega no estado final q2 quando lê um '0' indo pro q1 e depois um '1' indo pro q2). (Corrigido com Revisão)
3. **Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:**
Considerando que o "rejeita" será quando não se encontra no estado final então: 
   - `01` - Aceita (q0 -> q1 -> q2)
   - `101` - Aceita (q0 -> q0 -> q1 -> q2) 
   - `100` - Rejeita (q0 -> q0 -> q1 -> q1) 
   - `1101` - Aceita (q0 -> q0 -> q0 -> q1 -> q2)
   - `111` - Rejeita (q0 -> q0 -> q0 )
4. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.

       | Estado |  0 |  1 |
       |--------|----|----|         
       | **q0** | q1 | q0 |  Corrigido*
       | **q1** | q1 | q2 | 
       | **q2** | q1 | q0 | 

        
## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. **Gere cinco cadeias produzidas por essa gramática.**
  R: {`b`,`ab`, `aab`, `aaab`, `aaaab`}
2. **Descreva a linguagem em palavras.**
  R: É uma linguagem que gera uma sequência de letras 'a' (ou nenhuma) que obrigatoriamente termina com um único 'b' (Corrigido com revisão)
3. **Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.**
   Agora, com correção, parece-se ser linear rumo a direita, aceitando a cadeia sem verificações complexas.  (Corrigido com Revisão)
   
## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva:

1. **o que você entende dele**;
   
   R: A função de transição na máquina de Turing. Acredito que consigo explicar como ela navega, pois se na função de transição a máquina lê um valor e precisa marcá-lo, ela irá rodar um looping de estados que irá transitar até finalizar a fita. Considerando uma fita com marcações (ex: transformar `1` em `X`), onde o `X` está colocado, ele já indica para o estado atual que já passou por ali, permitindo que a cabeça de leitura vá para a direita continuar o processo até finalizar. (Corrigido com revisão)
2.**onde você se confunde;**

   R: Como visto acima, normalmente me confundo e tenho dificuldade com as terminologias teóricas (como o "juridiquês" formal) e em conseguir integrá-las diretamente ao conteúdo prático. Contudo, passos lógicos e heurísticos acabam fixando com mais facilidade na minha mente.
3. **que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta.**
   
   Sou um aluno que normalmente bate dias ou horas tentando entender uma questão e dissecando-a e através disso aprendendo conteúdos, desta forma, em caso de explicações a didática em formas de exercício guiado e/ou desenhos e analogia ajudariam muito o saber. 

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:

O que ligeiramente fiz foi utilizar a IA para entender o que eu errei aqui nessa atividade, porém não pretendo mudar as respostas pois, de certo modo apenas estarei justificando silenciosamento para mim mesmo que "devo ter aprendido" enquanto na verdade, deixar esse diagnóstico bruto para análise seja a melhor opção ao meu ver do que podá-lo com IA — mesmo que os registros mostrem as alterações não vejo o impacto que isso causaria diferente do natural.

```text
Pergunta feita: Pedi para a IA agir como revisora e analisar as respostas que eu já tinha escrito, de forma crua, para entender onde eu estava errando conceitualmente.
Resumo da resposta: A IA me mostrou que a minha lógica de navegação algorítmica (como em autômatos) estava ótima, mas que eu havia confundido as nomenclaturas teóricas na Seção 2 (misturando a Teoria Geral com a Máquina de Turing) e errado a geração das cadeias na Seção 5 (esquecendo de substituir a variável temporária 'S' no resultado final).
Como eu verifiquei: Li a análise da IA confrontando com as definições teóricas que acabei não lembrando de primeira.
O que eu alterei na minha resposta: Inicialmente, eu ia manter o diagnóstico "bruto" com meus erros para mostrar minha intuição original. Porém, ao ler os critérios de avaliação (que cobram pontuação pela correção dos conceitos), refiz as definições da Seção 2, as linguagens da Seção 3 e as cadeias da Seção 5 com base no que aprendi agora na revisão com a IA (marcadas com "Corrigido com Revisão"), garantindo a precisão técnica sem perder a honestidade do meu relato de dúvida (como mantive na questão 3.4).
O que ainda não entendi: Ainda preciso de prática para desvincular a lógica de programação prática que eu uso do rigor matemático cobrado na Teoria da Computação.
```


## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório: https://github.com/frndchagas-org/diagn-stico-de-retomada-teoria-da-computa-o-EriiSy/
Commit final: revisão de conceitos e atualização da autoavaliação
Autoavaliação: nível básico para o intermediário, maior dificuldade: conceitos e terminologias por extenso  e tópico que precisa ser retomado:  Hierarquia de Chomsky e Classes.
```
