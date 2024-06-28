# Guia Inicial para Programação Competitiva

> "Diante de um desafio de programação já conhecido, a meta é resolvê-lo no menor tempo possível."

A programação competitiva é fundamentada em uma variedade de técnicas e algoritmos. Além de dominá-los, a prática constante é essencial para reduzir o tempo gasto em cada desafio.

## Elementos-chave de um problema

Ok, você está prestes a resolver um problema. Para se familiarizar melhor com eles, aqui está um resumo de como eles geralmente são estruturados. Normalmente, os problemas são apresentados da seguinte maneira:

1. **Título do Problema:** Na maioria das vezes, é apenas um título, sem influência direta no problema. No entanto, ocasionalmente, ele pode fornecer uma dica para a solução (apresentando alguma *tag*, etc.)
2. **Contexto do Problema:** Semelhante ao que acontece em exames vestibulares. Uma história criada apenas para dar sentido ao problema - e que, assim como em matemática, o que realmente importa está escondido nela. Portanto, é sempre importante ler o enunciado para entender o que deve ser feito.
3. **Restrições:** Embora isso possa não fazer muito sentido agora, você verá mais adiante que isso é muito importante. As restrições de um problema representam o intervalo que os valores de entrada podem ter. Isso limitará a complexidade do algoritmo que você desenvolverá, ou o tipo de variável que você deve usar.
4. **Casos de Teste de Exemplo:** Suponha que você leu o enunciado e tem uma ideia do que fazer. Então, você vê os casos de teste de exemplo. Eles fornecerão um exemplo de valores de entrada, seguido pela saída esperada pelo problema.
5. **Explicação dos Casos de Teste:** Em alguns problemas, também é possível que os casos de teste sejam explicados, para facilitar a compreensão do problema.

## Problema básico exemplificado

Aqui está um exemplo simples de problema:

| Jader no Zerão  |
| ---------------- |
| Tempo limite: 1s |

Jader adora passear. Sempre que pode, ele vai ao Zerão nos finais de semana. Agora ele quer contar aos seus amigos a quantidade *k* de aves que ele observou em seu último passeio. Seja *n* (0 < n < 100) o número de pombos que Jader viu no sábado e *m* (0 < m < 100) o número de urubus que ele viu no domingo, determine a quantidade *k* de aves observadas.

**Entrada**
A primeira linha contém dois inteiros *n* e *m* (a quantidade de aves observadas).

**Saída**
Seu programa deve apresentar um único inteiro *k*, o total de aves.

**Exemplo**

```
Entrada:
3 4

Saída:
7
```

Provavelmente, você percebeu que a solução deste problema é simplesmente somar os dois valores de entrada. Nele, podemos observar as situações que destaquei acima: o título do problema *(que realmente não ajuda na solução em si)*; o contexto *(que tem muita informação desnecessária, mas é nele que o problema está descrito)*. Neste caso, as restrições são dadas também no enunciado (tanto *n* quanto *m* são valores inteiros entre 1 e 99, inclusive), isso nos ajuda a escolher os tipos de variáveis que vamos utilizar; e a restrição de tempo do problema é 1 segundo - ou seja, a execução do seu problema não pode ultrapassar 1 segundo - vamos ver mais adiante como saber se seu programa será executado dentro do tempo limite.

## Introdução à Programação em C++

Se você já tem familiaridade com alguma linguagem de programação *(c, python, pascal)*, não será tão difícil aprender os conceitos básicos de C++. Em C++, você pode usar tudo que se usa em *c* (por exemplo, posso pegar um programa em C e compilá-lo em C++ sem problemas).

### Estrutura do Código em C++

```c++
#include <iostream> //incluindo biblioteca que possui alguma função que eu quero

int main() { //funcao principal, a primeira a ser executada em seu codigo
    return 0; //retorno da funcao (opcional)
}

```

## Introdução à Complexidade

Em geral, os computadores convencionais conseguem executar aproximadamente 400 milhões de comandos por segundo. Aqui é onde as restrições do problema se tornam úteis. No exemplo anterior, o valor de *n* estava limitado a, no máximo, 100. Isso significa que poderíamos usar um laço de repetição ( *for* ) indo de 0 até *n* sem problemas, pois seriam executados apenas cerca de 100 comandos. No entanto, se o valor de *n* pudesse chegar a 10^9, isso não seria viável, pois ultrapassaria o limite de tempo. Mais adiante, estudaremos métodos para analisar a complexidade de cada código. Por enquanto, é bom ter algumas noções.

1. **Complexidade constante (O(1))** : Isso significa que o tempo de execução não depende do tamanho do problema. Por exemplo, se você está apenas somando dois números, independentemente do tamanho desses números, a operação é rápida e constante.

   Imagine que você tem uma calculadora e quer somar dois números. Independentemente de quão grandes ou pequenos esses números sejam, você só precisa fazer uma operação de adição. Isso é uma complexidade constante.

   **Exemplo**: Acesso direto a um elemento em um array (por índice) é **O(1)**, porque não importa o tamanho do array, a operação é rápida.
2. **Complexidade linear (O(n))** : Quando você tem um loop que executa de 0 até  *n* , a complexidade é linear. Quanto maior o valor de  *n* , mais tempo levará para executar o loop.

   Imagine que você está contando o número de elementos em uma lista. Se você percorrer cada elemento da lista uma vez, a quantidade de operações que você faz é proporcional ao tamanho da lista, certo? Isso é uma complexidade linear, ou seja, O(n).

   **Exemplo:** Para encontrar o maior número em uma lista de n elementos, você precisa comparar cada elemento com o maior número encontrado até agora. Isso requer n comparações, portanto, a complexidade é O(n).
