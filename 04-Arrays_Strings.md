# Vetores, Matrizes e Strings

# Vetores

Os **vetores** (ou arrays) são estruturas que permitem armazenar múltiplas variáveis do mesmo tipo, utilizando uma única referência. Eles são úteis quando precisamos lidar com coleções de dados que compartilham um contexto similar, como uma lista de números.

Um vetor pode ser representado assim:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    int tamanho = 7;
    int notas[tamanho]; // Declaração do vetor

    // Leitura dos valores do vetor
    for (int i = 0; i < tamanho; i++) {
        cout << "Digite a nota " << i + 1 << ": ";
        cin >> notas[i];
    }

    // Impressão dos valores armazenados
    cout << "As notas digitadas foram: ";
    for (int i = 0; i < tamanho; i++) {
        cout << notas[i] << " ";
    }
    cout << endl;

    return 0;
}
```

Neste caso, estamos lendo 7 valores que representam notas de alunos e armazenando-os no vetor `notas`. Cada posição do vetor pode ser acessada utilizando índices de 0 a `tamanho - 1`. Por exemplo, para acessar a terceira nota, utilizamos `notas[2]`.

Também é possível inicializar um array com valores, da seguinte forma:

```c++

#include <bits/stdc++.h>
using namespace std;

int main() {
    int cores[5] = {10, 20, 30, 40, 50};

    for (int i = 0; i < 5; i++) {
        cout << "Cor " << i + 1 << ": " << cores[i] << endl;
    }

    return 0;
}

```




O array acima pode ser representado da assim:

| Índice: | cores[0] | cores[1] | cores[2] | cores[3] | cores[4] |
| :----: | :----: | :----: | :----: | :----: | :----: |
| Valor: |   10   |   20   |   30   |   40   |   50   |

# Matrizes

As **matrizes** são vetores 2D, organizados em linhas e colunas. Elas são úteis para modelar tabelas, grades e outras estruturas bidimensionais.

O exemplo abaixo demonstra o uso de uma matriz para armazenar as vendas de três produtos em quatro meses:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    int produtos = 3;
    int meses = 4;
    int vendas[produtos][meses];

    // Leitura dos valores da matriz
    for (int i = 0; i < produtos; i++) {
        for (int j = 0; j < meses; j++) {
            cout << "Digite as vendas do produto " << i + 1 << " no mes " << j + 1 << ": ";
            cin >> vendas[i][j];
        }
    }

    // Impressão da matriz
    cout << "Vendas registradas:\n";
    for (int i = 0; i < produtos; i++) {
        for (int j = 0; j < meses; j++) {
            cout << vendas[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

Também é possível inicializar uma matriz com valores, da seguinte forma:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    int mat[2][3] = {{1, 2, 3}, {4, 5, 6}};

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            cout << mat[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}

```

A matriz acima pode ser representada assim:

|  Índice  | mat[][0] | mat[][1] | mat[][2] |
| :------: | :------: | :------: | :------: |
| mat[0][] |    1    |    2    |    3    |
| mat[1][] |    4    |    5    |    6    |


# Variáveis globais, locais e *lixo*

Até agora, todas as nossas variáveis foram declaradas dentro da função main. No entanto, também é possível declará-las fora dela. O uso de variáveis globais será mais útil mais adiante, especialmente quando abordarmos funções. Por ora, vamos explorar apenas uma vantagem de utilizar variáveis globais. Antes disso, precisamos entender o que significa lixo em C/C++.

Quando criamos uma variável sem atribuir um valor inicial, o espaço de memória reservado para ela pode conter qualquer valor. Mas o que isso significa? Quando uma variável é criada, o sistema reserva um espaço na memória para ela. No entanto, esse espaço pode ter sido usado anteriormente, e os dados antigos (representados por combinações de 0s e 1s) podem ainda estar presentes. Em vez de apagá-los, o computador simplesmente sobrescreve esses valores quando necessário.

Se isso ainda parecer confuso, você pode experimentar com um exemplo prático. Crie um programa da seguinte forma:

