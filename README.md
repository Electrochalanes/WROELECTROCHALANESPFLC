Electrochalanes Club de Robótica PFLC
====

Preparatoria Federal Lázaro Cárdenas, Tijuana, Baja California, México.

## Integrantes
Cano Andrade Raúl Daniel

Jurado Hernández Marco Tonatiuh

Sotelo Montoya Seth Uriel

Coach: Garcia Garcia Manuel Alexis

## Contenido

* `t-photos` contiene 2 fotos del equipo (una foto oficial y una foto divertida con los miembros del equipo)
* `v-photos` contiene 6 fotos del vehículo (desde cada una de las perspectivas)
* `video` contiene un enlace a un video donde se demuestra la conducción de el vehículo
* `schemes` contiene uno o más esquemáticos en JPEG, PNG o PDF de los componentes electromecánicos (componenetes electrónicos y motores) utilizados en el vehículo y como conectarlos entre sí.
* `src` contiene los códigos que se emplearon en todos los componentes programados para la competencia.
* `models` aquí se encuentran los modelos 3D y los componentes cortados en láser que se utilizaron para lograr el vehículo.

## Introduction

¿De qué manera conseguimos resolver cada uno de los desafíos de la competencia?
Primeramente se realizó una lista de componentes electrónicos a utilizar:
* Raspberry Pi 5
* Servomotor tipo SG90 marca Steren
* Micromotorreductor Pololu HPCB 6V 75:1
* Cámara web 4k 60fps USB
* Motorshield para Raspberry Pi SB Components
* Sensor ultrasónico SR04
* Batería lipo 7.4V 400mAh
* Powerbank

## Bases del diseño
Posterior a la selección de componentes se realizó el diseño del auto. ¿En qué se basó nuestro diseño?
Se llego a este diseño con la idea de crear una transmisión delantera que fuera sencilla de armar e imprimir en 3D, mientras que en las llantas traseras del automóvil controlan la velocidad y el avance de el carro a través de un sistema de engranajes conectado al motor, este mueve a las llantas girando un tornillo sin fin anclado a estas mismas.
La transmisión delantera es controlada por el servomotor que gira hacia la derecha o izquiera según la señal que reciba, delante de la transmisión colocamos una base para un sensor ultrasónico el cuál se encarga de detectar los muros de la pista y mandar una señal para el giro del vehículo. Encima de la transmisión pusimos una base para la cámara web encargada de la detección de obstaculos en el desafío e obstaculos. Y en medio de la base principal se encuentra la placa de programación "Raspberry Pi 5" y su motorshield, encima de esta se colocó un segundo piso para poner las fuentes de alimentación. Toda la realización del diseño de cada una de las piezas y acomodo de los componentes se realizó desde 0 a través de Fusion Autocad para ser cortadas en láser o imprimidas en 3D.

## Funcionamiento del código del desafío abierto
Para el desafío abierto utilizamos un código basado en las librerías:"gpiozero" y "time".

*Primero, al iniciar el automovil y activar el código este le da una señal al servo para mantenerse en el punto 0 (esto para que las llantas apunten recto al comienzo), posterior al acomodo este comenzará a avanzar en linea recta. La base del movimiento de nuestro auto recae en el sensor ultrasónico, este al detectar la distancia deseada envía una señal que es recibida por la placa, la cual manda la orden al servomotor de girar -49 grados, logrando así girar a la izquierda. Este proceso se repite un total de 12 veces, después de completar ese ciclo el auto se detiene dentro de la sección donde comenzó, dando así un total de 3 vueltas completas al circuito.

## Funcionamiento del código para el desafío de obstaculos

