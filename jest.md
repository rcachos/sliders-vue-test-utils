[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
# Jest

## Instalación

Para lanzar tests sobre nuestro código es necesario tener instalado [Jest], bien a nivel de proyecto o a nivel global, junto con el plugin de babel para Jest.

```bash
# Install Jest framework and utils
$ npm install --save-dev jest babel-jest
$ npm install --global jest
```



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
Además, si queremos lanzar los tests sobre componentes de *Vue.js* debemos tener instalado el paquete [@vue/test-utils] entre otros.

```bash
# Install vue test utils
$ npm install --save-dev @vue/test-utils vue-jest jsdom jsdom-global
```

> Si hemos inicializado el proyecto usando el Vue CLI, para configurar los tests debería ser suficiente con lanzar `vue add @vue/unit-jest`



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
## 1. Comandos básicos de Jest

A la hora de lanzar los tests desde el terminal, [Jest] ofrece un [CLI] con una serie de comandos y opciones para ello.

```bash
# Run tests
$ jest <filename/pattern> # Jest ods-btn

# Run tests and collect coverage
$ jest --coverage <filename/pattern>

# Run tests and watch for changes
$ jest -watch --coverage <filename/pattern>
```



 Si no se especifica se lanzarán todos los tests que encuentre jest dentro de nuestro proyecto. No es necesario especificar el archivo que se quiere testear, pero puede resultar útil si queremos testear un único componente.



 [Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
Es recomendable dar de alta estos comandos en el `package.json` de nuestro proyecto mediante un alias para tenerlos más accesibles:

 ```javascript
 {
   ...,
   "scripts": {
     ...,
     "unit": "jest --coverage",
     "unit:only": "jest",
     "unit:watch": "jest --watch --coverage"
   },
 }
 ```

> La documentación del CLI de Jest puede encontrarse en [este enlace][CLI]



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
## 2. Configuración básica de Jest

Jest se configura mediante un archivo de [configuración] con el nombre `jest.config.js` que se encuentra en el directorio raíz del componente.

Se trata de un archivo de configuración que exporta un objeto con las distintas opciones que ofrece Jest para configurar su funcionamiento.



Una **configuración básica** para [Jest] tendrá esta forma:

```javascript
// jest.config.js
const path = require('path')
module.exports = {
  rootDir: 'src',
  moduleFileExtensions: ['js'],
  moduleNameMapper: {
    '^@/(.*)$': '<rootDir>/$1',
  },
  transform: {
    '^.+\\.js$': 'babel-jest',
  },
  testRegex: '\\.spec\\.js$',
  testPathIgnorePatterns: [ 'ignore' ],
  coverageDirectory: path.resolve(__dirname, 'reports/unit/coverage'),
  collectCoverageFrom: [
    '**/*.js',
    '!**/node_modules/**',
    '!ignore/**/*.js'
  ],
  verbose: true,
}
````



### Opciones básicas

- `rootDir`

  Path al directorio raíz que utilizará Jest como punto de partida para escanear los archivos que queramos testear. En nuestro caso, todo el código debería encontrarse dentro del diretorio `/src` por lo que podremos configurarlo como `rootDir`.

  > Podemos referenciar esta ruta en el archivo de configuración usando `<rootDir>`.



- `moduleFileExtensions`

  Array con las extensiónes de los archivos de nuestro proyecto. En este caso se especifica que se lanzen tests únicamente para archivos con extensión `.js`.



- `moduleNameMapper`

  Nos permite definir alias para las rutas que utilicemos dentro de nuestros tests. En este caso, cualquier ruta que empiece por `@` sera resuelta a partir del directorio raíz, que en nuestro caso es el directorio `src`.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
- `transform`

  Nos permite definir el path a los compiladores que pueden transformar nuestro código antes de ejecutar los tests, como puede ser [Babel]. En nuestro caso especificamos que los archivos con extensión `.js` pasen por el plugin [babel-jest].



- `testRegex`

  Esta configuración se utiliza para definir la expresión regular que utilizará [Jest] para buscar los archivos en los que se encuentran los tests. En nuestro caso utilizaremos archivos con la forma `<nombre del componente>.spec.js` para escribir los tests de cada componente en concreto, por lo que la regex será `\\.spec\\.js$`.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
- `testPathIgnorePatterns`

  Array con expresiones regulares que se comparan contra todos los archivos que encuentra [Jest] dentro del directorio raíz para determinar si debe lanzar o no el test.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
- `coverageDirectory`

  Ruta del directorio donde [Jest] debe almacenar los resultados de cobertura de los tests.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
- `collectCoverageFrom`

  Array con las rutas donde [Jest] debe analizar archivos para determinar la cobertura.



- `verbose`

  Al poner esta configuración a `true` conseguimos una descripción más detallada de los resultados de las ejecuciones de los tests.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
> La lista completa de opciones de configuración de Jest puede encontrarse en [este enlace][configuración]



## 3. Lanzar un test e interpretar los resultados

Cuando se ejecuta un test se pueden visualizar los resultados en la terminal y hay que saber interpretar los datos que se aparecen.

```sh
> test-course@1.0.0 unit /.../front:ux/test-course
> jest --coverage

 FAIL  src/functions/functions.spec.js
  Multiply function test cases
    ✓ Multiply function returns the result of multiplying the arguments (2ms)
    ✓ Multiply function returns 80 when passing [10, 2, 4] as arguments
    ✓ Multiply function returns -100 when passing [-5, 20] as arguments
    ✓ Multiply function returns undefined if no arguments are passed
  Divide function test cases
    ✓ Divide function returns the result of dividing the arguments
    ✓ Divide function returns 2 when passing [80, 4, 10] as arguments
    ✓ Divide function returns -1 when passing [-10, 10] as arguments
    ✕ Divide function returns undefined if no arguments are passed (2ms)
  Sum function test cases
    ✓ Sum function returns the result of adding the arguments
    ✓ Sum function returns 94 when passing [80, 4, 10] as arguments
    ✓ Sum function returns -8 when passing [-10, 2] as arguments
    ✓ Sum function returns undefined if no arguments are passed
  Compute function test cases
    ✓ Compute function calls the callback function passed as an argument (1ms)
    ✓ Compute function calls the callback function passing on the arguments (1ms)
    ✓ Compute function returns the callback result

  ● Divide function test cases › Divide function returns undefined if no arguments are passed

    expect(received).toBeUndefined()

    Received: null

      41 |   test('Divide function returns undefined if no arguments are passed', () => {
      42 |     const result = divide()
    > 43 |     expect(result).toBeUndefined()
         |                    ^
      44 |   })
      45 |
      46 | })

      at Object.<anonymous> (functions/functions.spec.js:43:20)

