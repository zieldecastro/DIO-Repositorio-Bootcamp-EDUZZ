# DIO-Repositorio-Bootcamp-EDUZZ
Repositório para guardar materiais de estudo, códigos e informações importantes sobre o curso.
#TeamFullstackJS
#contratodecompromisso

//Neste documento me proponho a digitar e testar os exercícios na IDE (VS Code), pois entendo que dessa forma aprendo melhor.<br/>
//Para facilitar a leitura estarei dando um subtítulo para cada assunto.

# Javascript
Currying, Hoisting, Imutabilidade, Tipos e Variáveis.

## Exemplos de funções:

//Função de execução imediata:

let test = 'exemple'; //Variável no escopo global<br/>
(() => {<br/>
console.log(`Valor dentro da função "${test}"`); //Condicional buleano alterando o valor da variável<br/>
if (true) {<br/>
   let test = 'exemple';<br/>
   console.log(`Valor dentro do if "${test}"`);<br/>
}<br/>
console.log(`Valor após a execução do if "{$test}"`);<br/>
})();<br/>
<br/><br/>
## //Obs: <br/><br/>
//O var não respeita escopo de bloco, para respeitar devemos usar o let ou o const.<br/>
//O const não nos permite alterar um valor do tipo primitivo de uma variável.<br/>
<br/><br/>
## //Exemplo de array com const:<br/><br/>

const persons = ['Guilherme', 'Pedro', 'Jennifer'];<br/>
<br/>
//Podemos adicionar novos itens<br/>
persons.push('João');<br/>
//['Guilherme', 'Pedro', 'Jennifer', 'João']<br/>
<br/>
//Podemos remover algum item<br/>
persons.shift();<br/>
//['Pedro', 'Jennifer', 'João']<br/>
<br/>
//Podemos alterar diretamente na posição do array<br/>
persons[1] = 'James';<br/>
// ['Pedro', 'James', 'João']<br/>
<br/>
console.log('\nArray após as alterações: ', persons);<br/><br/>

-----------------------------------------------------------

## //Spread = iterar cada ítem de um array ou objeto e passar como parâmetro.<br/>
// Foi incluído do ES6<br/>
// Exemplo:<br/>
<br/>
var partes = ['ombro', 'joelhos'];<br/>
var musica = ['cabeça', ...partes,'e', 'pés'];<br/>
<br/>
function fn(x, y, z){}<br/>
var args = [0, 1, 2];<br/>
fn(...args);<br/>
<br/>

-----------------------------------------------------------
<br/>
##  //Operadores unários: Executam uma ação com um único operando. <br/>
EX:<br/>
// delete something; // Deletar algo<br/>
// typeof something; // Determinar tipo<br/>
<br/>
//Obs: String e array pussuem a propriedade length<br/>
<br/>
##  //Operadores binários: Executam ações com dois operandos. <br/>
// Operador in = something in somethingItems <br/>
// Operador instanceof = Verifica se o objeto é uma instância <br/>
<br/>
----------------------------------------------------------<br/>
<br/>
##  //Estruturas condicionais: if, else, for, else if, switch case, forEach... <br/>
<br/>
const array = [0, 1, 2, 3, 4, 5];<br/>
<br/>
array.forEach(item => {<br/>
   if (item % 2 === 0) {<br/>
   console.log(`O número ${item}é par.`);<br/>
   } else {<br/>
     console.log(`O número ${item} é impar.`);<br/>
   }<br/>
});   <br/>
<br/>
// Obs: Rodar pelo node copiando e colando no terminal do VS Code.<br/>
<br/>
##  //Encadeando condições com else if: <br/>
<br/>
const array = [2, 3, 4, 5, 6, 8, 10, 15];<br/>
<br/>
console.log('\nelse if');<br/>
array.forEach(item => {<br/>
   if (item % 2 === 0) {<br/>
      console.log(`O número ${item} é divisível por 2.`);<br/>
   } else if (item % 3 === 0){<br/>
      console.log(`O número ${item} é divisível por 3.`);<br/>
   } else if (item % 5 === 0) {<br/>
      console.log(`O número ${item} é divisível por 5.`);<br/>
   }<br/>
});<br/>
  <br/>
