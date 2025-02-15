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

## Ejercicio 8: Mini-Max Sum
Descripción: Dados cinco números enteros positivos, encuentre los valores mínimo y máximo que se pueden calcular sumando exactamente cuatro de los cinco números enteros. Luego imprima los valores mínimo y máximo respectivos como una sola línea de dos enteros largos separados por espacios.

### Código desarrollado en VScode
```javascript
function miniMaxSum(arr) {

    let sumElements = 0
    const resultArray = []

    //este for suma todos los indices del array
    for (let i = 0; i < arr.length; i++) {
        sumElements += arr[i]
    }

    for (let i = 0; i < arr.length; i++) {
        //para crear el array con la suma de cada conjunto de indices tome la suma total de todos los elementos en el array y le voy restando cada indice. 15-1=14, 15-2=13, 15-3=12 ...
        resultArray.push(sumElements - arr[i])
    }

    //este console log muestra el resultado de las sumas de cada conjunto de indices 2+3+4+5=14, 1+3+4+5=13, 1+2+4+5=12, 1+2+3+5=11, 1+2+3+4=10
    console.log(resultArray)
    let max = resultArray[0]
    let min = resultArray[0]

    for (let i = 0; i < resultArray.length; i++) {
        //esta condicional busca en el array de los resultados el indice mayor o menor para luego agregarlo a la variable correspondiente.
        if (resultArray[i] > max) {
            max = resultArray[i]
        } else if (resultArray[i] < min) {
            min = resultArray[i]
        }
    }

    console.log(min, max)

    //Math.max y Math.min es otra forma mas sencilla de hallar el numero mayor o menor en un array. Los ... es un spread
    let maxMath = Math.max(...resultArray)
    let minMath = Math.min(...resultArray)

    console.log(minMath, maxMath)
}

miniMaxSum([1, 2, 3, 4, 5])
```
`El resultado esperado debe ser: 10 14`

### Código final en HackerRank
```javascript
function miniMaxSum(arr) {
    
    let sumElements = 0
    const resultArray = []

    for (let i = 0; i < arr.length; i++) {
        sumElements += arr[i]
    }

    for (let i = 0; i < arr.length; i++) {
        resultArray.push(sumElements - arr[i])
    }

    let max = resultArray[0]
    let min = resultArray[0]

    for (let i = 0; i < resultArray.length; i++) {
        if (resultArray[i] > max) {
            max = resultArray[i]
        } else if (resultArray[i] < min) {
            min = resultArray[i]
        }
    }

    console.log(min, max)
}
```

## Ejercicio 9: Birthday Cake Candles
Descripción: Estás a cargo del pastel para el cumpleaños de un niño. Tendrá una vela para cada año de su edad total. Sólo podrán soplar las velas más altas. Su tarea es contar cuántas velas son las más altas.

### Código desarrollado en VScode
```javascript
function birthdayCakeCandles(candles) {

    /*Para encontrar el numero mayor del array primero creamos la variable.
    Se le asigna un indice del array para que cumpla su función de comparar
    en el condicional if*/
    let maxCandles = candles[0]

    //Con el for iteramos todos los indices del array
    for (let i = 0; i < candles.length; i++) {

        /*La condicional funciona de la siguiente forma
        la primera iteración 2 > 2 es false
        la segunda iteración 3 > 2 es true. Por lo que a la variable maxCandle se le asigna el 3
        la tercera iteración 1 > 2 es false
        La cuarta iteración es 3 > 2 es true y hace los mismo que en la segunda iteración.*/
        if (candles[i] > maxCandles) {
            maxCandles = candles[i]
        }
    }

    //por esto el resultado del console log es 3, ya que es el número mayor del array
    console.log(`el numero mayor de este array es: ${maxCandles}`)

    //conociendo cual es el numero mayor de nuestro array usamos filter crear un nuevo array con el numero mayor que se repite. 
    let cantMaxCandles = candles.filter((candle) => candle === maxCandles)

    //finalmente usamos .length para contar la cantidad de veces que se ha repetido el numero mayor en nuestro array candles.
    console.log(`Dentro del array el numero ${maxCandles} se repite ${cantMaxCandles.length} ${cantMaxCandles.length === 1 ? 'vez' : 'veces'}`)
}

birthdayCakeCandles([2, 3, 1, 3])
```
`El resultado esperado debe ser: 2`

### Código final en HackerRank
```javascript
function birthdayCakeCandles(candles) {
    
    let maxCandles = candles[0]

    for (let i = 0; i < candles.length; i++) {

        if (candles[i] > maxCandles) {
            maxCandles = candles[i]
        }
    }
   
    let cantMaxCandles = candles.filter((candle) => candle === maxCandles)
    
    return cantMaxCandles.length
}
```

## Ejercicio 10: Time Conversion
Descripción: Dada una hora en formato AM/PM, conviértala a hora militar.

