# Espacio de Estados en Sistemas Dinámicos
## Introducción
El espacio de estados es una representación matemática que describe el comportamiento de sistemas dinámicos al considerar no solo las entradas y salidas, sino también las variables internas del sistema. Esto permite una descripción completa de la dinámica y difiere de la función de transferencia, que se centra en entradas y salidas únicamente.

## Componentes del Espacio de Estados
- **Estado**: Conjunto de variables que permiten entender el comportamiento completo del sistema en un instante.
- **Variables de Estado**: Definen la dinámica del sistema. No siempre son medibles, pero su conocimiento es crucial para ciertos métodos de control.
- **Ecuaciones de Estado**: Combinan variables de estado mediante operadores matemáticos, formando un espacio geométrico llamado espacio de estados.

## Representación Matemática
Las ecuaciones de estado se representan usando las variables de entrada $u(k)$, salida $y(k)$ y variables de estado $x(k)$:

$X(k+1) = f(x(k), u(k), k)$

$y(k) = g(x(k), u(k), k)$

Las funciones $f$ y $g$ pueden ser no lineales y depender del tiempo, adaptándose a una gran variedad de sistemas.

## Representación Matricial
Para simplificar, se utiliza una representación matricial en modelos lineales:

$X(k+1) = A(k)X(k) + B(k)u(k)$

$y(k) = C(k)X(k) + D(k)u(k)$

En sistemas lineales invariantes en el tiempo las matrices $A$, $B$, $C$  y  $D$ son constantes, lo que facilita el análisis y diseño.

## Construcción del Espacio de Estados a partir de Ecuaciones Diferenciales
### Ejemplo y Representación Múltiple
Ecuacion diferencial: 

$u(t) - F_{K} - F_{B} = m * a$

En terminos de entrada y salida:

$u(t) - Ky(t) - By^{°}(t) = My^{°°}(t)$

Discretizando la ecuacion:

$MY(k+2) - 2MY(k+1) + MY(k) + BTY(k+1) - BTY(k) + T^{2}KY(k) = UT^{2}$

### Metodología para el Espacio de Estados
Para construir el modelo, se sigue un proceso de:
1. Despejar la máxima derivada en la ecuación de diferencias.
2. Igualar la salida a una variable de estado.
3. Aplicar adelantos para obtener las derivadas.
4. Organizar los términos en matrices $A$, $B$, $C$ y $D$.
   
### Aplicacion
1. $MY(k+2) = UT^{2} - (BT-2M)Y(k+1) - (M-BT-T^{2}K)Y(k)$
2. $MY(k) = x_{1}(k)$
3. $MY(k+1)=x_{1}(k+1)=x_{2}(k)$
   
   $x_{2}(k+1)=MY(k+2)$
   
4. $x_{1}(k+1) = x_{2}(k)$
   
   $x_{2}(k+1) = U(k)T^{2} - (\frac{BT}{M} - 2)x_{2}(k) - (1-\frac{BT}{M}+\frac{T^{2}K}{M})x_{1}(k)$

![Figura de ejemplo](ejemplo.png)

Figura 1. Imagen representacion de estados.
   

## Conclusiones
El espacio de estados es una herramienta fundamental para modelar sistemas dinámicos complejos y multivariables. Permite diseñar controladores robustos al adaptar el modelo a las necesidades específicas de cada aplicación, facilitando la implementación de sistemas de control efectivos y flexibles.
