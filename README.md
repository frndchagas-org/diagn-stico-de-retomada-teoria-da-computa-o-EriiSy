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

1. O que é um alfabeto? Temos dois tipos de alfabetos: O de entrada {0,1,#} que é o que o usuário pode dar "input", enquanto o Alfabeto Universal/Fita — é o que a máquina poderá usar no processo. {0,1,#, Vazio,x}
2. O que é uma cadeia? Uma sequência finita de combinações possíveis baseada em um alfabeto `beta = {x,y}` 
3. O que é uma linguagem? É as regras que regem esses alfabetos
4. O que é uma gramática? É o universo do automato finito regido : alfabetos, cadeia e linguagem 

## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:

1. escreva três palavras que pertencem à linguagem;
   R: L1 {0,1,w}
   R: L2 {a,b,ab} 
   R: L3 {a,b,c,ab,ac,abc}
3. escreva duas palavras que não pertencem;
   R: L1 {2w,02} 
   R: L2 {lac,lbc} 
   R: L3 {ah,bh,ch} 
5. diga, se souber, em qual classe ela provavelmente se encaixa;
   R: Se eu soubesse...provavelmente ela seria probabilistico
6. explique o motivo em linguagem simples.
   R: Possivelmente o motivo a ser explicado se eu soubesse... seria pela capacidade de realizar diversas combinações sem necessariamente rejeitar ou confirmar mas apenas tratar como parte das sequencias finitas.

Não há problema em dizer "não sei". Nesse caso, escreva o que te deixou em dúvida.

O que me deixou em duvida foi o fato de escrever o resultado do que a linguagem pertence ou não sem saber se está ligeiramente correto as nomenclaturas

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

1. Qual linguagem esse autômato parece reconhecer?
   R: Aparentemente : L = { 1^n + 1^n | n > 0 }
3. Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:
Considerando que o "rejeita" será quando não se encontra no estado final então: 
   - `01` - Aceita (q0 -> q1 -> q2)
   - `101` - Aceita (q0 -> q0 -> q1 -> q2) 
   - `100` - Rejeita (q0 -> q0 -> q1 -> q1) 
   - `1101` - Aceita (q0 -> q0 -> q0 -> q1 -> q2)
   - `111` - Rejeita (q0 -> q0 -> q0 )
4. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.

          |  0 |  1 |          
        q0| q0 | q1 |  
        q1| q1 | q2 | 
        q2| q1 | q0 | 

        
## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. Gere cinco cadeias produzidas por essa gramática.
  R: {aS, aSaS, b, bb, aSaSaSaS, bbbb, aSaSaS, bbb}
3. Descreva a linguagem em palavras.
  R: Não sei explicar, talvez : Linguagem = { aS em {b} | b = aS } 
4. Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.
   Parece livre de contexto, não há um padrão que defina limites ou regras especificas para aceitar ou rejeitar. 
## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva:

1. o que você entende dele; 
   R: A função de transição na máquina de turing quando esta um produto de base 2 ao invés de fazer um somatório (não mais unário) acredito que consigo explicar,pois se na função de transição {⊔,1,1,#,1,0,⊔} ele irá rodar um looping de estados que irá transitar (no mais otimizado possível) 15 passos até finalizar a lista para que chegue em {⊔,1,0,#,X,X,⊔} considerando que a fita é {0,1,#,⊔,x} e que onde o X está colocado ele já indica para o estado qAtual que já passou por ali e pode se encaminhar para a direita e tornar o próximo valor unitário 1 em X até finalizar ( o looping).
2. onde você se confunde;
   R: Normalmente me confundo e tenho dificuldade com as terminologias e conseguir integrar ela diretamente ao conteúdo, contudo, passos lógicos e heuristicos acabam fixando com mais facilidade
3. que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta.
   Sou um aluno que normalmente bate dias ou horas tentando entender uma questão e dissecando-a e através disso aprendendo conteúdos, desta forma, em caso de explicações a didática em formas de exercício guiado e/ou desenhos e analogia ajudariam muito o saber. 

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:

O que ligeiramente fiz foi utilizar a IA para entender o que eu errei aqui nessa atividade, porém não pretendo mudar as respostas pois, de certo modo apenas estarei justificando silenciosamento para mim mesmo que "devo ter aprendido" enquanto na verdade, deixar esse diagnóstico bruto para análise seja a melhor opção ao meu ver do que podá-lo com IA — mesmo que os registros mostrem as alterações não vejo o impacto que isso causaria diferente do natural.

```text
Pergunta feita: Pedi para a IA agir como revisora e analisar as respostas que eu já tinha escrito para entender onde estava errando.
Resumo da resposta: A IA me mostrou que minha lógica de navegação (autômatos) é muito forte, mas que eu confundi as nomenclaturas teóricas (ex: achar que um alfabeto precisa ser só de entrada/fita, ou que o 'S' maiúsculo fica na cadeia final da gramática).
Como eu verifiquei: Li a análise confrontando com as definições teóricas que acabei não lembrando de primeira.
O que eu alterei na minha resposta: Absolutamente nada. Mantive o diagnóstico bruto. Preferi deixar os meus erros e a minha intuição original intactos para a análise real do professor, em vez de "podar" o teste com as correções que aprendi agora.
O que ainda não entendi: Ainda preciso me acostumar a desvincular a lógica de programação prática (que eu domino) do "juridiquês" formal da matemática discreta.
```


## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório: https://github.com/frndchagas-org/diagn-stico-de-retomada-teoria-da-computa-o-EriiSy/
Commit final: Atividade_Revisao_01
Autoavaliação: nível básico para o intermediário, maior dificuldade: conceitos e terminologias por extenso  e tópico que precisa ser retomado:  Hierarquia de Chomsky e Classes.
```
