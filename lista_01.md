# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
`a) A saída será undefined seguido de erro`

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

`Explicação: Na primeira situação, como a variável "x" foi declarada com "var", sua existência é reconhecida antes mesmo de receber um valor. No entanto, como ainda não foi atribuída, seu valor inicial é undefined, resultando nessa saída ao executar "console.log(x)", já que é executado antes de "x" receber um valor. Já no segundo caso, a variável "y", declarada com "let", não pode ser acessada antes da sua definição. Isso significa que, até a linha em que é declarada e atribuída, "y" não existe para o programa, o que gera um erro (ReferenceError) já que o código "console.log(y)" é executado antes de "y" receber um valor.`


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

`a) Substituir if (a || b === 0) por if (a === 0 || b === 0)`

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

`Explicação: Os operadores em JavaScript também seguem uma ordem de execução como a matemática, por exemplo. Nesse contexto, o operador "===" possui prioridade em relação ao "||". Assim, como a comparação estrita é executada primeiro, somente a variável "b" está sofrendo a comparação de ""valor" e "tipo de dado". Em segunda instância, será executado o operador de "ou", que apenas necessita que uma das condições seja "truthy" para sua execução. Portanto, mesmo que "b" receba o valor de "0" e o tipo de dado number, se o "a" receber algo que caracterize ele como "truthy", ou seja, diferente de "0", "NaN", "undefined", "null", "string vazia" e, obviamente, "false", o código interpretará como "truthy" e a saída não será "Erro: número inválido". De uma maneira geral, mesmo que "b" receba "0", se "a" receber, por exemplo uma string "olá", a condição será "truthy". Para solucionar o erro, é necessário que "a" seja comparado a "0" ou "b" seja comparado a "0", ou seja "a === 0 || b === 0".`
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

`b) O código imprime 200.`

c) O código imprime 50.

d) O código gera um erro.

`Explicação: Inicialmente, sob o contexto da função "calcularPreco()", a variável "tipo" recebe "eletrônico" e, consequentemente, a variável "preco" recebe o valor do caso "eletrônico", ou seja, "1000". Porém, o caso "eletrônico" não possui o "break" após a declaração da variável "preco", o que faz com que "preco" continue no switch e passe a valer o valor do caso "vestuário", ou seja, "200", o qual tem "break" e define o valor da variável "preco" no código.`
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

`d) 24`

`Explicação: Inicialmente, no contexto da função "map()", os valores da array "numeros" são multiplicados por "2", assim o produto é: [2, 4, 6, 8, 10]. Subsequente, é filtrado todos os números maiores que "5" pela função "filter()", ou seja, resultam: [6, 8, 10]. Por fim, é somado todos os números que restaram na array da variável "numeros" por conta da função "reduce()" mais o número inicial, nesse contexto, "0", ou seja, 0 + 6 + 8 + 10 = 24. Portanto a variável "resultado" recebe 24.`
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

`c) ["banana", "abacaxi", "manga", "laranja"]`

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

`Explicação: A função "splice()" remove/adiciona elementos em uma array. O primeiro número dentro dos parênteses, nesse contexto, "1", indica o começo da modificação. O segundo número, "2", indica a quantidade de termos que serão removidos. Assim, como última etapa, adiciona-se os elementos na array começando pelo índice do começo, ou seja, "1". Portanto, na array "lista" foi removido "maçã" e "uva" e adicionado "abacaxi" e "manga".`
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


`a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.`

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

`Explicação: A herança em JavaScript permite que uma classe filha derive características de outra classe, a classe pai, promovendo reutilização de código e organização. Para isso, é necessário a palavra-chave "extends". Exemplo: class "classePai" {método} \n class "classeFilha" "extends" "classePai", logo o método da classePai é herdado para a classeFilha.`
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

`a) I e II são verdadeiras.`

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

`Explicação: A afirmação I) está correta, pois a classe filha "Funcionario" herda os atributos nome e idade da classe pai "Pessoa" por "extends". A afirmação II) está correta, pois ambas as classes possuem o método "apresentar()", o que gera a sobreposição do método da classe filha "Funcionario" em relação à classe pai "Pessoa". Porém, com a função "super.apresentar()", dentro do método "apresentar()" da classe "Funcionario", é executado primeiramente o método "apresentar()" da classe "Pessoa" e depois o "console.log()". A afirmação III) está incorreta, pois em JavaScript suporta herança de classes com a palavra-chave "extends".`
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

