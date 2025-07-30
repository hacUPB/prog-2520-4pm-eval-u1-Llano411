# Ejercicios de Representación de Datos

-----

## Ejercicio 1: ¿Cuántos estados diferentes se pueden representar usando N bits?

Para determinar cuántos estados diferentes se pueden representar usando **N bits**, aplicamos la fórmula de potencias de 2. Cada bit puede estar en uno de dos estados (0 o 1). Si tenemos N bits, cada bit actúa de forma independiente, duplicando el número de estados posibles con cada bit adicional.

Por lo tanto, el número de estados diferentes es $2$ elevado a la potencia de $N$

Número de estados diferentes = $2^N$.

-----

## Ejercicio 2: Convierte el número decimal 22 a binario.

Para convertir el número decimal **22** a binario, utilizamos el método de divisiones sucesivas por 2, anotando el residuo de cada división y luego leyendo los residuos en orden inverso (de abajo hacia arriba).

1.  Dividimos **22** entre 2:
    $22 \\div 2 = 11$
    Residuo: **0**

2.  Dividimos **11** entre 2:
    $11 \\div 2 = 5$
    Residuo: **1**

3.  Dividimos **5** entre 2:
    $5 \\div 2 = 2$
    Residuo: **1**

4.  Dividimos **2** entre 2:
    $2 \\div 2 = 1$
    Residuo: **0**

5.  Dividimos **1** entre 2:
    $1 \\div 2 = 0$
    Residuo: **1**

Ahora, leemos los residuos desde el último hasta el primero: **10110**.

Por lo tanto, el número decimal **22** es igual a **10110** en binario.

-----

## Ejercicio 3: ¿Cuál es el resultado en decimal del número binario 10110?

Para convertir el número binario **10110** a decimal, multiplicamos cada bit por la potencia de 2 correspondiente a su posición (empezando desde 0 para el bit más a la derecha) y sumamos los resultados:

  * **0** (último bit a la derecha) está en la posición $2^0$:
    $0 \\times 2^0 = 0 \\times 1 = 0$
  * **1** está en la posición $2^1$:
    $1 \\times 2^1 = 1 \\times 2 = 2$
  * **1** está en la posición $2^2$:
    $1 \\times 2^2 = 1 \\times 4 = 4$
  * **0** está en la posición $2^3$:
    $0 \\times 2^3 = 0 \\times 8 = 0$
  * **1** (primer bit a la izquierda) está en la posición $2^4$:
    $1 \\times 2^4 = 1 \\times 16 = 16$

Ahora, sumamos todos estos resultados:

$0 + 2 + 4 + 0 + 16 = \\textbf{22}$

Por lo tanto, el número binario **10110** es igual a **22** en decimal.

-----

## Ejercicio 4: Escribe un programa en Python que convierta un número decimal introducido por el usuario a binario.

Este programa en Python solicita al usuario un número decimal entero no negativo y luego lo convierte a su representación binaria utilizando divisiones sucesivas.

```python
def decimal_a_binario(decimal):
    # Caso especial para el número 0
    if decimal == 0:
        return "0"

    binario = ""
    # Realizamos divisiones sucesivas por 2
    while decimal > 0:
        # Obtenemos el residuo (será 0 o 1) y lo añadimos al inicio de la cadena binaria
        binario = str(decimal % 2) + binario
        # Actualizamos el número decimal para la siguiente iteración
        decimal = decimal // 2 # División entera

    return binario

# Solicitar al usuario que introduzca un número
try:
    numero_decimal = int(input("Introduce un número decimal entero no negativo: "))

    if numero_decimal < 0:
        print("Error: Por favor, introduce un número decimal que no sea negativo.")
    else:
        # Llamar a la función para realizar la conversión
        resultado_binario = decimal_a_binario(numero_decimal)
        print(f"El número decimal {numero_decimal} en binario es: {resultado_binario}")

except ValueError:
    # Manejar el error si el usuario no introduce un número entero
    print("Error: Entrada inválida. Por favor, introduce un número entero válido.")

```

-----

## Ejercicio 5: ¿Qué número binario representa el carácter 'C' en ASCII?