-------------|----------|----------|----------|----------|-------------------|
File         |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Lines   |
-------------|----------|----------|----------|----------|-------------------|
All files    |    93.75 |       90 |      100 |      100 |                   |
 functions.js|    93.75 |       90 |      100 |      100 |                17 |
-------------|----------|----------|----------|----------|-------------------|
Test Suites: 1 failed, 1 total
Tests:       1 failed, 14 passed, 15 total
Snapshots:   0 total
Time:        1.109s
Ran all test suites.

```



En este caso se está lanzando una sola suite de tests. Una suite es un archivo donde hemos definido una serie de tests para un componente. En este caso se trata de un archivo con el nombre `functions.js` donde se encuentran varias funciones (`multiply`, `divide`, `sum` y `compute`).

Para cada función se han definido una serie de tests que comprueban que éstas funcionan como se espera que funcionen.

La lista de checks muestra los resultados de los distintos tests, y debajo se da información de aquellos tests que han fallado y el motivo por el cual lo han hecho. En este caso, el test `Divide function returns undefined if no arguments are passed` ha fallado, ya que se esperaba que para las condiciones del test la función devolviera `undefined` y esta ha devuelto `null`.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
A la derecha de los títulos de los tests se muestra el tiempo que ha tardado [Jest] en ejecutar cada uno de ellos. Es importante que este tiempo no sea excesivo, ya que a la hora de desplegar nuestra aplicación se lanzarán todos los tests y puede llevar varios minutos terminar de comprobar el código. Si algún test tiene un tiempo elevado habrá que considerar refactorizarlo para simplificarlo.

La tabla de la parte inferior muestra el **nivel de cobertura** de nuestro código. Esto no tiene nada que ver con cómo funciona el código, pero nos indica qué partes de éste no han sido ejecutadas durante el test (por lo que no sabemos si realmente funcionan o no).



Las categorías que evalua la **cobertura** son:

- **Statements** - `% Stmts`

  Cobertura sobre las órdenes que aparecen en nuestro código. Se comprueba cuales han sido interpretadas y se divide entre el número total de órdenes.

- **Branches** - `% Branch`

  Cobertura sobre las ramas de nuestro código. Cada vez que utilizamos un condicional (un `if` o un `switch` por ejemplo) se generan una o varias ramas. Este indicador se encarga de avisarnos si nos hemos dejado condiciones sin contemplar.




- **Functions** - `% Funcs`

  Porcentaje de las funciones que aparecen en nuestro código que han sido invocadas durante los tests.

- **Lines** - `% Lines`

  Porcentaje de líneas que han sido interpretadas durante los tests. La diferencia entre este indicador y el de *Statements* está en que hay casos en los que en una línea se interpreta más de una órden.

  Por ejemplo, para el siguiente caso, si nuestro test no contempla el caso en que `value` sea `falsy`, la línea será interpretada, (por lo que la cobertura en líneas puede alcanzar el 100%), pero el statement `return false` no llega a ejecutarse (por lo que la cobertura en statements no podrá alcanzar el 100%).

  ```javascript
  if (!value) return false
  ```



## 4. Métodos `describe()` y `test()`

Para explicar la estructura que tiene un archivo de tests vamos a utilizar la función `multiply` del módulo `functions` que genera el resultado del apartado anterior. Se trata de una función que toma `n` argumentos y devuelve el resultado de multiplicarlos. Si no se pasan argumentos, devolverá `undefined`.

```javascript
function multiply(...values) {
  if (!values.length) return undefined
  return values.reduce((result, value) => result * value)
}
```



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
### Describe

Como el archivo `functions.js` tiene varios métodos y queremos probar la funcionalidad de cada uno por separado, resulta útil dividir la suite de tests en diferentes secciones. Para ello se utiliza el método `describe()` de [Jest].

Este método genera un contexto para la ejecución de uno o más tests. Además de agrupar los resultados de estos tests nos permite controlar cómo se comporta el entorno de la función que estamos probando de forma independiente al resto de funciones que probemos en este archivo (inicializar variables, crear funciones de ayuda, etc.).

Es el método encargado de generar un contexto para la ejecución de nuestros tests. No es necesario, pero generalmente ayuda a estructurar el archivo y a simplificar los tests.

> La documentación del método `describe()` puede encontrarse en [este enlace][describe]



### Test

El método `test()` es el encargado de comprobar el comportamiento de las funciones que queremos testear. Es el único método realmente necesario para que podamos testear nuestro código.

Recibe como primer argumento el nombre del test y como segundo una función que contiene nuestras expectativas acerca del comportamiento que queremos probar. La definición de estas expectativas se detalla en el siguiente apartado.




[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
```javascript
import { multiply } from './functions.js'

describe('Multiply function test cases', () => {
  test('Multiply function returns the result of multiplying the arguments', () => {
    // ...
  })
  test('Multiply function returns undefined if no arguments are passed', () => {
    // ...
  })
})
```

> La documentación del método `test()` puede encontrarse en [este enlace][test]



## 5. Método `expect()` y sus funciones

Para definir las expectativas que tenemos acerca del comportamiento de una función se hace uso del método `expect()`. Generalmente invocamos a la función que tenemos que testear en diferentes escenarios y con diferentes argumentos y condiciones, y **esperamos** que el resultado sea uno.

Para el caso de la función `multiply` esperamos que al utilizarla con unos argumentos determiandos, el resultado sea la multiplicación de estos argumentos. El test que contempla este caso se escribiría de la siguiente manera:

```javascript
test('Multiply function returns the result of multiplying the arguments', () => {
  const a = 10, b = 2
  const result = multiply(a, b)
  expect(result).toBe(20)
})
```




[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
Declaramos dos constantes conocidas (**10** y **2**) y las utilizamos como argumentos de la función `multiply`. Almacenamos el resultado de llamar a esta función en `result` y comprobamos que se cumple nuestra **espectativa** de que el resultado sea **20**. Para ello utilizamos el método `.toBe()` que compara el argumento de `expect()` contra el argumento que recibe.

> Una lista completa de los métodos que acompañan a `expect()` puede encontrarse en [este enlace][expect].




Como el comportamiento de esta función es bastante simple puede parecer que el testeo está terminado. Podemos comprobarlo corriendo los tests para esta suite con la opción `watch` por si es necesario hacer algún cambio:

```bash
$ npm run unit:watch functions
```

El resultado de esta ejecución es:

```bash
> test-course@1.0.0 unit /.../front:ux/test-course
> jest --coverage

 PASS  src/functions/functions.spec.js
  Multiply function test cases
    ✓ Multiply function returns the result of multiplying the arguments (2ms)

-------------|----------|----------|----------|----------|-------------------|
File         |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Lines   |
-------------|----------|----------|----------|----------|-------------------|
All files    |       80 |       50 |      100 |      100 |                   |
 functions.js|       80 |       50 |      100 |      100 |                 2 |
