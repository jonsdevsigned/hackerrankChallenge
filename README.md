# Mi Repositorio de Ejercicios

Este repositorio contiene ejercicios resueltos en diferentes lenguajes de programación.

## Ejercicio 1: Simple Array Sum

Descripción del ejercicio: Sumar los números en un array.

### Código

\```javascript
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
\```

El resultado esperado debe ser: 55