Para encontrar el número binario que representa el carácter **'C'** en ASCII, primero necesitamos conocer su valor decimal en la tabla ASCII y luego convertir ese valor a binario.

1.  **Valor decimal de 'C' en ASCII:**
    Consultando la tabla ASCII, el carácter 'C' (mayúscula) tiene un valor decimal de **67**.

2.  **Convertir 67 a binario:**
    Utilizamos el método de divisiones sucesivas por 2:

      * Dividimos **67** entre 2:
        $67 \\div 2 = 33$
        Residuo: **1**
      * Dividimos **33** entre 2:
        $33 \\div 2 = 16$
        Residuo: **1**
      * Dividimos **16** entre 2:
        $16 \\div 2 = 8$
        Residuo: **0**
      * Dividimos **8** entre 2:
        $8 \\div 2 = 4$
        Residuo: **0**
      * Dividimos **4** entre 2:
        $4 \\div 2 = 2$
        Residuo: **0**
      * Dividimos **2** entre 2:
        $2 \\div 2 = 1$
        Residuo: **0**
      * Dividimos **1** entre 2:
        $1 \\div 2 = 0$
        Residuo: **1**

    Leemos los residuos de abajo hacia arriba: **1000011**.
    Dado que los caracteres ASCII se suelen representar en 8 bits (un byte), podemos añadir un cero a la izquierda para completar los 8 bits.

Por lo tanto, el carácter 'C' en ASCII se representa con el número binario **01000011**.

-----

## Ejercicio 6: Convierte el número flotante 5.75 a binario (explica los pasos)

Para convertir un número flotante como **5.75** a su representación binaria, lo dividimos en dos partes: la parte entera y la parte fraccionaria, y convertimos cada una por separado.

### Paso 1: Convertir la Parte Entera (5) a Binario

Utilizamos el método de divisiones sucesivas por 2 para la parte entera:

1.  Dividimos **5** entre 2:
    $5 \\div 2 = 2$
    Residuo: **1**
2.  Dividimos **2** entre 2:
    $2 \\div 2 = 1$
    Residuo: **0**
3.  Dividimos **1** entre 2:
    $1 \\div 2 = 0$
    Residuo: **1**

Leyendo los residuos de abajo hacia arriba, la parte entera **5** en binario es **101**.

### Paso 2: Convertir la Parte Fraccionaria (0.75) a Binario

Utilizamos el método de multiplicaciones sucesivas por 2 para la parte fraccionaria, tomando la parte entera del resultado en cada paso.

1.  Multiplicamos **0.75** por 2:
    $0.75 \\times 2 = 1.50$
    Tomamos la parte entera: **1** (este es el primer bit después del punto binario).
    La nueva parte fraccionaria es 0.50.

2.  Multiplicamos **0.50** por 2:
    $0.50 \\times 2 = 1.00$
    Tomamos la parte entera: **1** (este es el segundo bit después del punto binario).
    La nueva parte fraccionaria es 0.00.

Cuando la parte fraccionaria se vuelve 0, detenemos el proceso.
Leyendo las partes enteras obtenidas de arriba hacia abajo, la parte fraccionaria **0.75** en binario es **.11**.

### Paso 3: Combinar Ambas Partes

Unimos la parte entera binaria y la parte fraccionaria binaria con un punto decimal binario.

Parte entera binaria: **101**
Parte fraccionaria binaria: **.11**

Combinado, el número flotante **5.75** en binario es **101.11**.

-----

## Ejercicio 7: ¿Cuántos bytes se necesitan para almacenar la palabra “Hola” en ASCII?

En el estándar **ASCII (American Standard Code for Information Interchange)**, cada carácter (letra, número, símbolo) se representa utilizando un único **byte**. Un byte consiste en 8 bits.

La palabra "Hola" está compuesta por los siguientes cuatro caracteres:

  * 'H'
  * 'o'
  * 'l'
  * 'a'

Dado que cada uno de estos caracteres requiere 1 byte de almacenamiento:

  * 'H' = 1 byte
  * 'o' = 1 byte
  * 'l' = 1 byte
  * 'a' = 1 byte