-------------|----------|----------|----------|----------|-------------------|
Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        1.424s
```



Como se puede ver en los resultados la cobertura no llega al 100%, por lo que puede haber partes de la función que no hemos probado que estén funcionando de forma incorrecta. El reporte de cobertura nos indica que faltan la mitad de las ramas por probar, y que aunque se han ejecutado todas las líneas, algún comando no ha sido interpretado, ya que marca un 80% en `Stmts`. También nos indica en qué linea faltan comandos por probar.

Volviendo a esa línea en el código de la función podemos ver que no hemos contemplado en nuestros tests el caso en que la función no reciba argumentos. Para este caso la función debe devolver `undefined`. Necesitamos un nuevo test que contemple este escenario:

```javascript
test('Multiply function returns undefined if no arguments are passed', () => {
  const result = multiply()
  expect(result).toBeUndefined()
})
```



Para comprobar que el resultado es `undefined` podemos utilizar el método `toBeUndefined()` que equivaldría a `toBe(undefined)`.

Con estos dos tests alcanzamos una cobertura del 100%, pero aunque estemos probando todos los escenarios, los casos no son suficientemente representativos y puede que la función no se esté comportando como esperamos a pesar de pasar los tests y tener una cobertura del 100%.

Pongamos por ejemplo esta modificación de la función `multiply`:

```javascript
function multiply(...values) {
  if (!values.length) return undefined
  return 20
}
```

Pasaría los tests que hemos programado sin problema, todas las líneas serían interpretadas y todos los statements evaluados, pero no cumple la función de multiplicar los argumentos que recibe.



Para conseguir una suite de tests más robusta podemos probar con diferentes argumentos la función `multiply` para demostrar que devuelve el resultado de multiplicarlos sean cuales sean estos argumentos. Para tests repetitivos de este tipo existe el método `test.each()` que nos permite lanzar el mismo test para distintos conjuntos de argumentos.

```javascript
test.each([
  [80, [ 10, 2, 4 ]],
  [-100, [ -5, 20 ]],
])('Multiply function returns %i when passing %p as arguments', (expected, values) => {
  const result = multiply(...values)
  expect(result).toBe(expected)
})
```

Ahora podemos como argumento de `test.each()` una tabla (o un array de arrays) que será lo que reciba la función de callback del método `test()` como argumentos ordenados. En nuestro caso, el primer elemento del array es el resultado que esperamos cuando los argumentos de `multiply` son los valores del segundo elemento del array. Podemos probar de esta forma que para distintos valores de entrada, la función se comporta como debería.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
De hecho podríamos utilizar este mismo test para eliminar el test anterior y comprobar que devuelve undefined cuando no recibe argumentos si añadimos ese caso al array:

```javascript
test.each([ ..., [ undefined, [] ] ])(...) // expected -> undefined; values -> []
```

> Puede encontrarse más información acerca del método `test.each()()` en [este enlace][test-each]

Con este nuevo test, el método `multiply` modificado no pasaría todos los tests, y veríamos que realmente no funciona. Al corregir el método y dejarlo como estaba inicialmente podemos ver que pasa correctamente la suite 🎉



```bash
> test-course@1.0.0 unit /.../front:ux/test-course
> jest --coverage

 PASS  src/functions/functions.spec.js
  Multiply function test cases
    ✓ Multiply function returns the result of multiplying the arguments (2ms)
    ✓ Multiply function returns 80 when passing [10, 2, 4] as arguments
    ✓ Multiply function returns -100 when passing [-5, 20] as arguments
    ✓ Multiply function returns undefined if no arguments are passed

-------------|----------|----------|----------|----------|-------------------|
File         |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Lines   |
-------------|----------|----------|----------|----------|-------------------|
All files    |      100 |      100 |      100 |      100 |                   |
 functions.js|      100 |      100 |      100 |      100 |                   |
-------------|----------|----------|----------|----------|-------------------|
Test Suites: 1 passed, 1 total
Tests:       4 passed, 4 total
Snapshots:   0 total
Time:        1.071s
Ran all test suites.
````



## 6. Funciones mockeadas `jest.fn()`

Es común encontrarse en la implementación de funciones, llamadas a otras funciones. Para que al testear las funciones de primer nivel dependemos de que las funciones que se invocan en el cuerpo de esta funcionen correctamente. Al tratarse de tests unitarios, esta dependencia debería tratar de eliminarse, ya que las funciones deberían poder probarse de forma completamente aislada.

Para ello debemos simular el funcionamiento de las funciones de las que depende la funcion objetivo utilizando el compotamiento que esperamos de estas, y no el que están teniendo (que puede ser erróneo).

Además de simular este funcionamiento podemos comprobar que estas funciones han sido invocadas desde la función de primer nivel.



Para esto es necesario utilizar las [jest mock functions] `jest.fn()`. Estas son funciones especiales que almacenan un estado y una historia acerca de cómo son invocadas, por quién, cuántas veces, con qué argumentos, etc.

Definiendo estas funciones y sustituyendo las que realmente se utilizan podemos testear el comportamiento de una función independientemente de cómo se comporten las funciones de las que depende.

En nuestro ejemplo vamos a considerar la función `compute()`:

```javascript
function compute(callback, ...values) {
  if (!callback || typeof callback !== 'function') return undefined
  return callback(...values)
}
```

Se trata de una función que toma otra función cómo argumento y se encarga de invocarla con los argumentos que recibe.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
Cómo primer test se nos puede ocurrir comprobar que la función pasada como argumento es invocada al invocar la función `compute()`. Si pasamos una función cualquiera, no tendremos forma de detectar si ha sido invocada, sin embargo, utilizando una `jest.fn()` podemos a posteriori ver su estado y comprobarlo.

```javascript
test('Compute function calls the callback function passed as an argument', () => {
  const callback = jest.fn()
  const result = compute(callback)
  expect(callback).toHaveBeenCalled()
})
```

Mediante el método `.toHaveBeenCalled()`, específico de las `jest.fn()`, podemos hacer que el test pase cuando [Jest] detecte que la función pasada como argumento haya sido invocada al menos una vez.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
Sin embargo, este test no demuestra que nuestra función se comporta como queremos. Sabemos que invoca a la función que recibe como parámetro, pero si no le pasa los argumentos correspondientes no hace lo que queremos que haga. Este test también daría un resultado positivo para esta modificación de la función `compute()`, ya que la función callback ha sido invocada:

```javascript
function compute(callback, ...values) {
  if (!callback || typeof callback !== 'function') return undefined
  return callback()
}
```

> Puede encontrarse la documentación acerca del método `.toHaveBeenCalled()` en [este enlace][toHaveBeenCalled].



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
Las `jest.fn()` además de permitirnos comprobar que han sido invocadas nos permiten ver qué argumentos han recibido. Para ello se utiliza el métido `.toHaveBeenCalledWith()`, al que se le pasan los argumentos que debería haber recibido la función.

