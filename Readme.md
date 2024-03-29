# Proyectos de Arduino

[![displays.png](https://i.postimg.cc/mgWKHGX5/displays.png)](https://postimg.cc/2VT0sgfQ)

Proyectos de Arduino y nodeMCU ESP8266

## Índice
- [Herramientas](#herramientas)
- [Arduino](#arduino)
    - [Señales digitales](#señales-digitales)
        - [Salidas digitales](#salidas-digitales)
            - [Blink](#blink)
            - [Display de 7 segmentos](#display-de-7-segmentos)
            - [Señales de trafico](#señales-de-trafico)
            - [Circuito de escalera](#circuito-de-escalera)
            - [Auto fantastico](#auto-fantastico)
            - [Flux capacitor](#flux-capacitor)
        - [Lectura de entradas](#lectura-de-entradas)
            - [Botones](#botones)
            - [PIR](#pir)
            - [HC-SR04](#hc-sr04)
    - [Señales analógicas](#señales-analógicas)
        - [Salidas analógicas](#salidas-analógicas)
            - [PWM](#salidas-pwm)
            - [Servo](#servo)
            - [L293D](#l293d)
        - [Lectura de entradas](#lectura-de-entradas)
            - [Potenciómetro](#potenciómetro)
            - [Sensores](#sensores)
            - [Sensor de temperatura](#sensor-de-temperatura)
    - [Extras](#extras)
        - [Serial Event](#serial-event)
- [nodeMCU ESP8266](#nodemcu-esp8266)
    - [Basico](#basico)
        - [Blink](#blink)
        - [Entrada analógica](#entrada-analógica)
        - [Funciones](#funciones)
        - [Pantalla OLED](#pantalla-oled)
        - [Puerto serie](#puerto-serie)
    - [Servidor web](#servidor-web)
        - [Crear un punto de acceso](#crear-un-punto-de-acceso)
        - [Unirse a un punto de acceso](#unirse-a-un-punto-de-acceso)
        - [Salida analógica](#salida-analógica)
    - [Microcotroladores por puerto serie](#microcontroladores-por-puerto-serie)


# Herramientas
Hardware y software utilizados:
- Microcontrolador: 
    - Arduino Uno o Mega 2560
    - NodeMCU ESP8266 V2 o V3
- IDE:
    - [Arduino](https://www.arduino.cc/en/Main/Software) o [VS Code](https://code.visualstudio.com/download) + [Arduino CLI](https://arduino.github.io/arduino-cli/0.23/installation/#use-the-install-script) + [python-pyserial](https://pypi.org/project/pySerial/) 
- Librerías:
    - `Servo`
    - `Wire`
    - `Adafruit_GFX`
    - `Adafruit_SSD1306`
    - `ESP8266WiFi`
    - `WiFiClient`
    - `ESP8266WebServer`

# Arduino
## Señales digitales
Proyectos que manejan entradas y salidas digitales.

### Salidas digitales
#### [Blink](https://github.com/adnksharp/iBlink)
Sketch para manipular salidas digitales:

- El programa hace uso de la función `digitalWrite` para manipular salidas digitales, las cuales se pueden encender o apagar cambiando el valor de una variable boolean.

#### [Display de 7 segmentos](https://github.com/adnksharp/iDsegments)
Sketch para manipular salidas digitales de uno o más displays de 7 segmentos usando:

- Una matriz de valores booleanos para representar los dígitos del display.

- En el caso de usar varios displays, una función para cambiar el valor que se muestra en cada uno de ellos.

#### [Señales de trafico](https://github.com/adnksharp/iTL)
Sketch para manejar señales de trafico:

##### Una señal de trafico
- El programa hace uso de la función `digitalWrite` para manipular salidas digitales, las cuales se pueden encender o apagar cambiando el valor de una variable boolean.
- Para esto, se usan tres vectores correspondientes a:

    - El tiempo de encendido de la señal de trafico.
    - El pin de salida de la señal de trafico.
    - El estado de la señal de trafico.

##### Varias señales de trafico
El programa para una señal de trafico funciona para multiples semaforos. Para esto:

- Se usa una matriz en lugar de un vector para el estado de las señales de trafico.
- Se usa un vector únicamente para las salidas de las señales de trafico de color rojo.

Mientras que en el sketch de una señal de trafico, los catodos de los LEDs de los semaforos se conectan a GND, en el sketch de varias señales de trafico, los catodos de los LEDs de los semaforos se conectan a los pines de salida digitales al igual que los anodos.


#### [Circuito de escalera](https://github.com/adnksharp/iSC)
Sketch para controlar el encendido de un relevador con dos botones.

#### [Auto fantastico](https://github.com/adnksharp/iKRL)
Simulación de las luces del auto fantastico (Knight Rider).

#### [Flux capacitor](https://github.com/adnksharp/iFC)
Simulación de la iluminación del flux capacitor de Back to the Future.

### [Lectura de entradas](https://github.com/adnksharp/iDread/blob/base/DigitalRead)
Sketch para leer entradas digitales. El programa hace uso de la función `digitalRead` para leer entradas digitales:

- El programa imprime en el puerto serie el valor de la entrada digital usando el condicional `if`.

#### [Botones](https://github.com/adnksharp/iDbuttons)
Sketch para manejar botones:

##### [Buttons](https://github.com/adnksharp/iDbuttons/blob/base/Buttons/Buttons.ino)
En este programa se usa la función `digitalRead` para leer entradas digitales dentro de dos funciones:

- El boton 1 altera el valor de una variable.
- La función 1 hace que un LED se encienda cuando se presiona un botón 2.
- La función 2 hace que uno de tres LEDs se encienda cuando se presiona el botón 1 dependiendo del valor de la variable.

##### [Counter](https://github.com/adnksharp/iDbuttons/blob/base/Counter/Counter.ino)
Para que un LED se encienda n cantidad de segundos:
- Un boton funciona como un contador.
- Un segundo boton funciona como un `execute`.

#### [PIR](https://github.com/adnksharp/iPIR)
Uso de un sensor de infrarrojos para detectar movimiento. Para esto es necesario detectar si el sensor esta en alto o si ah pasado el suficiente tiempo desde la última detección para activar un LED según sea el caso.

#### [HC-SR04](https://github.com/adnksharp/iHCSRS04)
Uso de un sensor de ultrasonico *HC-SR04* para medir la distancia de un objeto.

## Señales analógicas
Proyectos que manejan entradas y salidas analógicas.

### Salidas analógicas
#### [Salidas PWM](https://github.com/adnksharp/iAwrite)
Sketch para simular salidas analógicas usando PWM:

- Usando la función `analogWrite` se puede manipular la salida analógica. En este sketch, usando un variable entre 0 y 255, se puede manipular la salida analógica.

#### [Servo](https://github.com/adnksharp/iServo/blob/base/Servo/Servo.ino)
Crear una función para manipular un servomotor.

#### [L293D](https://github.com/adnksharp/iL293D)
Control de velocidad y dirección de motores usando un puente H.

### [Lectura de entradas](https://github.com/adnksharp/iAread)
Sketch para leer entradas analógicas. El programa hace uso de la función `analogRead` para leer entradas analógicas, las cuales representan normalmente sensores resistivos:

#### [Potenciómetro](https://github.com/adnksharp/iAread/blob/base/AnalogRead/AnalogRead.ino)
Creando una función para leer un potenciómetro, se puede usar la función `analogRead` para leer la entrada analógica e imprimirla en el puerto serie.

#### [Sensores](https://github.com/adnksharp/iAread/blob/base/Sensors/Sensors.ino)

1. Usando la libreria `Servo` se puede manipular un servo usando la función `analogRead` para leer la entrada analógica mapeada a un valor de 0 a 180.
2. Usando la función `analogWrite` se puede manipular una salida analógica entre 0 y 255.
3. Usando un botón se puede bloquear el punto 2 para definir la salida analógica en 255.

#### [Sensor de temperatura](https://github.com/adnksharp/iTMP)
Sketch para leer la temperatura de un sensor de temperatura *TMP36* y la función `analogRead` para leer la entrada analógica.

## Extras

### [Serial Event](https://github.com/adnksharp/iSevent)
Uso de la función [`SerialEvent`](https://www.arduino.cc/reference/en/language/functions/communication/serial/serialevent/) para manejar la lectura de una entrada del puerto serie.

# nodeMCU ESP8266
## Basico
Proyectos disponibles para el nodemcu ESP8266 y Arduino.

### [Blink](https://github.com/adnksharp/eBlink)
Sketch para encender un LED y apagarlo. En el caso del nodeMCU, el sketch permite manejar el LED integrado en el nodemcu.

### [Entrada analógica](https://github.com/adnksharp/eAnalog)
Manejo de la función `analogRead` para leer entradas analógicas.

### [Funciones](https://github.com/adnksharp/eFunctions)
Creación de funciones dentro de un Archivo de Arduino y un Archivo de C++ para controlar salidas digitales.

### [Pantalla OLED](https://github.com/adnksharp/eOLED)
Sketch para manejar una pantalla OLED por i2c.

### [Puerto serie](https://github.com/adnksharp/ieSerial)
Sketch para comunicar microcontroladores por puerto serie.

## Servidor web
Proyectos usando librerias de servidor web para el nodemcu ESP8266.

### [Crear un punto de acceso](https://github.com/adnksharp/eAP)
Crear un AP con una dirección IP y una contraseña.

### [Unirse a un punto de acceso](https://github.com/adnksharp/eLServer)
Unirse a un punto de acceso creado previamente y crear un servidor web.

### [Salida analógica](https://github.com/adnksharp/eLSPWM)
Crear un servidor web http para manejar una salida analógica.

## [Microcontroladores por puerto serie](https://github.com/adnksharp/ieSerial)
Proyectos para comunicar microcontroladores por puerto serie.