Sumando el almacenamiento para cada carácter: $1 + 1 + 1 + 1 = 4$ bytes.

Por lo tanto, se necesitan **4 bytes** para almacenar la palabra “Hola” en ASCII.

-----

## Ejercicio 8: ¿Cuántos bits hay en 5 KB?

Para calcular cuántos bits hay en 5 KB (kilobytes), necesitamos recordar las siguientes equivalencias:

1.  **1 Kilobyte (KB)** es igual a **1024 bytes**. (En contextos de almacenamiento digital, KB se refiere a 2^10 bytes, no a 1000 bytes).
2.  **1 Byte** es igual a **8 bits**.

Ahora, realizamos el cálculo paso a paso:

### Paso 1: Convertir Kilobytes a Bytes

Multiplicamos el número de Kilobytes por la cantidad de bytes en un Kilobyte:

$5 \\text{ KB} \\times 1024 \\text{ bytes/KB} = 5120 \\text{ bytes}$

### Paso 2: Convertir Bytes a Bits

Multiplicamos el número de bytes obtenido por la cantidad de bits en un byte:

$5120 \\text{ bytes} \\times 8 \\text{ bits/byte} = \\textbf{40960 bits}$

Por lo tanto, hay **40960 bits** en 5 KB.

-----

## Ejercicio 9: Convierte el número decimal 255 a hexadecimal.

Para convertir el número decimal **255** a hexadecimal, utilizamos el método de divisiones sucesivas por 16, anotando el residuo de cada división y luego leyendo los residuos en orden inverso (de abajo hacia arriba). Recordemos que en hexadecimal, los valores del 10 al 15 se representan con las letras A a F.

1.  Dividimos **255** entre 16:
    $255 \\div 16 = 15$
    Residuo: **15**

2.  Dividimos **15** entre 16:
    $15 \\div 16 = 0$
    Residuo: **15**

Ahora, convertimos los residuos a sus equivalentes hexadecimales:

  * El residuo **15** en hexadecimal se representa como **F**.
  * El residuo **15** en hexadecimal se representa como **F**.

Leemos los residuos de abajo hacia arriba: **FF**.

Por lo tanto, el número decimal **255** es igual a **FF** en hexadecimal.

-----

## Ejercicio 10: ¿Cuál es el valor hexadecimal de la secuencia binaria 11010110?

Para convertir una secuencia binaria a hexadecimal, la forma más sencilla es agrupar los bits de 4 en 4, comenzando desde la derecha. Luego, convertimos cada grupo de 4 bits (conocido como *nibble*) a su dígito hexadecimal equivalente.

La secuencia binaria es **11010110**.

### Paso 1: Agrupar los bits en grupos de cuatro

Dividimos la secuencia binaria en dos grupos de 4 bits:

**1101** | **0110**

### Paso 2: Convertir cada grupo de 4 bits a decimal

  * **Primer grupo (izquierda): 1101**
    Convertimos `1101` a decimal:
    $1 \\times 2^3 + 1 \\times 2^2 + 0 \\times 2^1 + 1 \\times 2^0$
    $= 1 \\times 8 + 1 \\times 4 + 0 \\times 2 + 1 \\times 1$
    $= 8 + 4 + 0 + 1 = 13$

  * **Segundo grupo (derecha): 0110**
    Convertimos `0110` a decimal:
    $0 \\times 2^3 + 1 \\times 2^2 + 1 \\times 2^1 + 0 \\times 2^0$
    $= 0 \\times 8 + 1 \\times 4 + 1 \\times 2 + 0 \\times 1$
    $= 0 + 4 + 2 + 0 = 6$

### Paso 3: Convertir los valores decimales a hexadecimal

  * El valor decimal **13** en hexadecimal se representa como **D**.
  * El valor decimal **6** en hexadecimal se representa como **6**.

Uniendo los resultados de ambos grupos: **D6**.

Por lo tanto, el valor hexadecimal de la secuencia binaria **11010110** es **D6**.

-----

## Ejercicio 11: Explica, en tus propias palabras, por qué es necesario que las computadoras representen los datos en binario.