##  //Obs: Se quiser que os itens caiam em mais de uma condição não use o else if, apenas o if <br/>
<br/>
console.log('\nif');<br/>
array.forEach(item => {<br/>
   if (item % 2 === 0) {<br/>
   console.log(`O número ${item} é divisível por 2.`);<br/>
}<br/>
if (item % 3 === 0) {<br/>
   console.log(`O número ${item} é divisível por 3.`);<br/>
}<br/>
if (item % 5 === 0) {<br/>
   console.log(`O número ${item} é divisível por 5.`); <br/>
   }<br/>
});   <br/>
<br/>
##  //Switch case <br/>
<br/>
const fruit = 'mamão';<br/>
<br/>
switch (fruit) {<br/>
   case 'banana':<br/>
     console.log('R$ 3,00 / kg');<br/>
	 break;<br/>
   case 'mamão':<br/>
   case 'pera':<br/>
   //Aqui basta ir incrementando os cases de frutas que custam o mesmo preço<br/>
     console.log('R$ 2,00 / kg'); <br/>
     break;<br/>
   default:<br/>
     console.log('Produto não existe no estoque.');<br/>
     break; //Obs: Se retirarmos esse break o default sempre será executado.<br/>
}	 <br/>
<br/>
//Obs: Ao inserir uma fruta não cadastrada o sistema exibirá "O produto não exister no estoque".<br/>
<br/>

-------------------------------------------------------------
<br/>
##  //Estruturas de repetição: for, while, do...ehile, for...in, continue e break. <br/>
<br/>
##  /** for ([expressãoInicial]; [condição]; [incremento/decremento]) <br/>
##   declaração <br/>
*/<br/><br/>

// Ex:<br/>
const array = ['one', 'two', 'three'];<br/>
<br/>
for (let index =0; index < array.length; index++) {<br/>
   const element = array[index];<br/>
   console.log(`Element #${index}: ${element}.`);<br/>
}<br/><br/>
   
   
##  /** while (condição) - Só começa a ser executado se a condição for verdade. <br/>
##       declaração <br/>
  */<br/><br/>
  
// Ex: <br/>  
var n = 0;<br/>
var x = 0;<br/>
while (n < 3){<br/>
  n++;<br/>
  x += n; ...........// 1, 2, 6<br/>
}<br/>
console.log(x);  <br/>
<br/>

##  /** do while - Executa primeiro, depois verifica a condição. <br/>
   do<br/>
       declaração<br/>
     while (condição);<br/>
  */<br/>
  <br/>
// Ex:<br/>
let i = 0;<br/>
do {<br/>
  i += 1; <br/>
  console.log(i);<br/>
} while (i < 5);  <br/>
console.log(i);<br/><br/><br/>


##  //for in e for of <br/>
// Ex:<br/>
let arr = [3, 5, 7];<br/>
arr.foo = "hello";<br/><br/>

for (let i in arr){<br/>
   console.log(i);  //logs "0", "1", "2", "foo" (O for in faz para cada propriedade do array).<br/>
}<br/><br/>

for (let i of arr){<br/>
   console.log(i);  //logs "3", "5", "7"  (for of executa somente para as propriedades numeradas exibindo seus valores).<br/><br/> 
   
//Obs. Array em função é um objeto, então podemos por a propriedade dentro dele.<br/><br/><br/>


##  //Controle da repetição com continue e break: <br/><br/>

// Ex:<br/>
console.log('Exemplo da utilização de break'); <br/>
var index = 0;<br/>
while(true) {<br/>
   index++;<br/><br/>
   
   if (index > 2) {<br/>
   break;<br/>
   }<br/>
   console.log(index);<br/>
 }<br/><br/>

//continue<br/>
console.log('Exemplo da utilização de continue');<br/>
const array = [1,2,3,4, 5, 6];<br/>

for (let index = 0; index <  array.length; index++){<br/>
   const element = array[index];<br/>
   
   if (element % 2 === 0){<br/>
      continue;<br/>
   }	  <br/>
   console.log(element);<br/>
}<br/><br/>

-----------------------------------------------------------
<br/><br/><br/>


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