3. **Complexidade quadrática (O(n^2))** : Se você tem dois loops aninhados, ambos indo de 0 até  *n* , a complexidade é quadrática. Isso significa que o tempo de execução aumenta rapidamente à medida que *n* cresce.

   Agora, pense em uma matriz bidimensional (uma tabela). Se você percorrer cada linha e, para cada linha, percorrer cada coluna, você está fazendo n operações para cada uma das n linhas. Isso resulta em n^2 operações no total.

   **Exemplo:** Verificar se há duplicatas em uma lista comparando todos os pares de elementos requer um loop dentro de outro, resultando em complexidade O(n^2).

Essa parte de complexidade não é tão imposta no início, e será revista mais tarde, então se você não entendeu isso agora, não se preocupe: o seu "eu" do futuro se preocupará com isso.

## Respostas dos Judges

Após submeter seu código, você pode receber alguma resposta do site em que mandou:

1. **Accepted (AC)** : Sua solução estava correta e foi aceita pelo juiz.
2. **Wrong Answer (WA)** : Sua solução produziu uma saída diferente da esperada. Pode ser um erro lógico ou de implementação.
3. **Time Limit Exceeded (TLE)** : Seu programa demorou mais tempo do que o limite permitido para executar. Isso geralmente ocorre quando a solução não é otimizada.
4. **Memory Limit Exceeded (MLE)** : Seu programa está usando mais memória do que o permitido. Isso pode acontecer se você alocar muita memória ou usar estruturas de dados ineficientes.
5. **Runtime Error (RTE)** : Seu programa encontrou um erro durante a execução, como um acesso indevido à memória ou uma divisão por zero.
6. **Presentation Error** : Alguns juízes consideram isso quando a formatação da saída não está exatamente como esperado.

---

## Referências

### Sites para aprender

É sempre bom ler sobre algoritmos em diferentes sites, para ter diferentes perspectivas sobre um tópico. Entre estes sites, recomendamos:

#### Em português

[Beecrowd](https://beecrowd.com/pt/)
[Neps Academy](https://neps.academy/login?next=%2F)

#### GitHub

[GitHub do Fakhoury](https://github.com/andrefakhoury)
[GitHub do Forbes](https://github.com/VictorXjoeY)
[GitHub do LoppA](https://github.com/LoppA)
[GitHub da lmoura](https://github.com/lusmoura)
[GitHub do Preischadt](https://github.com/thiagop-usp)
[GitHub do David](https://github.com/davidcairuz)
[Github do Turci](https://github.com/lucasturci)

#### Em inglês

[Geeks for Geeks](https://www.geeksforgeeks.org/)
[HackerRank](https://www.hackerrank.com/)
[HackerEarth](https://www.hackerearth.com/)
[CP-Algorithms](https://cp-algorithms.com/)
Canal do [Errichto](https://www.youtube.com/channel/UCBr_Fu6q9iHYQCh13jmpbrg) no youtube
Canal do [Abdul Bari](https://www.youtube.com/channel/UCZCFT11CWBi3MHNlGf019nw/) no youtube
Canal do [Tushar Roy](https://www.youtube.com/user/tusharroy2525) no youtubeSites para competir

Depois de adquirir alguma familiaridade com programação competitiva, você pode começar a treinar e competir. Existem vários sites que oferecem problemas para resolver, e alguns realizam campeonatos periodicamente, atribuindo uma pontuação ( *rating* ) com base nas soluções dos problemas. Na minha opinião, alguns dos melhores sites são:

[Codeforces](https://www.codeforces.com)
[Codechef](https://www.codechef.com)
[SPOJ](https://www.spoj.com)
[TopCoder](https://www.topcoder.com)
[CsAcademy](https://www.csacademy.com)
[UVA](https://uva.onlinejudge.org/)
[URI](https://www.urionlinejudge.com.br)

### Livro de programação competitiva

Para aqueles que estão aprendendo algoritmos e técnicas para maratonas de programação, o livro mais utilizado é o  **Competitive Programming 3** , escrito por Steven e Felix Halim. O livro oferece excelentes explicações e exemplos de código em C++, além de recomendar diversos problemas para cada tópico estudado.

Os problemas recomendados estão disponíveis no [UVA](https://uva.onlinejudge.org/), um dos sites mencionados anteriormente. Você pode acompanhar seu progresso na resolução de cada tópico usando o [uHunt](https://uhunt.onlinejudge.org/).

Uma ótima abordagem é combinar o estudo desse livro com outros recursos, como já mencionado anteriormente. Ter diferentes perspectivas sobre um mesmo tópico é fundamental.

### Acompanhando seu progresso

Após resolver problemas em alguns dos online judges mencionados anteriormente, talvez você queira ter uma visão geral do seu progresso. Para isso, existem sites que reúnem informações, exibem gráficos e listam os problemas que você já resolveu. Alguns desses sites são:

[StopStalk](https://www.stopstalk.com/): Reúne dados dos online judges mais famosos, mostra um heatmap de atividade, lista todos os problemas resolvidos e permite que você acompanhe seus amigos.

[Codeforces Visualizer](https://cfviz.netlify.com/): Foca especificamente no Codeforces e oferece informações detalhadas sobre seus problemas resolvidos.

Esses sites podem ser uma ótima fonte de motivação. Vale a pena conferir!
