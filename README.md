# Enclavamiento de motor (simulacion):

Este es uno de mis primeros ejercicios, y aunque sea basico, son cosas que con el tiempo se olvidan si no se vuelven a usar. 

---

## Componentes utilizados: 
- Software: TIA Portal v16
- PLC Siemens Simatic S7-1200 V4.4
- Memorias o marcas virtuales (para permitir la simulacion)

---
## Logica del proyecto:
### 1) Repaso:
Dentro la configuracion de nuestro plc (virtual) previamente seleccionado en el software, nosotros podemos crear variables (tags) las cuales estan dotadas de ciertas caracteristicas, como: tipo de dato (booleano, entero, etc), y despues el proposito de dicha variable las cuales se indican con I: entrada(del plc), Q: salida(del plc), M: marca(la que vamos a usar). Las variables de tipo M nos permiten crear escenarios simulaciones con la posibilidad de forzar la variable a 1(encendido) o 0(apagado), es el tipo de variable que nos interes para esta simulacion. 

### 2) aplicacion; 
Vamos a crear tres tags(o variables) las cuales se van a llamar: start button[%M0.0], stop button[%M0.1], motor 2[%M1.0] todos con tipo de dato booleano(bool). Luego vamos a hacer uso del lenguaje escalera para disponer esas variables de l siguiente forma: 
(insertar imagen)

### 3) configuraciones antes de simular: 
primero se enciende el plc, se guardan los cambios y se simula, sobre las variables ahora vamos a tener ls libertar de cambiar sus estados para ver que pasa con el circuito (ponerlo a 1 o 0).
