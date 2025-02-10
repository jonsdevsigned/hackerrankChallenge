# Mi Repositorio de Ejercicios

Este repositorio contiene ejercicios resueltos.

## Ejercicio 1: Solve me first

Descripción: Sumar dos números.

### Código final en HackerRank

```javascript
function solveMeFirst(a, b) {
  return a + b  
}
```
## Ejercicio 2: Simple Array Sum

Descripción: Sumar los números en un array.

### Código desarrollado en VScode

```javascript
function sumArray(userNum) {
    let resultSumArray = 0
    const arrayNum = []
    
    //el for con el metodo push crea el array de numero consecutivos
    for (let n=1; n<=userNum; n++) {
        arrayNum.push(n)
    }
    
    //este for recorre el array para ir sumando sus indices
    for (let i=0; i<arrayNum.length; i++) {
        resultSumArray += arrayNum[i]
    }
    
    return console.log(`la suma del array es: ${resultSumArray}`)

}

sumArray(10)
```
`El resultado esperado debe ser: 55`

### Código final en HackerRank

```javascript
function simpleArraySum(ar) {
    let sumArray = 0
    
    for (let i=0; i<ar.length; i++) {
        sumArray += ar[i]
    }
    
    return sumArray       
}
```

## Ejercicio 3: Compare the Triplets

Descripción: Compara dos arrays los cuales contiene 3 indices.

### Código desarrollado en VScode

```javascript
function compareTriplets(a, b) {
    let comparation = a.length === b.length
    let points = [0, 0]
    
    //el if verifica que los dos arrays contengan la misma cantidad de indices
    if (comparation === true) {
        
        for (let i = 0; i < a.length; i++) {

            console.log(`Comparacion ${i + 1}: Alice tiene ${a[i]} y Bob ${b[i]}`)

            //este if se encarga de sumar puntos a quien su contenido del indice sea mas alto
            if (a[i] < b[i]) {
                console.log('punto para Bob')
                points[1] += 1
            } else if (a[i] > b[i]) {
                console.log('punto para Alice')
                points[0] += 1
            } else if (a[i] === b[i]) {
                console.log('no hay puntos')
            }
        }

        console.log(`El array de puntuación es: [${points}]`)
    } else {
        console.log('Los arrays no contienen la misma cantidad de indices para una comparación optima.')
    }
}

compareTriplets([17, 28, 30], [99, 16, 8])
```
`El resultado esperado debe ser: [2,1]`

### Código final en HackerRank

```javascript
function compareTriplets(a, b) {
    const points = [0, 0]
    
    for(let i=0; i<a.length; i++) {
        
        if(a[i] < b[i]) {
            points[1] += 1
        } else if(a[i] > b[i]){
            points[0] += 1
        } 
    }
    
    return points
}
```

## Ejercicio 4: A very big sum
Descripción: Calcular e imprimir la suma de elementos en un array

### Código final en HackerRank
```javascript
function aVeryBigSum(ar) {

    let sum = 0

    for (let i = 0; i < ar.length; i++) {
        sum += ar[i]
    }

    return sum
}
```

## Ejercicio 5: Diagonal difference
Descripción: Dada una matriz cuadrada, calcula la diferencia absoluta entre las sumas de sus diagonales

### Código desarrollado en VScode
```javascript
function diagonalDifference(arr) {
    const diagonalA = []
    const diagonalB = []
    let sumDiagA = 0
    let sumDiagB = 0

    for (let i = 0; i < arr.length; i++) {
        //arr[0][0], arr[1][1], arr[2][2], arr[3][3]
        diagonalA.push(arr[i][i])
        sumDiagA += diagonalA[i]
        //para que la diagonal b fuera del ultimo al primero se tomo el tamaño del arreglo-1 y se resta su indice.
        //lo que da una cuenta regresiva: arr[0][3], arr[1][2], arr[2][1], arr[3][0]
        diagonalB.push(arr[i][(arr.length - 1) - i])
        sumDiagB += diagonalB[i]
    }

    let result = sumDiagA - sumDiagB
    console.log(`la primera diagonal es [${diagonalA}] = ${sumDiagA}`)
    console.log(`la segunda diagonal es [${diagonalB}] = ${sumDiagB}`)

    //con el operador ternario (condicion ? true : false) si el resultado es negativo lo multiplico * -1 para que su resultado sea positivo
    return console.log(`la diferencia entre ${sumDiagA} - ${sumDiagB} = ${result < 0 ? result * -1 : result}`)
}

diagonalDifference([[11, 2, 4, 5], [4, 5, 6, 7], [10, 8, -12, 9], [3, -5, 15, 1]])
```
`El resultado esperado debe ser: 17`

