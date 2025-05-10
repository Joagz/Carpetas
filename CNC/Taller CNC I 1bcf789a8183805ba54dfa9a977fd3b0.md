# Taller CNC I

Asignatura: TALLER DE CNC CAD CAM
Fecha de clase: 20/03/2025
Resumen de IA: El taller de CNC cubre la velocidad de corte, su cálculo y ejercicios prácticos, así como procesos de torneado como cilindrado, refrentado, ranurado y roscado, cada uno con sus características y técnicas específicas.
Tipo de clase: EETP 612

## Torno CNC (control numérico computarizado) :

### Velocidad de corte:

Es la velocidad expresada en metro por minutos (espacio en metros recorrido en un minuto), de un punto de la superficie que se mecaniza si es ésta quien lleva el movimiento de corte (torneado), o de un punto de la arista de corte se es la herramienta quien posee el movimiento de corte (fresadora, taladradora, cepilladora, etc).

Cuando el movimiento de corte es circular el punto a considerar es el mas alejado del eje de rotación. Es decir el diámetro exterior de la herramienta o pieza.

### Cálculo de la velocidad de corte:

$$
Vc [M/min] =\frac{\pi DN}{1000}
$$

$$
N[r/min]=\frac{1000Vc} {\pi D}
$$

Donde:

D: Diámetro mayor de la herramienta o pieza.

N: Número de revoluciones por minuto.

### Ejercicios:

1. ¿Cuál será la velocidad de corte que lleva una broca de 20mm si gira a una razón de N=320 rpm?
2. Calcular N que ha de dar una broca de 20mm para que su velocidad de corte sea 25[m/min].

### Respuestas:

1. Fórmula:
    
    $$
    Vc [M/min] =\frac{D.\pi .N}{1000}
    $$
    
    $$
    Vc [M/min] =\frac{20[mm].\pi .320[r/min]}{1000}
    $$
    
    $$
    Vc [M/min] =20,10
    $$
    
2. Fórmula:
    
    $$
    N\left[\frac r {min}\right]=\frac{1000.Vc}{ \pi . D}
    $$
    
    $$
    N\left[\frac r {min}\right]=\frac{1000.25[m/min]}{\pi . 20[mm]}
    $$
    
    $$
    N\left[\frac r {min}\right] = 397.88[r/min]
    $$

## Proceso de Torneado

- Cilindrado:
    - Modificar el diámetro de la pieza.
    - Avance paralelo al eje Z.
    - Casos especiales (cilindrado cónico y de arco).
- Refrentado
    - Generar superficie plana.
    - Avance perpendicular al eje Z.
    - Velocidad de rotación (constante o variable).
- Ranurado
    - Obtener ranuras.
    - Variedad de formas según la herramienta.
    - Caso particular: Tronzado.
- Roscado
    - Caso particular de cilindrado.
    - Elevado número de pasadas.

# Torno controlador FANUC MATE OI-TC

### Composición de un torno CNC: 

Panel de control
- Pantalla
- Teclado
- Interruptores varios
- Led indicadores
- Comandos
- Encendido

En el equipo

- Servo amplificadores
- Servo motores
- Encoder
- Encendido

## Importante
- Los accidentes ocurren una vez que el operador a tomado confianza con la maquina.
- Un error puede costar muy caro, tanto como para el operador como para la empresa.
- Recordar que la máquina NO PERDONA.
- Mantenerse alejado de las partes móviles.
- El operador debería formar un método de trabajo, para que sea cíclico y repetitivo, para reducir los riesgos.
- Mantener la máquina y el lugar de trabajo limpio y ordenado.
- Limpiar la máquina con frecuencia autoestablecida.
- Recordar: LIMPIAR ES REVISAR.
- Verificar los niveles de lubricantes y refrigerantes.
- Ante cualquier anomalía informar al superior directo.

## Características principales
- Todos los movimientos CKA6150 tanto en X como en Z y la torreta son comandados totalmentepor el CNC FANUC. La máquina tiene todas las ociones de torneado convencionales, así como torneado interno y externo, torneado cilíndrico, frenteado, roscado métrico y withworth, torneado cónico, interpolación en ambos ejes. (Encoder incorporado). 
- Cabezal con motor de variador de frecuencia, por lo cual la máquina posee velocidad de corte constante e infinitamente variable, dentro de las 3 gamas que posee (alta, media y baja).
- Las guías son sobre bolillas recirculantes, las bancadas templadas y rectificadas  los engranajes en el cabezal templados y rectificados.
- Lubricación forzada, completa tantos en las guías como en el cabezal y la caja.
- Pasaje de husillo 82mm.
- Torre de 6 posiciones (OPCIONAL) DIAMETRO MAX. TORNEADO EXT. 400mm.
- Freno automático.
- Entrada de tarjeta de memoria (MEMORY CARD) (puede grabar en su pc y llevar al CNC o viceversa). 
- Entrada RS232 para PC

