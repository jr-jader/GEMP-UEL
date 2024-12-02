# Laços de Repetição

Vamos explorar os **laços de repetição**, ferramentas fundamentais para executar blocos de código múltiplas vezes de maneira eficiente. Imagine que você precisa verificar se algum número de uma lista possui o valor 50. Sem laços, podemos fazer isso assim:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    int a, b, c, d, e;
    cin >> a >> b >> c >> d >> e;

    if (a == 50 || b == 50 || c == 50 || d == 50 || e == 50)
        cout << "Algum número é igual a 50" << endl;
    else
        cout << "Nenhum número é igual a 50" << endl;
}
```

Embora funcional, este método se torna inviável para verificar dezenas, centenas ou milhares de números. Para isso, usamos laços de repetição, que permitem repetir um bloco de código até que uma condição seja satisfeita.

Em C++, os laços disponíveis são **for,** **while**, e **do-while.** Vamos detalhar cada um deles com exemplos práticos.

## For

O comando for é especialmente útil quando o número de repetições é conhecido previamente. Sua estrutura básica é:

```c++
    for (iniciação; condição; incremento) {
    // código a ser executado
}
```

Um pouco confuso? Nem tanto. Ele sempre será mais ou menos assim:

```c++
    for (int i = 0; i < 5; i++) {
    cout << "Iteração: " << i << endl;
}
```

No exemplo acima:

- A variável i é inicializada como 0.
- O laço verifica se a condição i < 5 é verdadeira.
- Se a condição for verdadeira, o bloco de código dentro do laço é executado.
- Após a execução, o valor de i é incrementado.
- O processo se repete até que i seja maior ou igual a 5.

Vamos refazer o exemplo da verificação de números, agora com um laço **for**:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    bool encontrado = false;

    for (int i = 0; i < 5; i++) {
        int numero;
        cin >> numero;

        if (numero == 50) {
            encontrado = true;
        }
    }

    if (encontrado)
        cout << "Algum número é igual a 50" << endl;
    else
        cout << "Nenhum número é igual a 50" << endl;
}

```

Agora, se quisermos aumentar o limite de variáveis lidas para 10, 100 ou 1 milhão, é bem simples, pois apenas aumentamos o valor dentro da condição do for.

## Controle de Fluxo nos laços

Além do return, que encerra um programa, podemos usar dois comandos importantes dentro de laços:

### break;

Interrompe o laço imediatamente, independentemente de quantas iterações ainda restam.

```c++
   for (int i = 0; i < 5; i++) {
    int x;
    cin >> x;
    if (x == 10) {
        break; // Sai do laço assim que encontramos o valor 10
    }
}
```

### continue;

Faz o laço "pular" para a próxima iteração, ignorando os comandos restantes na iteração atual.

```c++
 for (int i = 0; i < 5; i++) {
    if (i == 2) {
        continue; // Pula a iteração quando i == 2
    }
    cout << i << " ";
}
// Saída: 0 1 3 4
```

## While

O **while** é outra estrutura de repetição, adequada quando o número de iterações não é conhecido de antemão. A lógica é simples: **enquanto** uma condição for verdadeira, o código dentro do laço será executado.

```c++
    while (condicao_for_verdadeira) {
        // comandos
        ...
    }
```

Abaixo, aquele mesmo exemplo de checar se temos um número 10 como entrada, agora usando while:

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    bool encontrado = false;
    int i = 0;

    while (i < 5) {
        int x;
        cin >> x;
        if (x == 10) {
            encontrado = true;
        }
        i++;
    }

    if (encontrado)
        cout << "Algum deles vale 10";
    else
        cout << "Nenhum deles vale 10";
}

```

## Do While

Diferente do **while**, o **do-while** garante que o código será executado pelo menos uma vez, já que a condição é verificada **após** a execução.

```c++
    do {
        // comandos
    } while (condicao_existencia);  
```

Mais uma vez, reescrevemos nosso problema utilizando **do-while**:


```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    bool encontrado = false;
    int i = 0;

    do {
        int x;
        cin >> x;
        if (x == 10) {
            encontrado = true;
        }
        i++;
    } while (i < 5);

    if (encontrado)
        cout << "Algum deles vale 10";
    else
        cout << "Nenhum deles vale 10";
}

```

Pratique alterando os exemplos e experimente criar suas próprias variações! Laços de repetição são bem simples mas essenciais em praticamente todo programa.
