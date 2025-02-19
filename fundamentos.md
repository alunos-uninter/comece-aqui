# Introdução a programação

Se você nunca escreveu uma linha de código na vida, então essa trilha é
definitivamente para você. Caso você já tenha uma certa experiência com
programação e no design de algoritmos, mesmo que você talvez conheça boa parte
dos métodos, recomendo ir direto para
[seção de como projetar algoritmos](como-projetar-algoritmos), lá é
explicado conceitos mais profundos no desenvolvimento de algoritmos.

## Estudar linguagem de programação não é aprender a programar

Talvez o método funcione para alguns estudantes, no entanto, ensinar as
características e sintaxe de uma linguagem de programação não é exatamente
estudar a metodologia de se projetar algoritmos. O principal fato chave disso
não ser uma abordagem recomendada é que ignora completamente os fundamentos
necessários que todas as linguagens de programação compartilham entre si,
criando então um conhecimento limítrofe de programação. Portanto, é
importante absorver os conceitos básicos para que seja possível a aplicação em
diferentes contextos ou linguagens de programação.

## ALGORITMOS

Título bem exagerado, mas há uma boa razão pra isso. Algoritmos são o objeto
central do estudo de ciência da computação, assim como também em outros
aspectos do cotidiano, apenas com outra nomenclatura. Informalmente falando, um
algoritmo é uma sequência de passos que almejam atingir um determinado objetivo.
Algoritmos possuem as seguintes propriedades:

* **São organizados de forma lógica**: Para melhor exemplificar isso pense no
simples processo de ligar um computador.
* **Devem terminar execução**: Um algoritmo mal projetado pode não finalizar,
ou seja, um _loop_ (execução em círculo) eterno. Isto pode ocorrer por causa da
negligência da organização lógica do algoritmo, incluindo a própria lógica
(ou prova real) do algoritmo.
* **Devem resolver o problema proposto**: O algoritmo deve ser capaz de
resolver o problema proposto, dado que está bem definido e é provado que o
algoritmo finaliza. Há exceções, já que nem sempre algoritmos podem ser
expressados para resolver alguns certos problemas ou os resultados podem não ser
um dos mais precisos (veja
[aqui](https://www.britannica.com/science/NP-complete-problem)).

### Representações Algorítmicas

- **Pseudocódigo**: Muito semelhante a uma linguagem de programação por causa de
sua estrutura. Não existe um padrão definido para esta representação de
algoritmos.
- **Fluxograma**: Figuras são usadas para representar algoritmos. Possuem um
padrão de representação. Sua principal utilidade é no projeto de desenvolvimento
de algoritmos.
- **Descrição objetiva**: É parágrafos em uma língua comum
(e.x português por exemplo). Útil em algoritmos levemente pequenos, grandes
algoritmos pode transformar esta abordagem mais incômoda.

O que foi descrito até agora, remete a ideia de algoritmos que seguem uma linha
reta, isto é, sem quebra de corrente de execução dos algoritmos. No entanto,
algoritmos reais tendem a quebrar a corrente de execução com uma certa
frequência, incluindo **repetir** certos passos dada determinada **condição**.

- **se-senão (if-else)**: Determina procedimentos específicos a serem
executados caso a **condição** seja atendida.

  ```py
  a = 12
  b = 32

  # Escreva no terminal o valor de a caso a seja igual a 12
  if (a == 12):
      print(a)
  else:
      print("O valor não era 12")
  ```

- **Laços de repetição**: Determina procedimentos específicos a serem
executados repetidamente de acordo com uma **condição**

  ```py
  # Variável contadora
  var_contador = 0

  # Será escrito na tela "AHAHAHAHAHAHAHAAHAHHAHAHAHA"
  # enquanto o contador for menor que 10
  while (var_contador < 10):
      print("AHAHAHAHAHAHAHAAHAHHAHAHAHA")

      # Acrescenta um ao contador. Essencial para que o algoritmo não esteja
      # preso em um círculo infinito (loop infinito)
      var_contador = var_contador+1
  ```

## Como projetar algoritmos

Em conceitos futuros de engenharia de software, é visto que um bom sistema de
software possui um processo bem definido de desenvolvimento. Algo similar ocorre
no projeto de algoritmos. Portanto nas seções a seguir, veremos uma espécie de
receita para diferentes desafios em projeto de algoritmos.
