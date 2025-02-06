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
    
    for (let n=1; n<=userNum; n++) {
        arrayNum.push(n)
    }
    
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

    if (comparation === true) {

        for (let i = 0; i < a.length; i++) {

            console.log(`Comparacion ${i + 1}: Alice tiene ${a[i]} y Bob ${b[i]}`)

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
`El array de puntuación es: [2,1]`