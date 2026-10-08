# Tema 1 — Fundamentos de almacenamiento y unidades de información

![Infografía resumen del Tema 1](imagenes/tema-01-infografia.png)

## 🎯 Objetivo de aprendizaje

Al terminar este tema deberías poder:

- explicar qué son un **bit** y un **byte**;
- reconocer las unidades **KB, MB, GB y TB**;
- realizar conversiones básicas entre estas unidades;
- entender por qué estas conversiones serán necesarias para estudiar después **sectores, clusters, archivos y volúmenes**;
- interpretar correctamente el ejemplo visto en clase del archivo `beta.txt`.

---

## 🔗 ¿Por qué comenzamos por este tema?

En Sistemas Operativos vamos a estudiar cómo se guarda la información dentro de un dispositivo de almacenamiento.

Pero antes de hablar de sectores o clusters necesitamos responder una pregunta más básica:

**¿Cómo medimos la cantidad de información?**

Por eso nuestra ruta comienza aquí:

**bit → byte → KB → MB → GB → TB**

Y después podremos avanzar hacia:

**bytes → sectores → clusters → archivos → sistema de archivos**

Si no dominamos las unidades de almacenamiento, más adelante será difícil comprender ejercicios como:

- ¿Cuántos sectores hay en 1 MB?
- ¿Cuántos sectores forman un cluster?
- ¿Por qué un archivo de 4 bytes puede ocupar 1 KB en disco?

---

# 1. El bit

Un **bit** es la unidad mínima de información digital.

La palabra viene de:

**Binary Digit = dígito binario**

Un bit solamente puede representar uno de dos valores:

**0** o **1**

Ejemplos:

`0` → 1 bit  
`1` → 1 bit  
`1010` → 4 bits  
`01001000` → 8 bits

La computadora utiliza combinaciones de bits para representar información.

## 💡 Analogía

Imagina un interruptor:

- **apagado = 0**
- **encendido = 1**

Un bit funciona de forma parecida: posee dos posibles estados.

---

# 2. El byte

Un **byte** es un grupo formado por:

**8 bits**

Por lo tanto:

**1 byte = 8 bits**

Ejemplo:

`01001000`

Tiene 8 bits, por lo tanto representa **1 byte**.

## 📊 Esquema visual

```text
1 BYTE

┌───┬───┬───┬───┬───┬───┬───┬───┐
│ 0 │ 1 │ 0 │ 0 │ 1 │ 0 │ 0 │ 0 │
└───┴───┴───┴───┴───┴───┴───┴───┘

        8 bits = 1 byte
```

---

# 3. El ejemplo visto en clase: `beta.txt`

En clase se creó un archivo llamado:

`beta.txt`

Dentro se escribió:

`hola`

La palabra tiene cuatro caracteres:

`h` `o` `l` `a`

En el ejemplo observado, las propiedades mostraban:

**Tamaño: 4 bytes**

Usando una codificación como UTF-8, cada una de esas letras simples ocupa un byte.

```text
h = 1 byte
o = 1 byte
l = 1 byte
a = 1 byte
────────────
Total = 4 bytes
```

Por ahora quédate con esta idea:

**el archivo contiene 4 bytes de información.**

Más adelante veremos por qué el sistema podía mostrar:

**Tamaño en disco: 1 KB**

aunque el contenido real fuera solamente de 4 bytes.

---

# 4. ¿Por qué necesitamos unidades mayores?

Un byte es una unidad muy pequeña.

Si tuviéramos que expresar el tamaño de un archivo grande solamente en bytes, obtendríamos números enormes.

Por eso utilizamos unidades mayores:

**byte → KB → MB → GB → TB**

---

# 5. Tabla fundamental de unidades

| Unidad | Equivalencia usada en clase |
|---|---:|
| 1 byte | 8 bits |
| 1 KB | 1024 bytes |
| 1 MB | 1024 KB |
| 1 GB | 1024 MB |
| 1 TB | 1024 GB |

La idea principal es:

**cada nivel es 1024 veces mayor que el anterior.**

---

# 6. La escalera de unidades

```text
                     MÁS GRANDE
                         ↑
                        TB
                         ↑
                     × 1024
                        GB
                         ↑
                     × 1024
                        MB
                         ↑
                     × 1024
                        KB
                         ↑
                     × 1024
                       Byte
                         ↑
                       8 bits
                         ↑
                        Bit
```

Otra forma de verlo:

```text
Byte → KB → MB → GB → TB
       ÷1024 ÷1024 ÷1024 ÷1024
```

Cuando avanzamos hacia una unidad más grande:

**dividimos entre 1024**

Cuando vamos hacia una unidad más pequeña:

**multiplicamos por 1024**

---

# 7. ¿Por qué aparece el número 1024?

Las computadoras trabajan internamente utilizando el sistema binario.

El número 1024 es importante porque:

**1024 = 2¹⁰**

Por eso, tradicionalmente, muchas cantidades de memoria y almacenamiento informático se explican utilizando potencias de 2.