Las computadoras representan todos los datos en **binario** (es decir, usando solo ceros y unos) porque su hardware fundamental, los circuitos electrónicos, funciona de una manera muy simple: tienen dos estados eléctricos básicos. Piensa en ellos como **interruptores**:

  * **Encendido (presencia de voltaje, paso de corriente):** Esto se representa con un **1**.
  * **Apagado (ausencia de voltaje, no paso de corriente):** Esto se representa con un **0**.

Es increíblemente difícil y propenso a errores para un circuito electrónico distinguir entre muchos niveles diferentes de voltaje para representar, por ejemplo, los diez dígitos del sistema decimal (0-9). Imagina un interruptor que tuviera que apagarse un poco, un poco más, a la mitad, casi todo, etc. Sería muy inestable.

En cambio, con solo dos estados, las computadoras pueden procesar, almacenar y transmitir información de manera **extremadamente confiable, rápida y eficiente**. Toda la información que una computadora maneja (ya sean números, texto, imágenes, música o videos) se descompone y se codifica en estas secuencias de ceros y unos para que el hardware pueda "entenderla" y manipularla sin ambigüedades. Esta simplicidad a nivel físico es la base de la complejidad y la potencia de la computación moderna.

-----

## Ejercicio 12: Convierte el número binario 10011011 a decimal y a hexadecimal.

Vamos a convertir el número binario **10011011** a sus equivalentes decimal y hexadecimal.

### Parte 1: Convertir a Decimal

Para convertir el número binario **10011011** a decimal, multiplicamos cada bit por la potencia de 2 correspondiente a su posición (empezando desde $2^0$ para el bit más a la derecha) y sumamos los resultados:

  * **1** (último bit a la derecha) está en la posición $2^0$: $1 \\times 2^0 = 1 \\times 1 = 1$
  * **1** está en la posición $2^1$: $1 \\times 2^1 = 1 \\times 2 = 2$
  * **0** está en la posición $2^2$: $0 \\times 2^2 = 0 \\times 4 = 0$
  * **1** está en la posición $2^3$: $1 \\times 2^3 = 1 \\times 8 = 8$
  * **1** está en la posición $2^4$: $1 \\times 2^4 = 1 \\times 16 = 16$
  * **0** está en la posición $2^5$: $0 \\times 2^5 = 0 \\times 32 = 0$
  * **0** está en la posición $2^6$: $0 \\times 2^6 = 0 \\times 64 = 0$
  * **1** (primer bit a la izquierda) está en la posición $2^7$: $1 \\times 2^7 = 1 \\times 128 = 128$

Ahora, sumamos todos estos resultados:

$1 + 2 + 0 + 8 + 16 + 0 + 0 + 128 = \\textbf{155}$

Por lo tanto, el número binario **10011011** es igual a **155** en decimal.

### Parte 2: Convertir a Hexadecimal

Para convertir el número binario **10011011** a hexadecimal, agrupamos los bits de 4 en 4, comenzando desde la derecha. Luego, convertimos cada grupo de 4 bits (un *nibble*) a su dígito hexadecimal equivalente.

La secuencia binaria es **10011011**.

1.  **Agrupar los bits:**
    **1001** | **1011**

2.  **Convertir cada grupo a decimal y luego a hexadecimal:**

      * **Primer grupo (izquierda): 1001**
        $1 \\times 2^3 + 0 \\times 2^2 + 0 \\times 2^1 + 1 \\times 2^0 = 8 + 0 + 0 + 1 = 9$.
        En hexadecimal, **9** es simplemente **9**.

      * **Segundo grupo (derecha): 1011**
        $1 \\times 2^3 + 0 \\times 2^2 + 1 \\times 2^1 + 1 \\times 2^0 = 8 + 0 + 2 + 1 = 11$.
        En hexadecimal, **11** se representa como **B**.

Uniendo los resultados de ambos grupos: **9B**.

Por lo tanto, el número binario **10011011** es igual a **9B** en hexadecimal.

-----

## Ejercicio 13: Investiga y describe cómo se representa una imagen en formato PNG en el disco.