# Controlador

**JOG**: manual

**AUTO**: automático para producción

**MDI**: confección de programa y se borra automáticamente al cocluir éste

**EDIT**: tecla para editar un programa

**HANDEL** (HANDLE??): permite mover el carro de forma manual

**REF**: la máquina vuelve a home

## **JOG (P/P)**

En este modo se pueden desplazar los carros en forma manual (paso a paso) con las teclas de dirección.

## **AUTOMÁTICO (AUTO)**

Se emplea en la ejecución de un programa de pieza. El control llama a un bloue tras otro y los interpreta.

## **SEMIAUTOMÁTICO (MDI)**

Se pueden introducir bloques de un programa de piezas en la memoria intermedia.

El control ejecuta los bloques introducidos y borra después la memoria intermedia para ejecutar nuevas entradas.

Después de introducir la secuencia a través del teclado de mando, se ejecuta. Durante el mecanizado ya no es posible editar la secuencia.

#3 **EDICIÓN (EDIT)**

En este modo se pueden introducir programas de piezas.

En este modo pueden desplazarse los carros con un salto incremental de $1\dots 10.000 \mu m$


## **HANDLE**

El incremento debe ser mayor que la resolución de la máquina, de lo contario no se producirá desplazamiento.

En este modo pueden desplazarse los carros con un salto incremental de $1\dots 10.000 \mu m$, por medio de las teclas de dirección.

**PUNTO DE REFERENCIA (REF)**

Este modo se emplea para la aproximación al punto de referencia ($R$).

Al llegar al punto de referencia, la memoria de posición actual se estabalece sobre el valor de las coordenas del punto de referencia. Con esto, el contol reconoce la posición de la herramienta en la zona de trabajo.

## **OPERATION SELECT**

**SINGLE BLOCK:** el programa funciona bloque a bloque

**DRY RUN:** es para quue corra el programa completo

**BLOCK SKIP:** no se ejecutan los bloques que tengan por delante una '/'

**MC LOCK:** bloqueo de ejes, el programa funciona sin movimientos de eje

**OPT STOP:** el programa se detiene cada vez que lea $M01$

**DNC:** para trabajar con la PC por paquetes

**COOLANT:** refrigerante

**WORK LAMP:** iluminación

**F3:** para paquetes de instrucciones (no se utiliza)

## **SPEED MULTIPLE**

**X1 F0:** milésima (para movimientos en G0 o manualmente)

**X10 25%:** centésima (para movimientos en G0 o manualmente)

**X100 50%:** décima (para movimientos en G0 o manualmente)

**F1:** ... no se utiliza ...

**F2:** ... no se utiliza ...

**100%:** corre el programa con velocidades cargadas

**SPDL DEC:** reduce hasta el 50% las RPM (10% por pulso)

**SPDL 100%:** RPM cargadas en el programa

**SPDL INC:** aumenta hasta el 50% las RPM (10% por pulso)

## **SPINDLE:** 
funciona únicamente en forma manual

**SPDL CCW:** giro en sentido antihorario

**SPDL CW:** giro en sentido horario

**SPDL STOP:** parada

## **OVERRIDE:** 
avances lentos, con el potenciómetro podemos ir regulando porcentualmente el avance, en modo manual y automático.

## **CYCLE**

**BLANCO:** comienzo del ciclo

**ROJO:** fin del ciclo

## **CURSORES**

Permite mover en forma manual el carro porta herramienta

# Introducción de programas

Los programas de piezas y subprogramas o subrutinas, se peuden introducir en los modos EDIC.

## Llamar a un programa

- Cambiar al modo EDICIÓN

- Pulsar la tecla *PRGRM*

- Con la tecla de software *BIBLIO* se ven los programas existentes

- Escribir el ID del programa (por ej. O777)

- Para un nuevo programa, pulsar *INSRT*

- Para un programa ya existente pulsar { $\downarrow$ }
