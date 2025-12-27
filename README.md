# Enclavamiento de motor (simulacion):

Este es uno de mis primeros ejercicios en programación de PLC. Aunque se trata de una lógica básica, es fundamental porque son conceptos que, si no se practican, tienden a olvidarse con el tiempo.
El ejercicio consiste en un enclavamiento de motor:
• 	El motor se enciende mediante un botón de inicio de tipo normalmente abierto.
• 	Se mantiene activo mientras la condición de arranque esté presente.
• 	Al presionar el botón de parada, la señal se interrumpe y el motor se apaga.
Este tipo de prácticas son la base para construir automatismos más complejos y confiables en el futuro.

---

## Componentes utilizados: 
- Software: TIA Portal v16
- PLC Siemens Simatic S7-1200 V4.4
- Memorias o marcas virtuales (para permitir la simulacion)

---
## Logica del proyecto:
### 1) Repaso:
Dentro la configuracion de nuestro plc (virtual) previamente seleccionado en el software, nosotros podemos crear variables (tags) las cuales estan dotadas de ciertas caracteristicas, como: tipo de dato (booleano, entero, etc), y despues el proposito de dicha variable las cuales se indican con I: entrada(del plc), Q: salida(del plc), M: marca(la que vamos a usar). Las variables de tipo M nos permiten crear escenarios simulaciones con la posibilidad de forzar la variable a 1(encendido) o 0(apagado), es el tipo de variable que nos interes para esta simulacion. 

### 2) Tags(marcas/variables): 
Vamos a crear tres tags(o variables) las cuales se van a llamar: start button[%M0.0], stop button[%M0.1], motor 2[%M1.0] todos con tipo de dato booleano(bool). Luego vamos a hacer uso del lenguaje escalera para disponer esas variables de l siguiente forma: 
![Configuracion](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/01%20esquema%20de%20conexionado%20de%20las%20marcas%20.jpg)

### 3) configuraciones y simulacion: 
configuracion: 
![Configuracion2](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/02%20pasos%20para%20configurar.jpg)

guardado y encendido: 
![Configuracion3](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/03%20pasos%20para%20encender.jpg)

inicio de simulacion y forzado: 
![Simulcion0](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/04%20simulacion%20.jpg)

de esa forma se crea el proyecto y se inicia la simulacion, ahora veamos el comportamiento del enclavamiento...

### 4) Enclavamiento: 
Ahora lo que nos interesaba del proyecto, ver el enclavamiento en accion. 

1) Vamos a forzar a Start Button de 0 a 1 (indicando que el operador lo presiono):
![Simulcion1](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/05%20boton%20sin%20presionar%20.jpg)

2) El motor esta energizado, ahora vamos a forzar a Start Button de 1 a 0 (indicando que se dejo de presionar):
![Simulcion2](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/06%20boton%20presionado%20.jpg)

3) El enclavamiento dejo encendido nuestro motor, si queremos apagrlo vamos a forzar a Stop Button de 0 a 1:
![Simulcion3](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/07%20boton%20sin%20presionar%20de%20vuelta%20.jpg)

4) Apagado del motor y fin de la simulacion:
![Simulcion4](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/08%20boton%20stop%20presionado%20.jpg)

## Comentarios finales: 
A continuacion se deja el archivo del proyecto para que cualquier persona con acceso al software pueda simularlo el mismo: 