Una imagen en formato **PNG (Portable Network Graphics)** no se guarda como una simple matriz de píxeles sin más. En el disco, un archivo PNG es un **flujo de bytes estructurado** que contiene la información de la imagen y metadatos adicionales, organizado en bloques específicos llamados "**chunks**" (trozos o fragmentos). PNG es conocido por usar **compresión sin pérdidas**, lo que significa que la calidad de la imagen no se degrada al guardarla y abrirla repetidamente.

Aquí te explico los componentes principales de cómo se representa:

1.  **Firma PNG (Signature):**
    Al inicio de cada archivo PNG, hay una secuencia fija de 8 bytes (como `89 50 4E 47 0D 0A 1A 0A` en hexadecimal). Esta "firma" actúa como un identificador mágico que permite a los programas reconocer rápidamente que el archivo es un PNG y si está corrupto al inicio.

2.  **Chunks (Bloques de datos):**
    Después de la firma, el resto del archivo PNG se organiza como una secuencia de "chunks". Cada chunk tiene una estructura definida:

      * **Longitud (Length):** Un valor de 4 bytes que indica cuántos bytes de datos contiene el chunk (sin incluir el tipo de chunk ni el CRC).
      * **Tipo de Chunk (Chunk Type):** Un código de 4 bytes (compuesto por letras ASCII) que identifica el propósito de ese bloque de datos. Por ejemplo, `IHDR` para la cabecera, `IDAT` para los datos de píxeles, `IEND` para el final del archivo.
      * **Datos del Chunk (Chunk Data):** La información real que el chunk almacena. El contenido varía según el tipo de chunk.
      * **CRC (Cyclic Redundancy Check):** Un valor de 4 bytes utilizado para verificar la integridad de los datos de ese chunk. Permite detectar si el chunk se ha corrompido durante la transferencia o el almacenamiento.

3.  **Chunks Críticos Fundamentales:**
    Existen varios tipos de chunks, pero algunos son esenciales para que la imagen pueda ser visualizada:

      * **IHDR (Image Header - Cabecera de Imagen):** Es siempre el primer chunk de datos. Contiene información vital sobre la imagen, como su **ancho** y **alto** en píxeles, la **profundidad de bits** (cuántos bits se usan para cada componente de color de un píxel, ej., 8 o 16 bits por canal), el **tipo de color** (si es escala de grises, RGB, con o sin canal alfa para transparencia, si usa paleta de colores), y los métodos de compresión, filtrado y entrelazado.
      * **PLTE (Palette - Paleta):** Si la imagen utiliza un tipo de color indexado (como las imágenes GIF), este chunk contiene la paleta de colores RGB utilizados. Cada entrada de la paleta es un color específico.
      * **IDAT (Image Data - Datos de Imagen):** Este es el chunk más importante ya que contiene los datos de **píxeles reales de la imagen**. Los datos de píxeles se comprimen utilizando el algoritmo **DEFLATE** (que combina LZ77 y codificación de Huffman), un método de compresión sin pérdidas. Antes de la compresión, los datos de los píxeles suelen ser "filtrados" para mejorar aún más la eficacia de la compresión, buscando patrones en las filas de píxeles. Una imagen puede tener uno o múltiples chunks `IDAT` concatenados.
      * **IEND (Image End - Fin de Imagen):** Este es siempre el último chunk del archivo PNG y simplemente marca el final del flujo de datos de la imagen.

4.  **Chunks Auxiliares (Metadata):**
    Además de los críticos, existen chunks auxiliares que contienen metadatos adicionales y no son estrictamente necesarios para renderizar la imagen, pero proporcionan información extra:

      * `tEXt`, `zTXt`, `iTXt`: Para almacenar texto legible por humanos (títulos, descripciones, autor, software).
      * `gAMA`: Para especificar la corrección gamma de la imagen.
      * `cHRM`: Para definir las cromaticidades primarias y el punto blanco.
      * `tRNS`: Para información de transparencia de píxeles o paleta.

