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
a) A saída será undefined seguido de erro **X = A alternativa correta é a A, pois o console.log(x) será incapaz de identificar o valor da variável x quando esta está declarada após
a sua execução, além da let y que também está inserida no mesmo problema e configura uma variável limitada à seu escopo, provocando um erro.**

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0) **X = A alternativa correta é a C, pois a condição utilizada inicialmente utiliza da condicional (ou) para verificar se o 
número é válido ou não, mas esta pode considerar os contextos em que somente um dos valores é 0, o que representa um erro pois, no exemplo utilizado, 2 + 0 = 2, ou seja, é uma
adição desnecessária porém válida. Para corrigir este erro, basta considerar o caso em que ambos os valores são 0, o que a alternativa C apresenta corretamente como alteração.**

d) Remover completamente a verificação if (a || b === 0)

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

b) O código imprime 200. **X = A alternativa correta é a B, pois a partir da chamada de "eletrônico", o código seguirá a estrutura de switches até que chegue em algum valor, o que 
levaria à impressão de 200. Após o primeiro valor (1000), não existe o comando de break, portanto o código continuaria progredindo até encontrar um.**

c) O código imprime 50.

d) O código gera um erro.

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

d) 24 **X = A alternativa correta é a D, pois o código passa pela a etapa de multiplicar todos os valores do array "numeros" por 2, considerar somente os valores que após a 
multiplicação são maiores que 5 (6, 8 e 10), e a etapa de somá-los (24).**
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] **X = A alternativa C é a correta, pois o comando lista.splice altera os valores interiores do array "lista", substituindo o segundo 
e terceiro valor (começando do 0) para "abacaxi" e "manga" respectivamente.**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira. **X = A alternativa A é a correta, pois ambas as afirmações são verdadeiras, com a segunda demonstrando de que maneira a repetição de código citada na primeira é evitada através do método de herança "extends", com este ocorrendo através da estrutura "class extends (nome da classe mãe){}.**

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
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

a) I e II são verdadeiras. **X = A alternativa correta é a A, pois a classe "Funcionario", criada após a classe "Pessoa", utiliza-se do método "extends" para utilizar os atributos da classe pai, de maneira que os nomes e idades disponíveis sejam considerados diretamente através do comando "super" dentro da função "constructor". O método apresentar() utiliza-se das determinações do método da classe pai utilizando super, porém sobrepõe tais elementos através da definição de um console.log diferente. A terceira afirmação é refutada a partir do momento que as duas anteriores são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção. **X = A alternativa correta é a D, pois a asserção define o polimorfismo como dois objetos de classes e tipos diferentes que são capazes de exercer diferentes funções com métodos de mesma nomenclatura, com estes sendo descritos em maior detalhe pela afirmação da razão, a partir do momento em que no processo das criações das classes, métodos de mesmo nome podem possuir parâmetros e comandos variados.**

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

**RESPOSTA**
```javascript
// Declara uma variável global e a inicializa com 0 (a fim de garantir a soma de todo o array mais para frente).
var soma = 0;

// Define uma função que recebe dois parâmetros: 'numeros' (um array) e 'soma' (um valor inicial para a soma), garantindo o registro de ambos ao longo do processo.
function somaArray(numeros, dobro) {
  for (i = 0; i < numeros.length; i++) {
    // Adiciona o valor do elemento atual à 'soma' e multiplica o resultado por 2, atribuindo o valor ao 'dobro', utilizando parênteses a fim de garantir que a multiplicação englobe todos os elementos somados.
    dobro = 2 * (soma += numeros[i]);
  }
  return dobro;
}

console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

**RESPOSTA**
```javascript
// Cria uma classe chamada Produto com os atributos nome e preco, e um método chamado calcularDesconto que retorna o valor do desconto de 10% do preço
class Produto {
  constructor(nome, preco) {
    this.nome = 'nome';
    this.preco = 0;
  }
    calcularDesconto() {
      return this.preco - this.preco * 0.1;
    }
}
//Utiliza a propriedade extends para criar uma classe chamada Livro que herda de Produto, utilizando o super para chamar os atributos do construtor da classe pai
class Livro extends Produto {
  constructor(nome, preco) {
    super(nome, preco);
    this.nome = 'livro';
    this.preco = 12;
  }
    //O método é alterado a partir da modificação do valor do decimal de 0.1 para 0.2
    calcularDesconto() {
      return this.preco - this.preco * 0.2;
    }
}
```