Para los ejercicios de esta materia seguiremos la convención utilizada en clase:

**1 KB = 1024 bytes**

## ⚠️ Una precisión importante

En informática moderna existe una distinción técnica:

- **1 kB = 1000 bytes**
- **1 KiB = 1024 bytes**
- **1 MiB = 1024 KiB**
- **1 GiB = 1024 MiB**

Sin embargo, muchos sistemas, libros y clases siguen utilizando informalmente las siglas **KB, MB y GB** cuando realizan cálculos con 1024.

Para mantenernos alineados con lo explicado por el docente, en nuestros ejercicios utilizaremos:

**1 KB = 1024 bytes**

---

# 8. Regla para convertir unidades

## De una unidad grande a una pequeña

**Multiplicamos por 1024.**

Ejemplo:

```text
2 KB × 1024 = 2048 bytes
```

## De una unidad pequeña a una grande

**Dividimos entre 1024.**

Ejemplo:

```text
2048 bytes ÷ 1024 = 2 KB
```

---

# 9. Ejemplo resuelto 1 — Convertir 5 KB a bytes

Sabemos que:

**1 KB = 1024 bytes**

Entonces:

**5 KB = 5 × 1024**

Resultado:

**5 KB = 5120 bytes**

---

# 10. Ejemplo resuelto 2 — Convertir 1 MB a bytes

```text
1 MB = 1024 KB
1 KB = 1024 bytes

1 MB = 1024 × 1024 bytes
1 MB = 1 048 576 bytes
```

---

# 11. Ejemplo resuelto 3 — Convertir 1 GB a bytes

```text
1 GB = 1024 MB
1 MB = 1024 KB
1 KB = 1024 bytes

1 GB = 1024 × 1024 × 1024 bytes
1 GB = 1 073 741 824 bytes
```

---

# 12. Una forma rápida de pensar las conversiones

```text
Byte ↔ KB ↔ MB ↔ GB ↔ TB
```

Cada salto equivale a **1024**.

Por ejemplo:

```text
1 GB
= 1024 MB
= 1024 × 1024 KB
= 1 048 576 KB
```

---

# 13. Conexión con sectores

En clase apareció una pregunta importante:

**¿Cuántos sectores hay en 1 MB o en 1 GB?**

Todavía no estudiaremos sectores en profundidad, pero podemos preparar la idea.

Supongamos que:

**1 sector = 512 bytes**

Entonces:

```text
1 KB = 1024 bytes

1024 ÷ 512 = 2
```

Por lo tanto:

**1 KB contiene 2 sectores de 512 bytes.**

---

# 14. Conexión con clusters

En el ejemplo visto en clase se tenía:

**1 cluster = 2 sectores**

y cada sector tenía:

**512 bytes**

```text
Sector 1 = 512 bytes
Sector 2 = 512 bytes
──────────────────────
Cluster   = 1024 bytes
```

Como:

**1024 bytes = 1 KB**

entonces:

**1 cluster = 1 KB**

en ese ejemplo concreto.

---

# 15. Volvemos a `beta.txt`

El archivo contenía:

`hola`

Su tamaño real era:

**4 bytes**

Pero el tamaño ocupado en disco era:

**1 KB**

En el ejemplo:

**1 cluster = 1024 bytes**

Por lo tanto, el archivo estaba utilizando:

**1 cluster completo**

aunque su contenido solamente necesitara 4 bytes.

```text
Archivo beta.txt
Contenido: "hola"

Información real:
┌────┬────┬────┬────┐
│ h  │ o  │ l  │ a  │
└────┴────┴────┴────┘
   4 bytes utilizados


Espacio reservado:
┌───────────────────────────────────────┐
│              1 CLUSTER                │
│              1024 bytes               │
│                                       │
│ 4 bytes usados + espacio restante     │
└───────────────────────────────────────┘
```

Por eso:

**Tamaño del archivo = 4 bytes**

pero:

**Tamaño en disco = 1 KB**

---

# 16. Diferencia entre información y espacio reservado

```text
Contenido real
      ↓
    4 bytes

Espacio asignado
      ↓
  1 cluster
      ↓
   1024 bytes
```

No significa que el archivo mágicamente contenga 1024 bytes de texto.

Significa que el sistema ha reservado una unidad completa de almacenamiento para guardarlo.

---

# 17. Tabla de conceptos principales

| Concepto | Significado |
|---|---|
| Bit | Unidad mínima de información |
| Byte | Grupo de 8 bits |
| KB | 1024 bytes en nuestros ejercicios |
| MB | 1024 KB |
| GB | 1024 MB |
| TB | 1024 GB |
| Sector | Unidad que estudiaremos después; en el ejemplo tiene 512 bytes |
| Cluster | Grupo de sectores utilizado para asignar espacio a archivos |

---

# 18. Analogía general

Imagina que almacenamos información utilizando cajas.

Un **bit** sería una pieza muy pequeña.

Varios bits forman una pequeña caja:

**byte**

Muchas de esas cajas forman una caja mayor:

**KB → MB → GB → TB**