```javascript
test('Compute function calls the callback function passing on the arguments', () => {
  const a = 10, b = 2
  const callback = jest.fn()
  const result = compute(callback, a, b)
  expect(callback).toHaveBeenCalledWith(a, b)
})
```

En nuestro caso podemos comprobar que al llamar a la función de primer nivel con los argumentos `a` y `b`, la función que se invoca internamente también se llama con esos mismos argumentos.

> Puede encontrarse la documentación acerca del método `.toHaveBeenCalledWith()` en [este enlace][toHaveBeenCalledWith].



Generalente el resultado de estas funciones invocadas internamente se utiliza dentro de la función de primer nivel, por lo que si queremos comprobar que funciona correctamente debemos simular el comportamiento de estas funciones internas para que no rompa el funcionamiento de la función que estamos probando.

En nuestro caso, como el resultado de la función de primer nivel es el resultado de la implementación de la función interna, podemos simular cualquier implementación y comprobar que la función que estamos probando implementa esa funcionalidad.

```javascript
test('Compute function returns the callback result', () => {
  const a = 10, b = 2
  const callback = jest.fn((a, b) => `${a}, ${b}`)
  const result = compute(callback, a, b)
  expect(result).toBe('10, 2')
})
```

Podemos por ejemplo comprobar que al pasar una función que devuelve los dos argumentos concatenados como una string, la función de primer nivel replica este funcionamiento.



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
> Otra forma de simular la implementación de una función de jest es utilizar el método `.mockImplementation()`. Puede encontrarse la documentación acerca de este método en [este enlace][mockImplementation].

Por último quedaría cubrir la línea que comprueba si la función de callback no es una función devolviendo `undefined` con lo que completaríamos la suite para la función `compute()`.

```javascript
test('When callback is not a function Compute returns undefined', () => {
  const a = 10, b = 2
  const result = compute('not a function', a, b)
  expect(result).toBeUndefined()
})
```

El resultado completo de la suite sería el siguiente 🎉:



```bash
> test-course@1.0.0 unit /.../front:ux/test-course
> jest --coverage

 PASS  src/functions/functions.spec.js
  Multiply function test cases
    ✓ Multiply function returns the result of multiplying the arguments (3ms)
    ✓ Multiply function returns 80 when passing [10, 2, 4] as arguments
    ✓ Multiply function returns -100 when passing [-5, 20] as arguments (1ms)
    ✓ Multiply function returns undefined if no arguments are passed
  Divide function test cases
    ✓ Divide function returns the result of dividing the arguments (1ms)
    ✓ Divide function returns 2 when passing [80, 4, 10] as arguments
    ✓ Divide function returns -1 when passing [-10, 10] as arguments
    ✓ Divide function returns undefined if no arguments are passed (1ms)
  Sum function test cases
    ✓ Sum function returns the result of adding the arguments
    ✓ Sum function returns 94 when passing [80, 4, 10] as arguments (1ms)
    ✓ Sum function returns -8 when passing [-10, 2] as arguments
    ✓ Sum function returns undefined if no arguments are passed
  Compute function test cases
    ✓ Compute function calls the callback function passed as an argument (1ms)
    ✓ Compute function calls the callback function passing on the arguments (1ms)
    ✓ Compute function returns the callback result (1ms)
    ✓ When callback is not a function Compute returns undefined

-------------|----------|----------|----------|----------|-------------------|
File         |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Lines   |
-------------|----------|----------|----------|----------|-------------------|
All files    |      100 |      100 |      100 |      100 |                   |
 functions.js|      100 |      100 |      100 |      100 |                   |
-------------|----------|----------|----------|----------|-------------------|
Test Suites: 1 passed, 1 total
Tests:       16 passed, 16 total
Snapshots:   0 total
Time:        0.984s, estimated 1s
Ran all test suites.
```