`b) A asserção é verdadeira e a razão é falsa.`

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

`Explicação: Polimorfismo em Programação Orientada a Objetos (POO) é a capacidade de objetos de diferentes tipos responderem à mesma mensagem de maneiras distintas, sem que um método sobrescreva outro dentro da mesma classe. Ou seja, cada classe pode ter sua própria implementação do mesmo método, garantindo que a afirmação "Asserção" esteja correta. Já a afirmação "Razão" está incorreta, pois JavaScript não possui suporte nativo para sobrecarga de métodos dentro de uma mesma classe. Isso significa que, se dois métodos dentro da mesma classe tiverem o mesmo nome, independentemente da quantidade ou tipo de parâmetros, o último método declarado sobrescreverá o anterior.`
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript

// Situação Problema 
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

```javascript

// Resposta
function somaArray(numeros) {
  let soma = 0; // declarei variável soma

    for (let i = 0; i < numeros.lenght; i++) { // declarei variável "i" e troquei "size" por "lenght"
        soma += 2 * numeros[i]; // implementei o operador "+=" para somar os valores dobrados
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4])); // saída: 20
```
`Explicação: Na linha 227 observei 2 erros: variável "i" não foi declarada, para isso utilizei a declaração "let", além de "size" não ser uma propriedade, para isso utilizei "lenght" para obter tamanho da array. Na linha 228 observei igualmente dois erros: variável soma não foi declarada, então declarei-a na linha 225 e variável soma apenas estava dobrando os valores da array, para somar os valores dobrados da array utilizei o operador "+=" que implementa esses valores em forma de soma. Logo, agora o código funcionará corretamente e, nesse caso, dobrará todos os valores da array [1, 2, 3, 4] e os somará, portanto, aparecerá o valor: 20.`
______

10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

``` javascript

// Criação da classe Produto
class Produto {
  constructor(nome, preco) { // Declaração do construtor para classe "Livro" herdar atributos "nome" e "preco"
    // Declaração de atributos para essa classe
    this.nome = nome; 
    this.preco = (preco); 
  }
  
  // Criação do método de calcular produto após desconto de 10% fixo
  calcularDesconto() {
    return this.preco * 0.90;
  }

  // Criação do método de exibir mensagem explicitando o nome e o valor após desconto do produto
  exibirPrecoComDesconto() {
    console.log(`O produto "${this.nome}" com 10% de desconto custa R$ ${this.calcularDesconto().toFixed(2)}`)
  }

}

// Criação da classe Livro que herda atributos e métodos da classe Produto
class Livro extends Produto {
  constructor(nome, preco) { 
    super(nome, preco); // Reutilização de atributos da classe pai "Produto"
  }
  
  // Modificação do mesmo método da classe "Produto", agora com atributos da classe filha "Livro"
  calcularDesconto() {
    return this.preco * 0.80;
  }

  // Modificação do mesmo método da classe "Produto", agora com atributos da classe filha "Livro"
  exibirPrecoComDesconto() {
    console.log(`O livro "${this.nome}" com 20% de desconto custa R$ ${this.calcularDesconto().toFixed(2)}`)
  }

}

// Criação de objetos com seus respectivos valores
let produto1 = new Produto("Mouse", 100);
let livro1 = new Livro("Hábitos Atômicos", 200);

// Chamando métodos
produto1.exibirPrecoComDesconto();
livro1.exibirPrecoComDesconto();

```
Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

`Explicação: A herança nesse contexto é utilizada para a classe filha "Livro" herdar os métodos e atributos da classe pai "Produto" com o uso da palavra-chave "extends", logo, a classe "Livro" já possui os atributos "nome" e "preco" sem precisar declará-los de novo, além dos métodos "calcularDesconto()" e "exibirPrecoComDesconto()" serem sobrescritos em relação à classe "Livro". Em relação à modificação do método na classe "Livro", eu sobrescrevi o método pois, já que o JavaScript não possui suporte nativo para sobrecarga de métodos, eles serão sobrescritos e reutilizados, agora modificando com as próprias informações da classe, utilizando assim o polimorfismo, evitando a repetição e facilitando a organização.`