### Código final en HackerRank
```javascript
function diagonalDifference(arr) {
    const diagonalA = []
    const diagonalB = []
    let sumDiagA = 0
    let sumDiagB = 0

    for (let i = 0; i < arr.length; i++) {
        diagonalA.push(arr[i][i])
        sumDiagA += diagonalA[i]
        diagonalB.push(arr[i][(arr.length-1) - i])
        sumDiagB += diagonalB[i]
    }

    let result = sumDiagA - sumDiagB
    
    return result < 0 ? result * -1 : result
}
```

## Ejercicio 6: Plus minus
Descripción: Dada una matriz de números enteros, calcula las razones de sus elementos que son positivos, negativos y ceros. Imprime el valor decimal de cada fracción en una nueva línea con 6 lugares después del decimal.

### Código desarrollado en VScode
```javascript
function plusMinus(arr) {
    const positivesArray = []
    const negativesArray = []
    const zerosArray = []

    for (let i = 0; i < arr.length; i++) {
        
        //filtra los numeros positivos, negativos y ceros en su respectivo array
        if (arr[i] === 0) {
            zerosArray.push(arr[i])
        } else if (arr[i] < 0) {
            negativesArray.push(arr[i])
        } else if (arr[i] > 0) {
            positivesArray.push(arr[i])
        }
    }

    console.log(`[${positivesArray}]\n[${negativesArray}]\n[${zerosArray}]`)

    let proportionsPositives = positivesArray.length / arr.length
    let proportionsNegatives = negativesArray.length / arr.length
    let proportionsZeros = zerosArray.length / arr.length

    //toFixed es el metodo encargado de ajustar las cantidades de decimales
    return console.log(`positivos ${positivesArray.length}/${arr.length}: ${proportionsPositives.toFixed(6)}\nnegativos ${negativesArray.length}/${arr.length}: ${proportionsNegatives.toFixed(6)}\nceros ${zerosArray.length}/${arr.length}: ${proportionsZeros.toFixed(6)}`)
}

plusMinus([-4, 3, -9, 0, 4, 1])
```
`El resultado esperado debe ser: positivos 3/6: 0.500000 | negativos 2/6: 0.333333 | ceros 1/6: 0.166667`

### Código final en HackerRank
```javascript
function plusMinus(arr) {
    const positivesArray = []
    const negativesArray = []
    const zerosArray = []

    for (let i = 0; i < arr.length; i++) {

        if (arr[i] === 0) {
            zerosArray.push(arr[i])
        } else if (arr[i] < 0) {
            negativesArray.push(arr[i])
        } else if (arr[i] > 0) {
            positivesArray.push(arr[i])
        }
    }

    let proportionsPositives = positivesArray.length / arr.length
    let proportionsNegatives = negativesArray.length / arr.length
    let proportionsZeros = zerosArray.length / arr.length

    return console.log(`${proportionsPositives.toFixed(6)}\n${proportionsNegatives.toFixed(6)}\n${proportionsZeros.toFixed(6)}`)
}
```

## Ejercicio 7: Staircase
Descripción: Imprima una escalera. No debe estar precedida por espacios. Todas las líneas están alineadas a la derecha.

```bash
El resultado esperado debe ser:
     #
    ##
   ###
  ####
 #####
######
```

### Código final en HackerRank
```javascript
function staircase(n) {
    
     let arrStaircase = []

    for (let i = 1; i <= n; i++) {

        arrStaircase.push('#')
        //.join es un metodo que se usa para separar los arrays segun le indiquemos. Pues ser sin espacio ('') con espacio (' ') con coma y espacio (', ')
        let separateContArr = arrStaircase.join('')
        //el console que retorna se queda dentro del for para que itere cada linea de numeros consecutivos
        console.log(separateContArr.padStart(n))
    }
}
```