[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
## 7. Métodos de Jest más utilizados

[Jest] ofrece muchos más métodos de los que se muestran en esta sección y pueden encontrarse descripciones y ejemplos en la [documentación oficial][Jest], pero los más comunes son los siguientes:

```javascript
/* GLOBALS (https://jestjs.io/docs/en/api) */
describe('name', () => {})
test('name', () => {}, timeout)
test.each(cases)('name', () => {}, timeout)
beforeAll(() => {}, timeout)
beforeEach(() => {}, timeout)

/* EXPECT (https://jestjs.io/docs/en/expect) */
expect().toBe()
expect().toBeUndefined()
expect().toBeNull()
expect().toBeTruthy()
expect().toEqual() // used with objects
expect().not.toBe()
expect().toHaveBeenCalled() // used with mocks
expect().toHaveBeenCalledWith() // used with mocks
expect().toHaveReturned() // used with mocks

/* MOCKS (https://jestjs.io/docs/en/mock-function-api) */
jest.fn()
jest.fn().mockImplementation(() => {})
jest.fn().mockReturnValue(value)
jest.fn().mockClear()
jest.fn().mockReset()
jest.fn().mockRestore()
```

[Jest]: https://jestjs.io/en/
[CLI]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[configuración]: https://jestjs.io/docs/en/configuration
[Babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[toHaveBeenCalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[toHaveBeenCalledWith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockImplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
# Vue Test Utils

## Instalación

Si hemos inicializado nuestro proyecto utlizando el cli de Vue debería ser suficiente con instalar el paquete y extender nuestro proyecto haciendo uso de los comandos que  nos ofrece:

```bash
$ npm install --save-dev @vue/test-utils
$ vue add @vue/unit-jest
```

> Si esto da problemas se pueden seguir las [instrucciones] de la documentación oficial de Vue Test Utils.




[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
## Configuración avanzada de Jest

También es necesario añadir una serie de modificaciones en el archivo de configuración de [Jest] para que interprete correctamente nuestros tests y sea capaz de probar los componentes cuando son _Single File Components_.

```diff
  module.exports = {
    rootDir: 'src',
-   moduleFileExtensions: ['js'],
+   moduleFileExtensions: ['js', 'vue'],
    moduleNameMapper: {
      '^@/(.*)$': '<rootDir>/$1',
    },
    transform: {
      '^.+\\.js$': 'babel-jest',
+     '.*\\.(vue)$': 'vue-jest',
    },
    testRegex: '\\.spec\\.js$',
    testPathIgnorePatterns: [ 'functions' ],
    coverageDirectory: path.resolve(__dirname, 'reports/unit/coverage'),
-   collectCoverageFrom: ['**/*.js', '!**/node_modules/**', '!functions/**/*.js'],
+   collectCoverageFrom: ['**/*.{js,vue}', '!**/node_modules/**', '!functions/**/*.js'],
    verbose: true,
  }
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
-   `moduleFileExtensions`

    Debemos añadir la extensión `.vue` para que [Jest] lance también los tests relacionados con los archivos de nuestros componentes.

-   `transform`

    Para que [Jest] sea capaz de interpretar el código escrito en los componentes es necesario que [vue-jest] transpile estos archivos.

-   `collectCoverageFrom`

    Debemos añadir también la extensión `.vue` a la expresión que utiliza [Jest] para determinar la cobertura, de manera que nuestros componentes sean analizados.



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
## Estructura de los archivos de Test

Si hemos configurado correctamente nuestro entorno de test, [Jest] se encargará de buscar los archivos correspondientes a la hora de lanzar los tests, por lo que es indiferente dónde dejemos estos archivos siempre y cuando estén dentro del scope que declaramos en la [configuración] de [Jest]. Se recomienda guardar los archivos de test junto con el archivo `.vue` del componente al que hacen referencia dentro de un mismo directorio bajo el nombre del componente. De esta forma tendremos los tests y los archivos del componente almacenados en un mismo directorio facilitando compartir nuestro componente y saber si dispone de tests o no.

    - src
      - components
        - componentA
          - ComponentA.vue
          - ComponentA.spec.js
        - componentB
          - ComponentB.vue
          - ComponentB.spec.js




Los tests pueden estructurarse de muchas formas distintas, pero recomendamos agrupar los distintos tests en función de qué propiedad del componente estamos probando. Además es recomendable seguir el mismo orden que tienen estas propiedades dentro de nuestros componentes:

```js
import Vue from 'vue'
import { shallowMount, createLocalVue } from '@vue/test-utils'
import Component from './Component'

describe('Component test suite', () => {

  /* TEMPLATE RELATED TESTS */
  describe('Template rendering', () => {
    // ...
  })

  /* DATA RELATED TESTS */
  describe('Data and Props', () => {
    // ...
  })

  /* COMPUTED PROPERTIES RELATED TESTS */
  describe('Computed properties', () => {
    describe('Computed property A', () => {
      // ...
    })
    // ...
  })

  /* LIFECYCLE HOOKS RELATED TESTS */
  describe('Lifecycle hooks', () => {
    describe('Created hook', () => {
      // ...
    })
    // ...
  })

  /* METHODS RELATED TESTS */
  describe('Methods', () => {
    describe('Method A', () => {
      // ..
    })
    // ...
  })

})
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
> Se pueden encontrar snippet con versiones para VSCode y Atom para inicializar los archivos de test con esta estructura [aquí](../../snippets)




[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
## Métodos `mount()` y `shallowMount()`

### Mount

Crea un Wrapper que contiene el componente Vue montado y renderizado.

Ejemplo sin opciones:

```javascript
test('renders a button', () => {
  const wrapper = mount(Button)
  expect(wrapper.contains('button')).toBe(true)
})
```

Ejemplo sin con opciones:

```javascript
test('renders a button', () => {
  const wrapper = mount(Button, {
    propsData: {
      size: 'medium'
    }
  })
  expect(wrapper.contains('button')).toBe(true)
})
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
> Puede encontrar más ejemplos y documentación más detallada del metodo  `mount()` en [este enlace][vue mount].



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
### ShallowMount

Al igual que `mount()`, crea un Wrapper que contiene el componente Vue montado y renderizado, pero con los componentes hijos están simulados, es decir no los monta realmente, con esto se evita que no se ejecute el codigo de los componetes hijos lo cual evita muchos problemas en el test. Ya que normalmente solo se quiere testear el componente y los componentes hijos tendran por su parte sus propios test.

Ejemplo sin opciones:

```javascript
test('renders a button', () => {
  const wrapper = shallowMount(Button)
  expect(wrapper.contains('button')).toBe(true)
})
```

Ejemplo sin con opciones:

```javascript
test('renders a button', () => {
  const wrapper = shallowMount(Button, {
    propsData: {
      size: 'medium'
    }
  })
  expect(wrapper.contains('button')).toBe(true)
})
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
> Puede encontrar más ejemplos y documentación más detallada del metodo  `shallowMount()` en [este enlace][vue shallowmount].




[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
### Principales Opciones
Opciones par mount y shallowMount
#### propsData
Setea las props del componente al montarlo.

```javascript
const Component = {
  template: '<div>{{ msg }}</div>',
  props: ['msg']
}
const wrapper = mount(Component, {
  propsData: {
    msg: 'aBC'
  }
})
expect(wrapper.text()).toBe('aBC')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### mocks
Agregue propiedades adicionales a la instancia. Útil para reemplazar metodos globales que en el momento del test no queramos que ejecuten el verdadero codigo. Tambien es útil para reemplazar metedos globlaes por otras funciones o por jest.fn que luengo espiemos para comprobar que estos se han llamado en nuestro código pero sin ejecutar el verdaderó código. Por ejemplo aquí podriamos reemplazar el i18n para que devuela un texto, el \$route para las rutas o el \$emit por un jest.fn para comprobar que es llamado y con que parametros se le llama.
(Muy util si estas llamadas o acceso a propiedades estan el el mounted o created del componente)
En mocks no podemos reemplazar los methods del propio componentes para ella usaríamos la propiedad methods.

```javascript
const $route = { path: 'http://www.example-path.com' }
const wrapper = shallowMount(Component, {
  mocks: {
    $route
  }
})
expect(wrapper.vm.$route.path).toBe($route.path)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### methods
Si en algun test necesitamos reemplazar un metodo del propio componente se haría con la propiedad methods.

```javascript
const Component = {
  template: '<div>{{ foo() }}{{ bar() }}{{ baz() }}</div>',
  methods: {
    foo() {
      return 'a'
    },
    bar() {
      return 'b'
    }
  }
}
const options = {
  methods: {
    bar() {
      return 'B'
    },
    baz() {
      return 'C'
    }
  }
}
const wrapper = mount(Component, options)
expect(wrapper.text()).toBe('aBC')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### data
Para pasar valores del data en el montado del componete, estos se fusionaran con los ya existenes. Es decir cambiara el valor del data del componente si exite y si no lo creara.

```javascript
const Component = {
  template: `
    <div>
      <span id="foo">{{ foo }}</span>
      <span id="bar">{{ bar }}</span>
    </div>
  `,

  data() {
    return {
      foo: 'foo',
      bar: 'bar'
    }
  }
}

const wrapper = mount(Component, {
  data() {
    return {
      bar: 'my-override'
    }
  }
})

wrapper.find('#foo').text() // 'foo'
wrapper.find('#bar').text() // 'my-override'
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### propsData
Setear las propiedades del componente en el momento del montado.

```javascript
const Component = {
  template: '<div>{{ msg }}</div>',
  props: ['msg']
}
const wrapper = mount(Component, {
  propsData: {
    msg: 'aBC'
  }
})
expect(wrapper.text()).toBe('aBC')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### localVue
Una copia local de vue creada con [`createLocalVue`][createLocalVue] para usarla al montar el componente. Es útil para instalar plugins de vue que solo usa esta componente en esta copia, ya que de esta forma no vamos ensuciando la instancia de vue global que comparten todos los componentes.

```javascript
import { createLocalVue, mount } from '@vue/test-utils'
import VueRouter from 'vue-router'
import Foo from './Foo.vue'

const localVue = createLocalVue()
localVue.use(VueRouter)

const routes = [{ path: '/foo', component: Foo }]

const router = new VueRouter({
  routes
})

const wrapper = mount(Component, {
  localVue,
  router
})
expect(wrapper.vm.$route).toBeInstanceOf(Object)
````



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### attachToDocument
* type: `boolean`
* default: `false`

Para setear si el componente puede atacar al DOM en el momento de montarlo.
Cuando se activa atacar al DOM, se debe llamar a `wrapper.destroy()` al terminar el test para eliminar los elementos del DOM renderizados y la instancia del componente.



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### slots
* tipo: `{ [name: string]: Array<Component>|Component|string }`

Provide an object of slot contents to the component. The key corresponds to the slot name. The value can be either a component, an array of components, or a template string, or text.
Agrega un objeto de slot al componente. La key corresponde al nombre del slot. El valor puede ser otro componente, un array de componentes, un template string o un texto.




```javascript
<template lang="pug">
  doctype html
  ods-module.module-action
    div(slot="header", class="module-action__header")
      h2.module-action__title(ref="title") {{ title }}
      ods-button(
        v-if="actionButton",
        type="secondary",
        size="small",
        ref="actionButton",
        @click="$emit('action')",
        :disabled="disabledButton") {{ textActionButton }}
    template
      slot
</template>
```
```javascript
import { shallowMount } from '@vue/test-utils'
import ModuleActionBtn from '@/components/ModuleActionBtn'

describe('ModuleActionBtn', () => {

test('if render slot content', () => {
    const textCheckedSlot = 'slot content'
    const wrapper = mount(ModuleActionBtn, {
      slots: {
        default: `<p>${textCheckedSlot}</p>`
      }
    })
    expect(wrapper.text()).toContain(textCheckedSlot)
  })
})
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### resto de propiedades
Hay más propiedades para configurar el componente en el momento del montado para poder verlas todas accede a la sección de propiedades en la docuentación de vue-test-util desde este
[enlace][mounting options].




[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
## wrapper
`Wrapper` es un objeto que contiene un componente montado o un vnode con sus metodos para testear el componente o el vnode.

### Propiedades

#### vm
`Component` (solo lectura): es la instancía de `Vue`. Se puede acceder a todos los metodos y porpiedades de la instancia con `wrapper.vm`. Esta instancia solo existe en el wrapper del componente Vue.

#### element
`HTMLElement` (solo lectura): el nodo DOM raiz del wrapper.




[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
### Metodos

#### attributes
Devuelve los atributos del nodo del DOM del `wrapper`. Si  se le pasa como parametro la `key` de un atributo devolvera el valor de ese atributo.
* Argumentos:
  * `{string} key` optional
* devuelve: `{[attribute: string]: any} | string`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
expect(wrapper.attributes().id).toBe('foo')
expect(wrapper.attributes('id')).toBe('foo')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### classes
Devuelve las clases del nodo del DOM del `wrapper`.
Devuelve un array de clases si no se le pasa parametro y si se le pasa un string como parametro devueve true o false si esté esta entre las clases que contiene el DOM.

* Argumentos:
  * `{string} className` optional
* Devuelve: `Array<{string}> | boolean`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
expect(wrapper.classes()).toContain('bar')
expect(wrapper.classes('bar')).toBe(true)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### contains
Devuelve si el `wrapper` contiene o no el elemento buscado por el [selector][selector] especificado.

* Argumentos:
  * `{string|Component}`selector
* Devuelve: `{boolean}`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'
import Bar from './Bar.vue'

const wrapper = mount(Foo)
expect(wrapper.contains('p')).toBe(true)
expect(wrapper.contains(Bar)).toBe(true)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### emitted
Devuelve un objeto que contiene los eventos personalizados emitidos por `wrapper` `vm`.
* Devuelve: `{ [name: string]: Array<Array<any>> }`
```javascript
import { mount } from '@vue/test-utils'
test('emit demo', async () => {
  const wrapper = mount(Component)

  wrapper.vm.$emit('foo')
  wrapper.vm.$emit('foo', 123)

  await wrapper.vm.$nextTick() // Wait until $emits have been handled

  /*
  wrapper.emitted() returns the following object:
  {
    foo: [[], [123]]
  }
  */

  // assert event has been emitted
  expect(wrapper.emitted().foo).toBeTruthy()

  // assert event count
  expect(wrapper.emitted().foo.length).toBe(2)

  // assert event payload
  expect(wrapper.emitted().foo[1]).toEqual([123])
})
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
También se puede escribir así.
```javascript
// assert event has been emitted
expect(wrapper.emitted('foo')).toBeTruthy()

// assert event count
expect(wrapper.emitted('foo').length).toBe(2)

// assert event payload
expect(wrapper.emitted('foo')[1]).toEqual([123])
```
El método `.emitted()` devuelve el mismo objeto cada vez que se llama, no uno nuevo, por lo que el objeto se actualizará únicamente cuando se activen nuevos eventos.



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### emittedByOrder
Devuelve un array que contiene los eventos personalizados emitidos por `wrapper` `vm`.

* Devuelve: `Array<{ name: string, args: Array<any> }>`

```javascript
import { mount } from '@vue/test-utils'

const wrapper = mount(Component)

wrapper.vm.$emit('foo')
wrapper.vm.$emit('bar', 123)

/*
wrapper.emittedByOrder() returns the following Array:
[
  { name: 'foo', args: [] },
  { name: 'bar', args: [123] }
]
*/

// assert event emit order
expect(wrapper.emittedByOrder().map(e => e.name)).toEqual(['foo', 'bar'])
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### exists
Devuelve si el `Wrapper` o el `WrapperArray` existe.
* devuelve: `{boolean}`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
expect(wrapper.exists()).toBe(true)
expect(wrapper.find('does-not-exist').exists()).toBe(false)
expect(wrapper.findAll('div').exists()).toBe(true)
expect(wrapper.findAll('does-not-exist').exists()).toBe(false)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### find
Devuelve el 'Wrapper' del primer elemento del DOM o componente Vue que coincide con el [selector][selector] pasado como parametro.

* Argumentos:
  * `{string|Component}` selector
* Devuelve: `{Wrapper}`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'
import Bar from './Bar.vue'

const wrapper = mount(Foo)

const div = wrapper.find('div')
expect(div.is('div')).toBe(true)

const bar = wrapper.find(Bar)
expect(bar.is(Bar)).toBe(true)

const barByName = wrapper.find({ name: 'bar' })
expect(barByName.is(Bar)).toBe(true)

const fooRef = wrapper.find({ ref: 'foo' })
expect(fooRef.is(Foo)).toBe(true)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### findAll
Devuelve el [`WrapperArray`][WrapperArray] de los elementos que coinciden con el [selector][selector] pasado como parametro.
* Argumentos:
  * `{string|Component}` selector
* Devuelve: `{WrapperArray}`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'
import Bar from './Bar.vue'

const wrapper = mount(Foo)
const div = wrapper.findAll('div').at(0)
expect(div.is('div')).toBe(true)
const bar = wrapper.findAll(Bar).at(0)
expect(bar.is(Bar)).toBe(true)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### isEmpty
Devuelve true si el `Wrapper` no contiene hijos.
* Devuelve: `{boolean}`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
expect(wrapper.isEmpty()).toBe(true)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### isVisible
Devuelve true si el 'Wrapper' es visible.
Comprueba tambien que los elementos ancestros no tengan ni 'display: none' ni 'visibility: hidden' para chequear que el 'Wrapper' es visible.
Es útil para comprobar que se esta apliacando la directiva v-show en componentes.

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
expect(wrapper.isVisible()).toBe(true)
expect(wrapper.find('.is-not-visible').isVisible()).toBe(false)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### setData
Setea a `Wrapper` `vm` data.
`setData` usa internamente `Vue.set`
* Argumentos:
  * `{Object}` data

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
wrapper.setData({ foo: 'bar' })
expect(wrapper.vm.foo).toBe('bar')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### setMethods
Crea o sobrescribe metodos y fuerza su actualización en `Wrapper` `vn`.

* Arguments:
  * `{Object}` methods

```javascript
import { mount } from '@vue/test-utils'
import sinon from 'sinon'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
const clickMethodStub = sinon.stub()

wrapper.setMethods({ clickMethod: clickMethodStub })
wrapper.find('button').trigger('click')
expect(clickMethodStub.called).toBe(true)
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### setProps
Setea propiedeades y fuerza su actualización en `Wrapper` `vn`.

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
wrapper.setProps({ foo: 'bar' })
expect(wrapper.vm.foo).toBe('bar')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### setValue
Setea el valor de un input text o seleciona un elemento y actualiza el data asociado al v-model.

* Argumentos:
  * `{any}` value

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)

const textInput = wrapper.find('input[type="text"]')
textInput.setValue('some value')

const select = wrapper.find('select')
select.setValue('option value')
```
Ver tambien [setChecked][setChecked], [setSelected][setSelected].




[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### text
Devuelve el contenido de texto del `Wrapper`.

* Devuelve: `{string}`

```javascript
import { mount } from '@vue/test-utils'
import Foo from './Foo.vue'

const wrapper = mount(Foo)
expect(wrapper.text()).toBe('bar')
```



[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected
#### trigger
Lanza un evento asincrono del `Wrapper` DOM node.

* Argumentos:
  * `{string} eventType` requerido
  * `{Object} options` optional

```javascript
import { mount } from '@vue/test-utils'
import sinon from 'sinon'
import Foo from './Foo'

test('trigger demo', async () => {
  const clickHandler = sinon.stub()
  const wrapper = mount(Foo, {
    propsData: { clickHandler }
  })

  wrapper.trigger('click')

  wrapper.trigger('click', {
    button: 0
  })

  wrapper.trigger('click', {
    ctrlKey: true // For testing @click.ctrl handlers
  })

  await wrapper.vm.$nextTick() // Wait until trigger events have been handled

  expect(clickHandler.called).toBe(true)
})
```



## Ejemplo buscar elementos en el DOM
Para los casos en los que tenemos que interactuar con algún elemento del DOM es más seguro agregarle an atributo ref, que por una query de clases ya que es más improbable que cambiemos una referencia que una clase.




ejemplo para el tempalte:
```html
<template lang="pug">
  doctype html
  ods-module.module-action
    div(slot="header", class="module-action__header")
      h2.module-action__title(ref="title") {{ title }}
      ods-button(
        v-if="actionButton",
        type="secondary",
        size="small",
        ref="actionButton",
        @click="$emit('action')",
        :disabled="disabledButton") {{ textActionButton }}
    template
      slot
</template>
<script>
export default {

  name: 'ModuleActionBtn',

  props: {

    title: {
      type: String,
      required: true,
      default: ''
    },

    textActionButton: {
      type: String,
      default: ''
    },

    disabledButton: {
      type: Boolean,
      default: false
    }

  },

  computed: {

    actionButton () {
      return this.textActionButton !== ''
    }

  }

}
</script>
```



el test podría ser:
```javascript
import { shallowMount } from '@vue/test-utils'
import ModuleActionBtn from '@/components/ModuleActionBtn'
describe('ModuleActionBtn', () => {
  test('if actionButton is false don´t mount action button', async () => {
    const wrapper = shallowMount(ModuleActionBtn, {
      propsData: {
        textActionButton: 'test' }
      })
    wrapper.setProps({ textActionButton: '' })
    await wrapper.vm.$nextTick()
    expect(wrapper.find({ ref: 'actionButton' }).exists()).toBe(false)
  })
})

```



## Ejemplos reemplazar funcionalidades y propiedades de objetos




### Mockear propiedades de difícil acceso o control
Aquí teníamos el problema que necesitabamos acceder a un hijo del popover por referencia y no teniamos acceso por temas de como se monta el popover no sabemos cuando esta accesible etc.

```javascript
Object.defineProperty(cmp.vm, '$refs', {
  writable: true,
  value: {
    popover: {
      $refs: {
        popper: {
          style: {
            color: 'fadsfas'
          }
        }
      }
    }
  }
})
expect(cmp.vm.$refs.popover.$refs.popper.style.color).toBe('fadsfas')
cmp.vm.setColor()
expect(cmp.vm.$refs.popover.$refs.popper.style.color).toBe('pink')
```



### Probar un try catch

tenemos este código

```javascript
setColor () {
  const cell = this.$refs['status-cell']
  try {
    this.color
      ? cell.style.setProperty('--color', this.color)
      : cell.style.removeProperty('--color')
  } catch (e) {
    this.color
      ? cell.style.color = this.color
      : cell.style.color = ''
  }
}
```



Y parte de su test sería

```javascript
test('if component with the ref status-cell is enable and the color is empty and removeProperty faild', () => {
    const wrapper = shallowMount(StatusCell, { propsData: propsDataTestWithoutColor })
    const vm = wrapper.vm
    jest.spyOn(vm.$el.style, 'removeProperty').mockImplementation(() => {
      throw new Error('Error')
    })
    try {
      vm.setColor()
    } catch (e) {
      expect(wrapper.attributes('style')).toBe(undefined)
    }
  })
  test('if component with the ref status-cell is enable and the color is not empty and removeProperty fail', () => {
    const wrapper = shallowMount(StatusCell, { propsData: propsDataTestWithColor })
    const vm = wrapper.vm
    jest.spyOn(vm.$el.style, 'setProperty').mockImplementation(() => {
      throw new Error('Error')
    })
    vm.setColor()
    expect(wrapper.attributes('style')).toBe('color: rgb(255, 255, 255);')
  })
```



### Pisar una funcionalidad de un elemento del DOM

Por ejemplo style.removeProperty

```javascript
test('if component with the ref status-cell is enable and the color is empty', () => {
    const wrapper = shallowMount(StatusCell, { propsData: propsDataTestWithoutColor })
    const vm = wrapper.vm
    const removePropertyStub = jest.fn()
    jest.spyOn(vm.$el.style, 'removeProperty').mockImplementation(removePropertyStub)
    wrapper.vm.setColor()
    expect(removePropertyStub).toBeCalledWith('--color')
  })

```



### Reemplazando respuestas de llamandas a axios

Ejemplo de componente

```html
<template>
    <p v-if="weather">
        La temperatura actual en {{ weather.name }} es de {{ weather.temp | KelvinToCelsius }}
    </p>
    <p v-else>
        Sin datos de temperatura
    </p>

</template>

<script>
    import axios from 'axios'
    export default {
        name: 'weather',
        data() {
            return {
                weather: null
            }
        },
        filters: {
            KelvinToCelsius(kelvin) {
                return `${Math.round(kelvin-273.15)}ºC`;
            }
        },
        created(){
            return axios.get('https://api.openweathermap.org/data/2.5/weather', {
                params: {
                    q: 'Tudela',
                    appid: 'cf36ef5d9429a5452c230f9c97bab06d'
                },
            }).then( data => {
                const {name, main: {temp} } = data.data;
                this.weather = {name, temp};
            }).catch(() => {
                this.weather = null;
            })
        }
    }
</script>
```




Su test probando tanto la llamada correcta como el fallo en la respuesta sería

```javascript
import Weather from '@/components/Weather';
import axios from 'axios'
jest.mock('axios', () => ({
    get: jest.fn()
}));

describe('Weather.vue', () => {
    beforeEach(() => {
        jest.resetAllMocks();
    })
    describe('created', () => {
        test('axios api call ok', async () => {
            const weather = {
                name: 'Tudela',
                temp: 273.15
            }
            axios.get.mockImplementation(() => Promise.resolve({
                data: {
                    name: weather.name,
                    main: {
                        temp: weather.temp
                    }
                }
            }));
            let vmData = Weather.data();
            await Weather.created.call(vmData);
            expect(vmData.weather).toMatchObject(weather);
            expect(axios.get).toHaveBeenCalledWith('https://api.openweathermap.org/data/2.5/weather', {
                params: {
                    q: 'Tudela',
                    appid: 'cf36ef5d9429a5452c230f9c97bab06d'
                }
            });
        })
        test('axios api call ko', async () => {
            axios.get.mockImplementation(() => Promise.reject());
            let vmData = Weather.data();
            await Weather.created.call(vmData);
            expect(vmData.weather).toBe(null);
        })
    })
    describe('filters', () => {
        test('KelvinToCelsius', () => {
            expect(Weather.filters.KelvinToCelsius(273.15)).toBe('0ºC');
        })
    })
})
```



Primero interceptamos todas las llamadas get de axios de forma global (esto se podria sacar a un archivo de utilidades)

```javascript
import axios from 'axios'
jest.mock('axios', () => ({
    get: jest.fn()
}));
```
```javascript
  axios.get.mockImplementation(() => Promise.reject());
```

Es interesante ver que podemos traernos al test el data predefinido ejecutando el nombreComponente.data()

```javascript
  let vmData = Weather.data();
```



Para poder validar que los datos se actuilzan como queremos en el then o el catch de la llamada tenemos que aislar la llamanda en un metodo para que ese metodo lo unico que haga es devolver la promesa de este modo dese jest lo único que deveremos hacer es tener un await al metodo para que nos ejecute el las comprobaciones del test hasta que se halla resuleto la llamada axios

```javascript
  created(){
    return axios.get('https://api.openweathermap.org/data/2.5/weather', {
    params: {
       q: 'Tudela',
       appid: 'cf36ef5d9429a5452c230f9c97bab06d'
      },
    }).then( data => {
      const {name, main: {temp} } = data.data;
      this.weather = {name, temp};
    }).catch(() => {
      this.weather = null;
    })
  }
```
```javascript
await Weather.created.call(vmData);
  expect(vmData.weather).toMatchObject(weather);
```

[jest]: https://jestjs.io/en/
[cli]: https://jestjs.io/docs/en/cli
[@vue/test-utils]: https://github.com/vuejs/vue-test-utils
[vue-jest]: https://github.com/vuejs/vue-jest
[configuración]: https://jestjs.io/docs/en/configuration
[babel]: https://babeljs.io/
[babel-jest]: https://www.npmjs.com/package/babel-jest
[describe]: https://jestjs.io/docs/en/api#describename-fn
[test]: https://jestjs.io/docs/en/api#testname-fn-timeout
[expect]: https://jestjs.io/docs/en/expect
[test-each]: https://jestjs.io/docs/en/api#testeachtablename-fn-timeout
[jest mock functions]: https://jestjs.io/docs/en/mock-function-api
[tohavebeencalled]: https://jestjs.io/docs/en/expect#tohavebeencalled
[tohavebeencalledwith]: https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2
[mockimplementation]: https://jestjs.io/docs/en/mock-function-api#mockfnmockimplementationfn
[jsdom]: https://github.com/jsdom/jsdom
[vue mount]: https://vue-test-utils.vuejs.org/api/mount.html
[vue shallowmount]: https://vue-test-utils.vuejs.org/api/shallowMount.html
[instrucciones]: https://vue-test-utils.vuejs.org/guides/testing-single-file-components-with-jest.html
[createLocalVue]: https://vue-test-utils.vuejs.org/api/createLocalVue.html
[mounting options]: https://vue-test-utils.vuejs.org/api/options.html
[selector]: https://vue-test-utils.vuejs.org/api/selectors.html
[WrapperArray]: https://vue-test-utils.vuejs.org/api/wrapper-array/
[setChecked]: https://vue-test-utils.vuejs.org/api/wrapper/#setchecked
[setSelected]: https://vue-test-utils.vuejs.org/api/wrapper/#setselected