### Código desarrollado en VScode
```javascript
function timeConversion(s) {

    /* substring es un metodo que devuelve el texto entre los indices especificados. 
    Si el string es '07:05:45PM' devolvera '07:05:45'*/
    let hourDeleteAMPM = s.substring(0, 8)
    /* el metodo split divide el string en un array. 
    Siendo el string recibido '07:05:45PM' devuelve ['07', '05', '45PM'] */
    let separateHour = s.split(':')
    let militaryHour

    /*Este if permite reconocer con include si la hora es AM o PM Revisando el indice 2 de separateHour '45PM'
    includes revisa si un string contiene la cadena indicada.*/
    if (separateHour[2].includes('AM')) {

        //El indice 0 '07' es ==== '12'  --  false
        if (separateHour[0] === '12') {
            //replace remplaza la parte del string indicada. En este caso si el indice 0 contiene '12' sera remplazado por '00'
            militaryHour = console.log(hourDeleteAMPM.replace('12', '00'))
        } else {
            //si no es el caso anterior entonces se eliminara el AM
            militaryHour = console.log(hourDeleteAMPM)
        }

    }

    if (separateHour[2].includes('PM')) {

        if (separateHour[0] === '01') {

            militaryHour = console.log(hourDeleteAMPM.replace('01', '13'))
        } else if (separateHour[0] === '02') {

            militaryHour = console.log(hourDeleteAMPM.replace('02', '14'))
        } else if (separateHour[0] === '03') {

            militaryHour = console.log(hourDeleteAMPM.replace('03', '15'))
        } else if (separateHour[0] === '04') {

            militaryHour = console.log(hourDeleteAMPM.replace('04', '16'))
        } else if (separateHour[0] === '05') {

            militaryHour = console.log(hourDeleteAMPM.replace('05', '17'))
        } else if (separateHour[0] === '06') {

            militaryHour = console.log(hourDeleteAMPM.replace('06', '18'))
        } else if (separateHour[0] === '07') {

            /* en nuestro ejemplo es desde aca que la evaluación del string es true porque el indice 0 contiene '07'
            entonces el string '07' sera remplazado por '19' dando como resultado '19:05:45' */
            militaryHour = console.log(hourDeleteAMPM.replace('07', '19'))
        } else if (separateHour[0] === '08') {

            militaryHour = console.log(hourDeleteAMPM.replace('08', '20'))
        } else if (separateHour[0] === '09') {

            militaryHour = console.log(hourDeleteAMPM.replace('09', '21'))
        } else if (separateHour[0] === '10') {

            militaryHour = console.log(hourDeleteAMPM.replace('10', '22'))
        } else if (separateHour[0] === '11') {

            militaryHour = console.log(hourDeleteAMPM.replace('11', '23'))
        } else if (separateHour[0] === '12') {

            militaryHour = console.log(hourDeleteAMPM.replace('12', '12'))
        }
    }

    return militaryHour
}

timeConversion('07:05:45PM')
```
`El resultado esperado debe ser: 19:05:45`

### Código final en HackerRank
```javascript
function timeConversion(s) {
    
    let hourDeleteAMPM = s.substring(0, 8)
    let separateHour = s.split(':')
    let militaryHour

    if (separateHour[2].includes('AM')) {

        if (separateHour[0] === '12') {
            militaryHour = hourDeleteAMPM.replace('12', '00')
        } else {
            militaryHour = hourDeleteAMPM
        }

    }

    if (separateHour[2].includes('PM')) {

        if (separateHour[0] === '01') {

            militaryHour = hourDeleteAMPM.replace('01', '13')
        } else if (separateHour[0] === '02') {

            militaryHour = hourDeleteAMPM.replace('02', '14')
        } else if (separateHour[0] === '03') {

            militaryHour = hourDeleteAMPM.replace('03', '15')
        } else if (separateHour[0] === '04') {

            militaryHour = hourDeleteAMPM.replace('04', '16')
        } else if (separateHour[0] === '05') {

            militaryHour = hourDeleteAMPM.replace('05', '17')
        } else if (separateHour[0] === '06') {

            militaryHour = hourDeleteAMPM.replace('06', '18')
        } else if (separateHour[0] === '07') {

            militaryHour = hourDeleteAMPM.replace('07', '19')
        } else if (separateHour[0] === '08') {

            militaryHour = hourDeleteAMPM.replace('08', '20')
        } else if (separateHour[0] === '09') {

            militaryHour = hourDeleteAMPM.replace('09', '21')
        } else if (separateHour[0] === '10') {

            militaryHour = hourDeleteAMPM.replace('10', '22')
        } else if (separateHour[0] === '11') {

            militaryHour = hourDeleteAMPM.replace('11', '23')
        } else if (separateHour[0] === '12') {

            militaryHour = hourDeleteAMPM.replace('12', '12')
        }
    }

    return militaryHour
}
```