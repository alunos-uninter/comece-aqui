# Funções com Kotlin
* Nosso objetivo neste tutorial, é demonstrar as capacidades do kotlin, relacionado a funções.
* O Pré-requisito para este tutorial é ter seguido o material anterior a esse o Introdução ao Kotlin.
* Também é necessário que você crie um novo arquivo kotlin no Intellij IDEA para que você possa praticar com nossos exemplos.
———
## Funções sem retorno.
* No tutorial anterior, já vimos como podemos criar funções simples, que não pedem argumentos nem retornam valores, ainda assim, vamos fazer uma revisão.
* Lembre-se para declarar uma função vamos usar a palavra `fun`.
* Vamos criar uma função chamada clear, nela vamos imprimir 30 vezes as linhas em branco, para poder limpar a tela do nosso terminal.
```Kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    for (i in 0..30) {
        println(i)
    }
}

fun clear() {
    for (_ in 0..30) {
        println()
    }
}
```

* Quando quisermos chamar a função clear, basta colocar em uma linha e colocar os parênteses após o nome `clear()`, como por exemplo:

```Kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    for (i in 0..30) {
        println(i)
    }
    clear()
}

fun clear() {
    for (_ in 0..30) {
        println()
    }
}
```

## Funções que pedem argumentos
* Argumentos, são constantes que pedimos o valor no momento em que chamamos a função.
*  Para declarar elas, não será necessário usar o comando val, e também devemos nos atentar que elas devem ser colocados dentro dos (), no momento da declaração da função.
*  Vamos criar uma função que diz olá, para o usuário, e que varia de acordo com o valor recebido.
```kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    Ola(“Felipe”)
    Ola(“Samantha”)
    Ola(“Denis”)
}

fun Ola(nome: String) {
    println(“Olá, $nome”)
}
```
* Ao declaramos um parâmetro, sempre teremos `nome: Tipo`.

* Note também que não é possível alterar o valor recebido como parâmetro dentro da função, caso deseje, o ideal é criar uma segunda variável dentro do corpo da função que receba o valor do parâmetro.
## Funções com retorno
* Imagine que estamos precisando criar uma função que calcule a área de um triângulo. Baseado na base e na altura recebidos como parâmetros, e devemos retornar o resultado da operação.
>[!Important]
> Fórmula da área do triângulo, A = (B * H) / 2

* Para colocar um retorno, devemos colocar o tipo que nossa função retornará na sua declaração. Para isso podemos fazer da seguinte maneira: `fun exemplo(): Int {}`, sim exatamente como quando colocamos o tipo de maneira explícita em uma variável.
* Dentro do corpo da função quando quisermos finalizar a execução da função podemos usar o comando `return`, quando nossa função tiver um tipo de retorno definido explicitamente, o Kotlin nos obrigará a retornar um valor.
* Vamos implementar a função de cálculo da área do triângulo para clarificar esses conceitos.

```kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    val area: Double = AreaDoTriangulo(25.0, 30.0)
    println(“Área calculada foi de $area”)
}

fun AreaDoTriangulo(base: Double, altura: Double): Double{
    val area: Double = (base * altura) / 2
    return area
}
```
* Como você pode ver nossa função recebe dois parâmetros double e retorna um valor double.
* Um outro ponto, quando estamos chamando uma função podemos colocar o nome explicito do parâmetro para facilitar a leitura, veja o exemplo:
```kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    val area: Double = AreaDoTriangulo(base= 25.0, altura= 30.0)
    println(“Área calculada foi de $area”)
}

fun AreaDoTriangulo(base: Double, altura: Double): Double{
    val area: Double = (base * altura) / 2
    return area
}
```
## Funções com retorno, simplificado:
* Esse tipo de função é com retorno também, porém, vamos trabalhar com uma abordagem mais funcional.
* nela vamos substituir o bloco de código {}, pelo símbolo de =. Neste caso nossa função só pode ter uma linha, e sem o comando return.
```kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    val area: Double = AreaDoTriangulo(25.0, 30.0)
    println(“Área calculada foi de $area”)
}

fun AreaDoTriangulo(base: Double, altura: Double) = (base * altura) / 2
```
* como você pode ver, nossa função foi bastante simplificada.
* a variável val area, foi removida, o bloco de código e o comando return foram simplificados pelo operador =, que agora já diz ao compilador que a frente temos um retorno baseado em uma formula.
* Se você pensar, esse tipo de declaração se assemelha a matemática.
---
* Isso cobre o básico das funções em Kotlin, como declarar, parâmetro e retorno.
* Agora vamos começar a trabalhar com alguns tópicos mais complexos.
---
## Funções de extensão
* Imagine que vamos precisar construir uma função que formate um valor Float, para que ele seja retornado em Reais, com o seguinte formato R$ XXXX,xx;
* Como nós sempre vamos usar um valor float como parâmetro, podemos então adotar a abordagem de função de extensão. Veja como funciona declarar esse tipo de função:
```kotlin
package net.felipealafy.kotlin_introduction

//Main code …

fun Float.formatoMoeda(): String {
    //Note que trocamos um parâmetro pelo Float. <- Isso diz ao compilador que estamos criando uma função que só pode ser aplicada a valores Float.
    return “R$ %.2F”.format(this) //Note que no lugar de usar o nome do parâmetro como em uma função convencional, aqui vamos usar o comando `this`, que substitui o nome.
}
```
* Alguns pontos importantes a notar, se você alguma vez já trabalhou com Go Lang você deve ter se lembrado das `reciver functions`, em kotlin as funções de extensão são parecidas, porém em kotlin elas podem fazer parte de qualquer tipo, incluindo nossas próprias classes e tipos.
* agora vamos ver como chamar esse tipo de função
```kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    val valor: Float = 15.76342F
    println(valor.formatoMoeda())
}
//Função de extensão…
``` 
* como você pode ver, a maneira de chamar é usando o `.`como ligação entre o valor e a função. Exatamente como acontece com `””.format()`

