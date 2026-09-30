# 🔤 Lenguajes y Autómatas: Gramáticas Libres de Contexto (GLC)

En este repositorio se presentan la resolución analítica y las derivaciones formales correspondientes a los ejercicios de **Gramáticas Libres de Contexto (GLC)** expuestos en el documento `Lenguajes y Autómatas-Gramáticas-Ejercicios-Filmina 8.pdf`.

## 📌 Gramática $G$ Definida

Sea la gramática libre de contexto $G = (V, \Sigma, R, S)$, definida por las siguientes reglas de producción:

$$
\begin{aligned} R &\to X R X \mid S \\ S &\to a T b \mid b T a \\ T &\to X T X \mid X \mid \epsilon \\ X &\to a \mid b \end{aligned}
$$

Donde:

* **Variables (**$V$**):** $\{R, S, T, X\}$ (Total: 4)

* **Terminales (**$\Sigma$**):** $\{a, b\}$ (Total: 2)

* **Símbolo Inicial:** $R$

## ⚙️ Análisis de la Gramática y Respuestas

### 1. Propiedades Fundamentales

| **Ítem** | **Pregunta / Concepto** | **Respuesta** | 
| **a** | ¿Cuántas variables tiene $G$? | **4** ($R, S, T, X$) | 
| **b** | ¿Cuántos terminales tiene $G$? | **2** ($a, b$) | 
| **c** | Símbolo inicial de $G$ | $R$ | 
| **d** | Cadenas de muestra en $L(G)$ | `ab`, `aabb`, `abb` | 
| **e** | Cadena mínima posible | `ab` (o `ba`) | 

### 2. Evaluaciones de Verdad o Falsedad (V/F)

$\text{T } \Rightarrow^* \text{T}$: **Verdadero** *(Propiedad reflexiva de la relación de derivación en cero o más pasos)*.

$\text{XXX } \Rightarrow^* \text{aba}$: **Verdadero** *(Puesto que cada* $X$ *deriva individualmente en* $a$ *o* $b$*)*.

$\text{X } \Rightarrow^* \text{aba}$: **Falso**.

$\text{T } \Rightarrow^* \text{XX}$: **Verdadero**.

$\text{S } \Rightarrow^* \epsilon$: **Falso** *(El símbolo inicial* $S$ *siempre produce al menos los terminales* $a$ *y* $b$*)*.

## 🌳 Ejemplo de Derivación Formal y Árbol

A continuación se muestra el proceso de derivación de la cadena `aabababa`:

```
          R
       /  |  \
      X   R   X
      |   |   |
      a   S   a
        / | \
       a  T  b
        / | \
       X  T  X
       |  |  |
       b  a  b

```

### Pasos de Derivación:

1. $R \Rightarrow X R X$

2. $a R a \Rightarrow a S a$

3. $a (a T b) a \Rightarrow a a T b a$

4. $a a (X T X) b a \Rightarrow a a b T b a$

5. $a a b a b a$

## 💡 Descripción del Lenguaje $L(G)$

El lenguaje generado por la gramática $G$, denominado $L(G)$, está conformado por cadenas sobre el alfabeto $\Sigma = \{a, b\}$ con estructura simétrica respecto al núcleo generado por $S$, garantizando una combinación equilibrada de prefijos y sufijos terminales a través de la variable auxiliar $X$.