```c++
    #include <bits/stdc++.h>
    using namespace std;
  
    int main() {
        int x;
        cout << x << endl;
    }
```

Execute o programa várias vezes e observe os valores que a variável x assume. Esses valores diferentes indicam que, a cada execução, uma posição de memória distinta é utilizada e que, nessa posição, havia um valor "lixo".

Por outro lado, ao criar variáveis globais, além de poderem ser acessadas em qualquer parte do código (voltaremos a falar disso ao abordar funções), elas já são inicializadas automaticamente com zero. Isso pode ser bastante útil em diversas situações.

```c++
    #include <bits/stdc++.h>
    using namespace std;

    int vet_global[15]; //variavel global, array de tamanho 15 de inteiros.

    int main() {
        int vet_local[15];
        for (int i = 0; i < 15; i++) printf("%d ", vet_local[i]);
        // no meu computador, foram printados esses valores: 0 0 8 0 1 0 -1477321288 32764 -1477321272 32764 9 0 0 0 4839111

        //variavel global:
        for (int i = 0; i < 15; i++) printf("%d ", vet_global[i]);
        // no meu computador, foram printados esses valores: 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
    }
```
É importante destacar, no entanto, que embora o uso de variáveis globais seja bastante útil em programação competitiva, essa prática é amplamente desencorajada na programação convencional. Em projetos maiores, com muitos arquivos, variáveis e funções (sim, prometo que falaremos bastante sobre elas em breve), o uso excessivo de variáveis globais pode levar a problemas como conflitos de nomes ou dificuldade de manutenção do código.

Portanto, em contests e exercícios competitivos, você pode usar e abusar das variáveis globais para ganhar tempo e simplicidade. Mas, ao trabalhar em projetos mais estruturados, como os das aulas de ICC, prefira alternativas mais organizadas, como variáveis locais e estruturas bem definidas.

# Strings

Strings são basicamente arrays de caracteres, sendo utilizadas para representar palavras ou frases. Em C, não existe um tipo nativo chamado string, então é necessário trabalhar diretamente com vetores de caracteres ou incluir a biblioteca string.h para facilitar algumas operações. Já em C++, contamos com o tipo string, que é uma abstração mais poderosa e fácil de usar para manipular textos.

No código abaixo podemos ver como se faz leitura e escrita de palavras:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string nome;

    cout << "Digite seu nome: ";
    cin >> nome;

    cout << "Olá, " << nome << "!" << endl;

    return 0;
}
```

Para ler frases ou qualquer string que contenha espaços, em C++ utilizamos a função getline(). Diferente do cin >>, que só lê até o primeiro espaço, a função getline() lê toda a linha de entrada, incluindo os espaços, até o final da linha.

A sintaxe para utilizá-la é a seguinte:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string frase;

    cout << "Digite uma frase: ";
    getline(cin, frase);

    cout << "Você digitou: " << frase << endl;

    return 0;
}
```

Uma coisa interessante é que em C++ podemos "somar" strings. Essa operação concatena strings, ou seja, se somarmos as strings a e b (a + b), adicionaremos a string b ao final de a. O exemplo abaixo mostra essa operação:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string saudacao = "Bom ";
    string parteDoDia = "dia!";
    string mensagem = saudacao + parteDoDia;

    cout << mensagem << endl; // Saída: Bom dia!

    return 0;
}
```

Também é possível acessar uma string da mesma forma que vimos para arrays, isto é, utilizando [] para termos o valor de uma certa posição, que no caso da string é uma letra. Para fazer isso, geralmente é preciso utilizar a função size(), que retorna o tamanho da string. No código abaixo lemos uma string e imprimimos uma letra em cada linha.

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string palavra;
    cout << "Digite uma palavra: ";
    cin >> palavra;

    for (int i = 0; i < palavra.size(); i++) {
        cout << "Letra " << i + 1 << ": " << palavra[i] << endl;
    }

    return 0;
}
```
Existem muitas funções úteis para manipular strings, como encontrar substrings, comparar, e transformar caracteres. Esses conceitos serão explorados em detalhes em aulas futuras.