>[!Important]
> Nem sempre, que vemos uma função nesse estilo valor.funcao(), em kotlin, quer dizer que por trás há uma função de extensão, pois como veremos em orientação a objetos, métodos são outra maneira de criar funções que tem essa sintaxe.
---
## Passando uma função para dentro de outra função (High Order Functions)
* Muitas vezes, em desenvolvimento Android você vai se deparar com uma função que cria um componente na tela e que pede uma função como parâmetro teremos que aprender a como manejar essas funções e declarar.
* A razão do Android pedir esse tipo de parâmetro, é porque é necessário que o componente execute uma serie de comandos personalizados, a decorrer da ação do usuário.
* Para isso precisamos compreender, como o podemos criar uma função que pede uma função. No Kotlin, temos uma sintaxe bem simples, no primeiro passo, vamos dar um nome como para um parâmetro comum, porém a diferença está no tipo que vamos passar.
```kotlin
package net.felipealafy.kotlin_introduction

//main…

fun menu(operacao: (Int, Int) -> Int) {
    println(“======== Menu =========”)
    println(“Eu vou executar a operação que eu recebi como parâmetro”)
    println(“O resultado foi ${operacao(5, 10)}”)
}
```
* Note, que criamos um parâmetro que obriga, nossa chamada dentro da função menu, a passar dois parâmetros numéricos. E também diz que ela retornara um valor Int por fim.
* Mas você deve estar estranho, porque eu estou criando uma função dentro  do argumento de outra função?
* O que acontece na prática é que dividimos o bloco de código da declaração. Isso porque como veremos abaixo, o bloco de código agora será definido no momento da chamada da função, veja:

```kotlin
package net.felipealafy.kotlin_introduction

fun main() {
    menu(operação = {n1, n2 ->
        n1 + n2
    })
    
    menu(operação = {n1, n2 ->
        n2 - n1
    })
    
    menu(operação = {n1, n2 ->
        n1 - n2
    })
    
    menu(operação = {n1, n2 -> //Como você pode reparar todo parâmetro que declaramos, estará aqui separado por vírgulas e com uma flecha no fim das declarações, isso nos possibilita usar os valores declarados dentro da função Menu.
        n2 / n1
        //Também não devemos usar explicitamente o comando return.
    })
    
    //trailing lambda -> quando a declaração da nossa função espera uma High Order Function - HOF, em última posição nos parâmetros, isso permite que tiremos dos parênteses essa declaração e passemos para um bloco de código a seguir. A função menu é um exemplo disso, então na pratica tiramos o menu(operação = {}), e passamos apenas para menu() { /* Código */ }
    //Veja o exemplo de trailing lambda ->
    menu() {n1, n2 ->
        n1 - n2
    }
}

fun menu(operacao: (Int, Int) -> Int) {
    println(“======== Menu =========”)
    println(“Eu vou executar a operação que eu recebi como parâmetro”)
    println(“O resultado foi ${operacao(5, 10)}”)
}
```
* Vamos observar, esse fato do comando return não ser explicito, isso ocorre principalmente pela maneira pela qual declaramos, observe as duas linhas abaixo:
`operacao: (Int, Int) -> Int`
`fun operacao(n1: Int, n2: Int) = n1 + n2`
* Reparou como são parecidos? Na prática esse tipo de declaração é uma versão pouco diferente de uma função com retorno simplificado. Por isso não podemos usar o comando return.
---
E aqui terminamos nosso tutorial de funções. Espero que você tenha gostado de ler, em seguida veremos um pouco sobre orientação a objetos.