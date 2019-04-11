---
layout: post
title:  "n+1, n++ e ++n, qual usar?"
date:   2019-04-04 20:00:00 -0300
categories: jekyll update
---

Essa é uma dúvida muito comum no início do estudo de uma linguagem de programação. Afinal, **qual a diferença entre n+1, n++ e ++n?** 

Bom, para começar analise o código a seguir e tente adivinhar o que ele irá imprimir:

```c++
#include<bits/stdc++.h>
using namespace std;

int main() {
    int n = 10;
    cout <<n+1 <<endl;
    cout <<n++ <<endl;
    cout <<++n <<endl;
}
```

Quais números ele irá imprimir?

- 11, 12, 13
- 11, 10, 12
- 11, 12, 13
- 10, 10, 10

Antes de continuar tente pensar na resposta.

*Pense...*

*Pense...*

*Pronto? Beleza!*

A resposta certa são os números... *suspense*... 11, 10, 12 !!!

É estranho, mas vamos entender o que significa cada coisa:

- **n+1:** simplesmente estamos pegando o valor de `n` e adicionando 1, mas atenção: não estamos alterando o valor de `n`! A única coisa que fazemos é utilizar o valor armazenado na variável `n`. 

  Caso o objetivo seja acrescentar 1 em `n`, precisamos escrever `n = n+1`, ou seja, atribua a `n` o valor de `n+1`.

- **n++:** é o mesmo que escrever `n = n+1`, ou seja, estamos adicionando 1 à variável `n`. Em caso de utilização de `n` durante o esse incremento, primeiro é utilizado o valor de `n` e depois ele é incrementado.

- **++n:** é o mesmo que escrever `n = n+1`, ou seja, estamos adicionando 1 à variável `n`. Em caso de utilização de `n` durante o esse incremento, primeiro é incrementado o valor de `n` e depois ele é utilizado.

No caso do `cout <<n++`, o que realmente acontece é que primeiro é impresso o valor de `n` e depois ocorre o incremento. Em `cout <<++n` é o contrário, primeiro ocorre o incremento e depois é impresso o valor de `n` (já incrementado em 1 unidade).

Valor de `n` linha por linha:

```c++
#include<bits/stdc++.h>
using namespace std;

int main() {
    int n = 10;
    // n = 10
    cout <<n+1 <<endl; // n = 10
    // n = 10
    cout <<n++ <<endl; // n = 10
    // n = 11
    cout <<++n <<endl; // n = 12
    // n = 12
}
```