La idea es que utilizamos unidades cada vez mayores para evitar trabajar con números demasiado grandes.

---

# 19. Errores y confusiones frecuentes

## Error 1
Pensar que **1 byte = 1 bit**.

Correcto:

**1 byte = 8 bits**

## Error 2
Confundir cuándo multiplicar y cuándo dividir.

**Grande → pequeño = multiplicar**

**Pequeño → grande = dividir**

## Error 3
Pensar que tamaño del archivo y tamaño en disco siempre son iguales.

El ejemplo `beta.txt` demuestra que un archivo de **4 bytes** puede ocupar **1 KB en disco**.

## Error 4
Pensar que un cluster siempre mide 1 KB.

Incorrecto. En nuestro ejemplo de clase mide 1 KB porque contiene:

**2 sectores × 512 bytes**

El tamaño de cluster puede variar según el sistema de archivos y su configuración.

---

# ⭐ Lo que debes recordar sí o sí

```text
1 byte = 8 bits

1 KB = 1024 bytes
1 MB = 1024 KB
1 GB = 1024 MB
1 TB = 1024 GB
```

Regla:

```text
Unidad grande → unidad pequeña
MULTIPLICAR × 1024

Unidad pequeña → unidad grande
DIVIDIR ÷ 1024
```

---

# 20. Preguntas de comprensión

1. ¿Qué es un bit?
2. ¿Cuántos bits forman un byte?
3. ¿Cuántos bytes hay en 1 KB según la convención utilizada en clase?
4. ¿Cuántos KB forman 1 MB?
5. Si pasamos de MB a bytes, ¿multiplicamos o dividimos?
6. ¿Por qué utilizamos unidades como MB y GB en lugar de expresar todo en bytes?
7. ¿Por qué `beta.txt`, con solamente 4 bytes de información, podía ocupar 1 KB en disco?
8. Si un sector mide 512 bytes, ¿cuántos sectores caben en 1 KB?

---

# 21. Ejercicios

## Nivel 1 — Conversión directa

- **A.** 3 KB a bytes.
- **B.** 8 KB a bytes.
- **C.** 2048 bytes a KB.
- **D.** 2 MB a KB.
- **E.** 4 GB a MB.

## Nivel 2 — Conversión de varios pasos

- **A.** 2 MB a bytes.
- **B.** 3 GB a KB.
- **C.** 1 GB a bytes.

## Nivel 3 — Preparación para sectores

Supongamos que:

**1 sector = 512 bytes**

Calcula:

- **A.** ¿Cuántos sectores caben en 1 KB?
- **B.** ¿Cuántos sectores caben en 2 KB?
- **C.** ¿Cuántos sectores caben en 4 KB?

---

# 22. Mini evaluación

### Pregunta 1
¿Cuántos bits forman un byte?

A) 2  
B) 4  
C) 8  
D) 1024

### Pregunta 2
¿Cuántos bytes utilizaremos para representar 1 KB en los ejercicios?

A) 100  
B) 512  
C) 1000  
D) 1024

### Pregunta 3
¿Cuál operación realizamos para convertir 4 MB a KB?

A) 4 + 1024  
B) 4 × 1024  
C) 4 ÷ 1024  
D) 1024 ÷ 4

### Pregunta 4
En el ejemplo visto en clase, `beta.txt` contenía:

A) 1 byte  
B) 2 bytes  
C) 4 bytes  
D) 1024 bytes

### Pregunta 5
Si un sector mide 512 bytes, ¿cuántos sectores forman 1024 bytes?

A) 1  
B) 2  
C) 4  
D) 8

---

# 23. Respuestas de la mini evaluación

**1 → C**  
**2 → D**  
**3 → B**  
**4 → C**  
**5 → B**

---

# 24. Mapa mental del tema

```text
                 INFORMACIÓN DIGITAL
                        │
                        ▼
                       BIT
                        │
                   8 bits
                        ▼
                      BYTE
                        │
                    × 1024
                        ▼
                       KB
                        │
                    × 1024
                        ▼
                       MB
                        │
                    × 1024
                        ▼
                       GB
                        │
                    × 1024
                        ▼
                       TB


Luego utilizaremos estas unidades para entender:

BYTE
  ↓
SECTOR
  ↓
CLUSTER
  ↓
ARCHIVO
  ↓
VOLUMEN
```

---

# 25. Conexión con el siguiente tema

Ahora ya sabemos medir la información utilizando:

**bytes, KB, MB y GB.**

El siguiente paso es comprender **dónde se almacena físicamente o lógicamente esa información**.

Para eso comenzaremos a estudiar:

**dispositivos de almacenamiento y estructura básica del disco**

y después entraremos de lleno en:

**sectores**

La idea será responder preguntas como:

- ¿Cómo se divide un disco?
- ¿Qué es exactamente un sector?
- ¿Por qué aparece el valor 512 bytes?
- ¿Cómo calculamos cuántos sectores existen en 1 MB o 1 GB?

Con esto quedará preparada la base necesaria para llegar correctamente al tema de **clusters**.
