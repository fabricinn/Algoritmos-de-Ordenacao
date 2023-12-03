# Bubble Sort
O **Bubble sort** é um algoritmo de ordenação simples e intuitivo que funciona trocando repetidamente elementos vizinhos se eles estiverem na ordem errada. A ideia é percorrer um conjunto de elementos diversas vezes, e a cada passagem fazer "flutuar" para o topo o maior elemento da sequência. Seu nome deve-se à forma como os elementos maiores "borbulham" até suas posições corretas à medida que o algoritmo percorre os dados.

## Como Bubble Sort funciona

Este algoritmo percorre a lista de itens ordenáveis do início ao fim, verificando a ordem dos elementos dois a dois, e trocando-os de lugar se necessário. Percorre-se a lista até que nenhum elemento tenha sido trocado de lugar na passagem anterior.

![code](https://www.researchgate.net/publication/348959084/figure/fig1/AS:986621331652608@1612240264456/Working-procedure-of-Bubble-Sort.ppm)

### Código em JavaScript
```js
// Criando a função bblSort. 
função bblSort(arr) {  
	// "i" é quantas vezes o código vai ser executado
	// até que a lista esteja completamente ordenada 
	for (let i = 0; i < arr.length; i++) {  
  
		// "j" é o indice do array percorrido
		// começa no indice 0 e termina no final
		for (let j = 0; j < (arr.length - i - 1); j++) {  
  
			// Verificando se o item que está na iteração atual  
			// é maior que a próxima iteração. 
			if (arr[j] > arr[j + 1]) {  
  
				// Se a condição for verdadeira  
				// então troque-os.  
				let temp = arr[j]  
				arr[j] = arr[j + 1]  
				arr[j + 1] = temperatura  
		}  
	}  
}  
  
// Retorna o array ordenado.  
console.log(arr);  
}  
  
// Este é o nosso array não ordenado.  
let arr = [234, 43, 55, 63, 5, 6, 235, 547];  
  
//Agora passe este array para a função bblSort()  
bblSort(arr);

// Output --> [5, 6, 43, 55, 63, 234, 235, 547]
```

Em alguns casos a lista já estará ordenada, ou pode ser que fique ordenada na metade do loop, para não começarmos o mesmo processo do início verificamos se houve alguma troca na lista. Quando nenhuma modificação é feita, significa que a lista está ordenada.

```js
// Bubble Sort otimizado.

function bubbleSort(arr) {

	var i, j;
	var len = arr.length;

	var isSwapped = false;

	for (i = 0; i < len; i++) {

		isSwapped = false;

		for (j = 0; j < (len - i - 1); j++) {
			if (arr[j] > arr[j + 1]) {
				var temp = arr[j]
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
				isSwapped = true;
			}
		}

		// SE dois elementos não foram trocados
		// dentro do loop interno ele para.
		if (!isSwapped) {
			break;
		}
	}

	// Retorna o array.
	console.log(arr)
}

var arr = [243, 45, 23, 356, 3, 5346, 35, 5];

// Chamando a Função bubbleSort 
bubbleSort(arr)

// Output --> [3, 5, 23, 35, 45, 243, 356, 5346]
```
## Big O

No melhor caso, o algoritmo executa *n* operações relevantes, onde *n* representa o número de elementos do array. No pior caso, são feitas *n²* operações. A complexidade desse algoritmo é de ordem quadrática. Por isso, ele não é recomendado para programas que precisem de velocidade e operem com quantidade elevada de dados. 