En resumen, cuando guardas una imagen como PNG, el software toma los datos de los píxeles, los filtra y comprime de manera inteligente y sin pérdidas. Luego, encapsula estos datos comprimidos, junto con toda la información necesaria para reconstruir la imagen (dimensiones, tipo de color, etc.) y cualquier metadato adicional, en una serie de bloques bien definidos (chunks) dentro de un único archivo binario en el disco. Esto permite que el archivo sea eficiente en espacio y que la imagen se vea exactamente igual cada vez que se abre.

-----

## Ejercicio 14: Analiza la siguiente situación: ¿Qué sucede si intentas almacenar un número mayor al que puede representar un byte (por ejemplo, 300)? ¿Cómo lo maneja Python?

-----

### ¿Qué sucede si intentas almacenar un número mayor al que puede representar un byte (por ejemplo, 300)?

Un solo **byte** está compuesto por 8 bits. Con 8 bits, se pueden representar $2^8$ (dos elevado a la octava potencia) estados diferentes, lo que equivale a **256** valores únicos. Si consideramos números enteros **sin signo**, un byte puede representar valores desde **0 hasta 255**, ambos inclusive.

Si intentas almacenar un número como **300** en un contenedor que solo puede guardar hasta 255 (es decir, un solo byte), se produce una situación conocida como **desbordamiento** (o *overflow*). El número 300 simplemente "no cabe" dentro del espacio asignado.

En lenguajes de programación de bajo nivel o con tipos de datos de tamaño fijo (como `byte` o `unsigned char` en C/C++ o Java), un desbordamiento puede tener consecuencias específicas:

  * **Truncamiento:** Los bits más significativos del número que exceden la capacidad del byte son simplemente descartados. Por ejemplo, 300 en binario es `100101100` (9 bits). Si solo se tomaran los últimos 8 bits (lo que cabe en un byte), el resultado sería `00101100`, que en decimal es 44.
  * **Comportamiento de envoltorio (Wrap-around):** El valor "se envuelve" de nuevo al inicio del rango permitido. Imagina un contador que va de 0 a 255. Si sumas 1 a 255, el contador vuelve a 0. Para el 300, sería como exceder el límite y volver a contar desde el principio: $300 - 256 = 44$.

Este tipo de comportamiento puede llevar a resultados inesperados y errores lógicos difíciles de depurar en programas que no manejan explícitamente estas situaciones.

-----

### ¿Cómo lo maneja Python?

La forma en que Python maneja esta situación es una de sus características más convenientes y robustas. A diferencia de lenguajes con tipos de datos de tamaño fijo, los números enteros (integers) en Python son de **precisión arbitraria**.

Esto significa que los enteros de Python **no tienen un tamaño máximo predefinido** que esté limitado por un número fijo de bytes (como 8, 16, 32 o 64 bits). Python asigna automáticamente la cantidad de memoria necesaria para almacenar cualquier número entero, por grande que sea, hasta el límite de la memoria disponible en tu sistema.

**Por lo tanto, si intentas almacenar el número 300 en Python, no hay ningún desbordamiento.** Python simplemente almacena el valor 300 sin problemas.

Veamos un ejemplo práctico en Python:

```python
# Asignamos el número 300 a una variable
numero_grande = 300
print(f"El número es: {numero_grande}")
print(f"El tipo de dato es: {type(numero_grande)}")

# Asignamos un número mucho, mucho más grande
numero_muy_grande = 1234567890123456789012345678901234567890
print(f"El número muy grande es: {numero_muy_grande}")
print(f"El tipo de dato es: {type(numero_muy_grande)}")
```

La salida de este código sería:

```
El número es: 300
El tipo de dato es: <class 'int'>
El número muy grande es: 1234567890123456789012345678901234567890
El tipo de dato es: <class 'int'>
```

Como puedes ver, Python maneja sin problemas tanto el 300 como un número mucho más grande. Internamente, Python gestiona la representación de estos números utilizando múltiples "palabras" de la máquina según sea necesario, de forma transparente para el programador. Esto elimina la necesidad de preocuparse por los desbordamientos de enteros en la mayoría de los casos, a diferencia de otros lenguajes.

-----
