# DIO-Repositorio-Bootcamp-EDUZZ
Repositório para guardar materiais de estudo, códigos e informações importantes sobre o curso.
#TeamFullstackJS
#contratodecompromisso

//Neste documento me proponho a digitar e testar os exercícios na IDE (VS Code), pois entendo que dessa forma aprendo melhor.
//Para facilitar a leitura estarei dando um título para cada assunto.

# Javascript
Currying, Hoisting, Imutabilidade, Tipos e Variáveis.

# Exemplos de funções:

//Função de execução imediata:

let test = 'exemple'; //Variável no escopo global
(() => {
console.log(`Valor dentro da função "${test}"`); //Condicional buleano alterando o valor da variável
if (true) {
   let test = 'exemple';
   console.log(`Valor dentro do if "${test}"`);
}
console.log(`Valor após a execução do if "{$test}"`);
})();

# //Obs: 
//O var não respeita escopo de bloco, para respeitar devemos usar o let ou o const.
//O const não nos permite alterar um valor do tipo primitivo de uma variável.

# //Exemplo de array com const:

const persons = ['Guilherme', 'Pedro', 'Jennifer'];

//Podemos adicionar novos itens
persons.push('João');
//['Guilherme', 'Pedro', 'Jennifer', 'João']

//Podemos remover algum item
persons.shift();
//['Pedro', 'Jennifer', 'João']

//Podemos alterar diretamente na posição do array
persons[1] = 'James';
// ['Pedro', 'James', 'João']

console.log('\nArray após as alterações: ', persons);

-----------------------------------------------------------

# //Spread = iterar cada ítem de um array ou objeto e passar como parâmetro.
// Foi incluído do ES6
// Exemplo:

var partes = ['ombro', 'joelhos'];
var musica = ['cabeça', ...partes,'e', 'pés'];

function fn(x, y, z){}
var args = [0, 1, 2];
fn(...args);

-----------------------------------------------------------

# //Operadores unários: Executam uma ação com um único operando
EX:
// delete something; // Deletar algo
// typeof something; // Determinar tipo

//Obs: String e array pussuem a propriedade length

# // Operadores binários: Executam ações com dois operandos
// Operador in = something in somethingItems 
// Operador instanceof = Verifica se o objeto é uma instância 

----------------------------------------------------------

# //Estruturas condicionais: if, else, for, else if, switch case, forEach...

const array = [0, 1, 2, 3, 4, 5];

array.forEach(item => {
   if (item % 2 === 0) {
   console.log(`O número ${item}é par.`);
   } else {
     console.log(`O número ${item} é impar.`);
   }
});   

// Obs: Rodar pelo node copiando e colando no terminal do VS Code.

# //Encadeando condições com else if:

const array = [2, 3, 4, 5, 6, 8, 10, 15];

console.log('\nelse if');
array.forEach(item => {
   if (item % 2 === 0) {
      console.log(`O número ${item} é divisível por 2.`);
   } else if (item % 3 === 0){
      console.log(`O número ${item} é divisível por 3.`);
   } else if (item % 5 === 0) {
      console.log(`O número ${item} é divisível por 5.`);
   }
});
  
# //Obs: Se quiser que os itens caiam em mais de uma condição não use o else if, apenas o if

console.log('\nif');
array.forEach(item => {
   if (item % 2 === 0) {
   console.log(`O número ${item} é divisível por 2.`);
}
if (item % 3 === 0) {
   console.log(`O número ${item} é divisível por 3.`);
}
if (item % 5 === 0) {
   console.log(`O número ${item} é divisível por 5.`);   
   }
});   

# //Switch case

const fruit = 'mamão';

switch (fruit) {
   case 'banana':
     console.log('R$ 3,00 / kg');
	 break;
   case 'mamão':
   case 'pera':
   //Aqui basta ir incrementando os cases de frutas que custam o mesmo preço
     console.log('R$ 2,00 / kg');
     break;
   default:
     console.log('Produto não existe no estoque.');
     break; //Obs: Se retirarmos esse break o default sempre será executado.
}	 

//Obs: Ao inserir uma fruta não cadastrada o sistema exibirá "O produto não exister no estoque".

-------------------------------------------------------------

# //Estruturas de repetição: for, while, do...ehile, for...in, continue e break.

# /** for ([expressãoInicial]; [condição]; [incremento/decremento])
#   declaração
*/

// Ex:
const array = ['one', 'two', 'three'];

for (let index =0; index < array.length; index++) {
   const element = array[index];
   console.log(`Element #${index}: ${element}.`);
}
   
   
# /** while (condição) - Só começa a ser executado se a condição for verdade
#       declaração
  */
  
// Ex:   
var n = 0;
var x = 0;
while (n < 3){
  n++;
  x += n; ...........// 1, 2, 6
}
console.log(x);  


# /** do while - Executa primeiro, depois verifica a condição. 
#   do
#       declaração
#     while (condição);
  */
  
// Ex:
let i = 0;
do {
  i += 1; 
  console.log(i);
} while (i < 5);  
console.log(i);


# //for in e for of
// Ex:
let arr = [3, 5, 7];
arr.foo = "hello";

for (let i in arr){
   console.log(i);  //logs "0", "1", "2", "foo" (O for in faz para cada propriedade do array).
}

for (let i of arr){
   console.log(i);  //logs "3", "5", "7"  (for of executa somente para as propriedades numeradas exibindo seus valores). 
   
//Obs. Array em função é um objeto, então podemos por a propriedade dentro dele.


# //Controle da repetição com continue e break:

// Ex:
console.log('Exemplo da utilização de break');
var index = 0;
while(true) {
   index++;
   
   if (index > 2) {
   break;
   }
   console.log(index);
 }

//continue
console.log('Exemplo da utilização de continue');
const array = [1,2,3,4, 5, 6];

for (let index = 0; index <  array.length; index++){
   const element = array[index];
   
   if (element % 2 === 0){
      continue;
   }	  
   console.log(element);
}

-----------------------------------------------------------



# Iniciando no Typescript
1º Configuração do ambiente e criação do arquivo index:
2º No terminal, crie ou acesse uma pasta para trabalhar com o typescript digite: npm init e pressione enter a cada passo até terminar a instalação.
3º Observe pela sua IDE que será criado um arquivo {}package.json e um {}package-lock.json
4º No terminal, digite: npm i parcel-bundler  
5º Na sua IDE crie um arquivo index.html e crie a estrutura do arquivo em html.
6º Crie também um arquivo index.ts contendo: console.log('TypeScript');
7º No arquivo package.json, vamos criar logo abaixo da palavra script o nosso start = "start": "parcel index.html",
8º No arquivo index.html, referencie o arquivo index.ts dentro da tag body = <script src="./index.ts"></script>
9º Rode o seguinte comando no terminal = npm run start
10º copie o endereço http://localhost:xxxx e cole no seu navegador, pressione enter e em seguda a tecla f12 para ver se aparece a palavra TypeScript no console.

