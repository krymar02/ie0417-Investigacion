# Curso: Diseño de Software para Ingeniería  
## Tema: Ingeniería de Software para Sistemas Embebidos e IoT  
### Grupo 6  

---

## Estudiantes
- Daylan Pereira Arroyo
- Kryssia Martínez Martínez B84636
- María José Guevara Matarrita C13476 
---

## Índice
1. [Introducción a los sistemas embebidos](#i-introducción-a-los-sistemas-embebidos)  
2. [Ejemplos de sistemas embebidos](#ii-ejemplos-de-sistemas-embebidos)  
3. [Internet de las Cosas (IoT)](#iii-internet-de-las-cosas-iot)  
4. [Tecnologías clave](#iv-tecnologías-clave)  
5. [Caso práctico](#v-caso-práctico)  
6. [Áreas laborales](#vi-áreas-laborales)  
7. [Conclusiones](#vii-conclusiones)  
8. [Bibliografía](#viii-bibliografía-en-formato-ieee)  

---

## I. Introducción a los sistemas embebidos
 
*(Desarrollar contenido aquí)*  

---

## II. Ejemplos de sistemas embebidos
  
*(Desarrollar contenido aquí)*  

---

## III. Internet de las Cosas (IoT)

El **Internet de las Cosas (IoT)** es una **infraestructura socio-técnica** que interconecta **cosas** físicas y virtuales (equipos, sensores, actuadores y objetos cotidianos, así como sistemas industriales) mediante **redes de comunicaciones** y **plataformas de servicios** para **capturar, transportar, procesar y convertir datos en acciones** de forma segura y, en muchos casos, autónoma. Esta visión se alinea con la definición de **ITU-T Y.2060/Y.4000**, que describe a IoT como una “infraestructura global para la sociedad de la información” sustentada en la interconexión de *cosas*, y con el encuadre de **NIST** sobre dispositivos y productos conectados a Internet. [ITU][1], [csrc.nist.gov][2], [NIST][11]

**Arquitectura y flujo de datos (visión por capas):**  
1) **Capa de percepción**: *cosas* con **sensores** y **actuadores** que miden el entorno y ejecutan órdenes. [ITU][1]  
2) **Capa de conectividad/red**: redes IP y **gateways** que transportan telemetría y comandos; protocolos ligeros como **MQTT** (modelo *publish/subscribe* con QoS 0/1/2). [OASIS MQTT][3]  
3) **Capa de servicios/compute**: **edge/fog/cloud** para **ingesta → almacenamiento → análisis/ML → orquestación** (reglas, alertas, control). [ITU][1], [NIST][11]  
4) **Capa de aplicación**: dashboards, APIs y procesos de negocio que entregan valor (automatización, eficiencia, trazabilidad).

**Capacidades nucleares:**  
- **Identidad y direccionamiento** por dispositivo (certificados por dispositivo, uso de TLS/IPv6 cuando aplica). [NIST][11]  
- **Interoperabilidad y gobierno de datos** (modelos de datos, esquemas de tópicos, versionado). [OASIS MQTT][3], [ITU][1]  
- **Gestión del ciclo de vida**: *provisioning*, configuración, **actualizaciones OTA**, retirada segura. [NIST][11]  
- **Seguridad desde el diseño**: autenticación mutua, cifrado en tránsito, control de acceso de mínimo privilegio, monitoreo continuo. [NIST][11]

**Modos de interacción:**  
- **M2M** (dispositivo↔dispositivo o dispositivo↔gateway),  
- **Device-to-Cloud** y **Cloud-to-Device**, típicamente sobre **MQTT** por su eficiencia y fiabilidad en enlaces inestables. [OASIS MQTT][3]

---

### Sensores y actuadores

- **Sensores:** transductores que **miden** variables físicas (temperatura, humedad, vibración, pH, etc.) y generan datos digitales. (NIST los clasifica como dispositivos IoT típicos). [csrc.nist.gov][2]  
- **Actuadores:** componentes que **ejecutan acciones** (abrir una válvula, encender un relé, mover un servomotor) a partir de comandos provenientes de la plataforma o de otros dispositivos (modelo “cosas-a-cosas” descrito por ITU). [ITU][1]

---

### Comunicación M2M (machine-to-machine)

La **M2M** es el intercambio **directo** de datos entre “cosas”, con o sin intervención humana. En IoT se implementa comúnmente con **MQTT**, estandarizado por **OASIS** (y también ISO), que define **QoS 0/1/2**, sesiones persistentes y *retain* para asegurar entrega eficiente en redes de baja potencia o alta latencia. [docs.oasis-open.org][3]

---

### Ejemplos por dominio

- **Casas inteligentes:** automatización de iluminación, climatización, seguridad y ahorro energético; arquitecturas con sensores/actuadores y *gateways* hacia la nube. [PMC][4]  
- **Monitoreo de salud:** telemetría de signos vitales y seguimiento remoto con redes de sensores corporales y *gateways* seguros. [PMC][4]  
- **Agricultura de precisión:** sensores de suelo/ambiente, estaciones meteorológicas y análisis para optimizar riego y fertilización; beneficios y desafíos (datos, ciberseguridad, adopción). [PMC][5]

> **Interoperabilidad en el hogar:** el estándar **Matter** busca compatibilidad entre marcas y plataformas (Apple/Google/Amazon), reduciendo fricción de integración. [Axios][6]

---
## IV. Tecnologías clave

### Lenguajes
Los lenguajes de programación proporcionan instrucciones al microprocesador, permitiendo que el dispositivo realice operaciones. El compilador actúa como puente entre las instrucciones y el microcontrolador que las ejecuta. Seleccionar un lenguaje apropiado es fundamental para definir las capacidades y funcionalidades del producto final en sistemas embebidos.

### Lenguajes comunes en sistemas embebidos
- C
- C++
- Assembly
- BASIC
- Java
- JavaScript

#### C
- Lenguaje compilado utilizado para crear aplicaciones de bajo nivel en microcontroladores.
- Amplio uso en aplicaciones industriales.
- Requiere conocimientos avanzados de codificación.
- Destaca por eficiencia y control sobre recursos del sistema.

#### C++
- Lenguaje eficiente con biblioteca estándar rica.
- Facilita codificación modular y rápida gracias a la programación orientada a objetos.

### Ventajas y Desventajas de C++ en Sistemas Embebidos

| Aspecto | Ventajas | Desventajas |
|---------|----------|-------------|
| Facilidad de uso y escalabilidad | Diseño modular, plantillas y herencia que facilitan reutilización y escalabilidad | Difícil de aprender; muchas construcciones aumentan la curva de aprendizaje |
| Portabilidad | Código reutilizable entre dispositivos | Plantillas complejas pueden causar incompatibilidades |
| Biblioteca estándar | Herramientas optimizadas listas para usar | Uso inadecuado puede afectar rendimiento |
| Estabilidad y soporte | Programas confiables, comunidad amplia, lenguaje maduro | Mantener bases de código grandes es desafiante |
| Interoperabilidad y aprendizaje | Facilita aprender otros lenguajes modernos | Gestión manual de memoria; no hay recolector de basura automático |
| Interfaces gráficas (GUI) | Facilita implementación de GUI | Consumo de recursos mayor que C puro |
| Rendimiento | Compiladores modernos optimizan velocidad y memoria | Excepciones o RTTI pueden reducir eficiencia; plantillas complejas afectan rendimiento |
| Mantenimiento y base de código | Diseño modular facilita extensión | Complejidad del lenguaje dificulta mantenimiento; riesgo de inconsistencias |

---

#### Python
- Lenguaje de programación accesible, fácil de aprender y con sintaxis clara.
- Popular para prototipos rápidos, automatización y scripting.
- MicroPython adapta Python a tareas de hardware y sistemas integrados.
- Ideal para desarrollo ágil, aunque no tan eficiente como C/C++ en tiempo real.

### Ventajas y Desventajas de Python en Sistemas Embebidos

| Aspecto | Ventajas | Desventajas |
|---------|----------|-------------|
| Sintaxis y facilidad de uso | Lenguaje accesible, sintaxis clara, rápido desarrollo | No eficiente para tareas críticas de tiempo real |
| Prototipado rápido | Creación de prototipos ágil, MicroPython para hardware | Limitado al hardware compatible; no ideal para sistemas muy restringidos |
| Flexibilidad y adaptabilidad | Uso en scripting, automatización y pruebas rápidas; compatible con varias plataformas | Gestión de memoria menos eficiente; velocidad de ejecución más lenta |
| Comunidad y soporte | Amplia comunidad y gran cantidad de librerías | Algunas librerías estándar no optimizadas para sistemas embebidos |
| Aplicaciones recomendadas | Prototipos IoT, sistemas educativos, secuencias de comandos | No recomendable para aplicaciones críticas de alto rendimiento o tiempo real |

---

### Cómo elegir el lenguaje adecuado
La elección depende de la familiaridad del programador, el tipo de proyecto, la industria y los requisitos del sistema. Los sistemas embebidos requieren equilibrar necesidades técnicas con capacidades y limitaciones del lenguaje.

### Plataformas
##Arduino
### 1. Qué es Arduino
Arduino es una plataforma de hardware y software de código abierto que permite a los usuarios crear proyectos electrónicos interactivos. Consiste en placas con microcontroladores y un entorno de desarrollo que facilita programarlas para controlar sensores, actuadores y otros dispositivos electrónicos.

  - Las placas Arduino pueden leer entradas: luz en un sensor, un dedo en un botón o un mensaje de Twitter, y convertirlas en una salida: activar un motor, encender un LED, publicar algo en línea.
  - Puede indicarle a su placa qué hacer enviando un conjunto de instrucciones al microcontrolador de la placa.
  - Se utiliza el lenguaje de programación Arduino (basado en Wiring), y el Software Arduino (IDE), basado en Processing. 
  - Se daptó a nuevas necesidades y desafíos, diferenciando su oferta desde simples placas de 8 bits hasta productos para aplicaciones de IoT, dispositivos portátiles, impresión 3D y entornos integrados.


### 2. Entorno de Desarrollo Integrado (IDE)
El IDE de Arduino es un software que permite:
- Escribir, verificar y cargar código en las placas Arduino.
- Utilizar bibliotecas que agregan funcionalidades, como controlar sensores, pantallas o módulos adicionales.
- Trabajar tanto en escritorio (Arduino Software IDE) como en línea (Arduino Cloud Editor).

**Tipos de IDE:**
1. **IDE de escritorio**: Para trabajar sin conexión y con control completo de las bibliotecas.
2. **Arduino Cloud Editor**: IDE en línea que guarda los bocetos en la nube, actualiza automáticamente las funciones y permite acceder a los proyectos desde cualquier dispositivo conectado.
3. **Arduino Cloud**: Plataforma para proyectos IoT; permite monitorear, controlar y rastrear dispositivos de manera remota.

### 3. Uso del IDE
- Conecta la placa Arduino al computador, el IDE la reconoce automáticamente.
- Se pueden cargar **bocetos** (programas) directamente a la placa.
- Ejemplo básico: el programa “Blink” hace parpadear un LED integrado en la placa.
- El IDE permite modificar la velocidad del parpadeo ajustando parámetros en el código.

### 4. Bibliotecas
- Proporcionan funcionalidades adicionales para manejar hardware y datos.
- Pueden instalarse desde el IDE de escritorio o Arduino Cloud Editor.
- Permiten reutilizar código y acceder a ejemplos preconfigurados.

### 5. Arduino Cloud
Arduino Cloud es la plataforma en línea de Arduino que permite:
- Conectar, monitorear y controlar dispositivos desde cualquier lugar.
- Crear automáticamente código para los dispositivos, agregando líneas específicas para personalización.
- Configurar variables y tipos de datos (int, float, boolean, etc.) que se generan en los bocetos.
- Conectar dispositivos a Wi-Fi y generar funciones que responden a eventos desde la nube.
- Crear **paneles de control (dashboards)** para visualizar y controlar los dispositivos de forma gráfica usando **widgets**.
- Compatible con placas oficiales Arduino (algunas requieren tarjetas SIM o gateways según el modelo).

### 6. Configuración de red
- Para conectar dispositivos a Arduino Cloud, se deben permitir ciertos dominios y puertos en firewalls de red:
  - mqtts-up.iot.arduino.cc → 8884
  - mqtts-sa.iot.arduino.cc → 8883
  - wss.iot.arduino.cc → 8443
  - NTP → puerto 123 UDP
- Recomendado para redes escolares o domésticas que bloqueen ciertos puertos.

### 7. Aplicaciones prácticas
- Educación y prototipado rápido.
- Proyectos IoT con control remoto de sensores y actuadores.
- Automatización y monitoreo de dispositivos electrónicos.
- Interacción visual mediante dashboards personalizados en la nube.


# Raspberry Pi :

## ¿Qué es?
La Raspberry Pi es una computadora de bajo costo y tamaño compacto, capaz de ejecutar Linux y conectarse a monitores, teclados y mouse. Permite aprender programación y realizar proyectos de computación y electrónica, desde navegación en internet y multimedia, hasta proyectos de IoT y automatización.

## Hardware
- Tamaño compacto (tarjeta de crédito)
- Puertos USB, HDMI, Ethernet, Wi-Fi y Bluetooth
- Pines GPIO para interactuar con sensores y actuadores

## Sistemas operativos
- **Raspbian**: Sistema oficial basado en Linux, optimizado para Raspberry Pi.
- **NOOBS**: Instalador que permite elegir y configurar diferentes sistemas operativos fácilmente.
- Soporta software para ofimática, programación, multimedia y proyectos IoT.

## Usos comunes
1. **Mini PC**: navegación, edición de documentos y multimedia.
2. **Servidor de impresión Wi-Fi**: conectar impresoras antiguas a la red.
3. **Máquina Arcade**: emulación de consolas clásicas con Recalbox o Retropie.
4. **Servidor web**: Apache, WordPress, MySQL.
5. **Reproductor multimedia**: con KODI.
6. **Sistema NAS**: almacenamiento centralizado con OpenMediaVault.
7. **Domótica**: control de luces, temperatura, seguridad, y más con Domoticz.

---

## Comparativa Raspberry Pi 4 vs Arduino UNO

| Característica | Arduino UNO | Raspberry Pi 4 |
|----------------|------------|----------------|
| Tipo | Microcontrolador | Mini PC |
| Sistema operativo | Ninguno | Linux (Raspbian) |
| Pines digitales | 14 | 40 |
| Pines analógicos | 6 | 0 (requiere ADC externo) |
| Lenguaje | C/C++ | Python |
| Multitarea | No | Sí |
| Uso ideal | Control directo de sensores y actuadores | Procesamiento de datos, multimedia, IoT |
| Ventaja principal | Respuesta inmediata y control preciso | Potencia de cálculo, multitarea y conectividad |

**Resumen :**  
- **Raspberry Pi**: ideal para proyectos que requieren potencia de cálculo, multitarea o conectividad.  
- **Arduino**: más indicado si se necesita control inmediato de sensores y actuadores.  
- Se pueden combinar ambas plataformas para aprovechar lo mejor de cada una. Ya que arduino recoge datos de sensores y controla actuadores; Raspberry Pi procesa la información, maneja aplicaciones complejas y la sube a la nube.


- **ESP32**: Microcontrolador potente con Wi-Fi y Bluetooth integrados; económico y popular en IoT.
# Exposición: ESP32

## ¿Qué es ESP32?
El ESP32 es un microcontrolador y SoC (System on Chip) con Wi-Fi y Bluetooth integrados, diseñado por Espressif Systems. Es versátil, compacto y de bajo costo, ideal para proyectos IoT, domótica, robótica, dispositivos portátiles y automatización industrial.

### Características principales
- **Diseño robusto**: funciona en rangos de temperatura de -40°C a +125°C, confiable en entornos industriales.
- **Consumo ultrabajo**: ideal para dispositivos móviles y IoT.
- **Alta integración**: incluye antena, amplificadores, filtros y gestión de energía.
- **Conectividad**: Wi-Fi, Bluetooth clásico y BLE, soporte para protocolos como Zigbee, ESP-NOW y Matter.
- **Memoria**: 4MB Flash y ~500KB RAM (PSRAM opcional en versiones avanzadas).
- **Flexibilidad**: puede funcionar de manera independiente o como periférico de otro microcontrolador.

### Sistemas operativos y lenguajes
Compatible con múltiples frameworks y lenguajes:
- Arduino (C/C++)
- MicroPython (Python)
- Mongoose OS (JavaScript/C)
- Espruino (JavaScript)
- SDK especializados: ESP-IDF, audio ADF, ESP-Mesh, ESP-Matter

### Aplicaciones
1. **IoT**: sensores, dispositivos domésticos inteligentes.
2. **Domótica**: luces, termostatos y electrodomésticos controlables vía Wi-Fi/Bluetooth.
3. **Robótica**: control inalámbrico de robots.
4. **Dispositivos portátiles**: relojes, rastreadores de actividad, monitores de salud.
5. **Automatización industrial**: monitorización y control remoto de procesos.
6. **Monitoreo ambiental**: calidad del aire, clima y contaminación.
7. **Seguridad y salud**: sistemas de alarma, cámaras, telemedicina.
8. **Educación y prototipos**: enseñanza de electrónica y programación.

---
## Ventajas del ESP32
- Bajo costo y alto rendimiento.
- Consumo energético optimizado.
- Amplia compatibilidad con SDK y lenguajes de programación.
- Ideal para proyectos que requieren conectividad y procesamiento en tiempo real.


### Actividad sugerida
- **Demostración**: Encender un LED con un sensor en Arduino o ESP32.
- **Simulación**: Usar Tinkercad Circuits para mostrar un circuito con sensor y LED.


---

## V. Caso práctico

*(Desarrollar contenido aquí)*  

---

## VI. Áreas laborales

## Firmware Developer
- **Qué hace:**  
  Desarrolla software cercano al hardware de dispositivos electrónicos, optimizando la comunicación entre microcontroladores, sensores y actuadores. Crea drivers, protocolos de comunicación y algoritmos de control, asegurando eficiencia, estabilidad y bajo consumo energético en sistemas embebidos.

- **Ejemplo de empresas:**  
  - Empresas como Avient o KLA Tencor contratan ingenieros para trabajar en controladores y microprocesadores industriales.
  - **Avient:** empresa de materiales avanzados y soluciones tecnológicas.  
  - **KLA Tencor:** compañía especializada en control de calidad y automatización para semiconductores.

---

## IoT Developer
- **Qué hace:**  
  Diseña soluciones que integran dispositivos conectados a internet, permitiendo automatización, monitoreo y análisis de datos en tiempo real. Implementa protocolos como MQTT, HTTP y WebSocket, y asegura la conectividad y seguridad de los dispositivos en la nube.

- **Ejemplo de empresas:**  
  - Rootstack y Intel Costa Rica desarrollan proyectos IoT para smart cities, monitoreo ambiental y hogares inteligentes.
  - **Rootstack:** empresa de desarrollo de software y soluciones IoT.  
  - **Intel Costa Rica:** desarrollo de tecnología y soluciones de conectividad para IoT.

---

## Ingeniero embebido
- **Qué hace:**  
  Diseña y programa sistemas con recursos limitados como microcontroladores y FPGA. Optimiza memoria, procesador y energía, desarrollando aplicaciones en robótica, control industrial, electrónica de consumo y dispositivos médicos.

- **Ejemplo de empresas:** 
  - Fiserv y HP Costa Rica aplican sistemas embebidos en equipos de impresión y terminales de pago.
  - **Fiserv:** soluciones tecnológicas financieras y sistemas embebidos.  
  - **HP Costa Rica:** desarrollo de hardware y software integrado para dispositivos electrónicos.

---

## Sectores con creciente demanda
- **Qué se hace:**  
  Integración de sensores y actuadores, automatización de procesos, análisis de datos, desarrollo de productos inteligentes y monitoreo remoto de sistemas.

- **Ejemplo de empresas por sector:**  
  - **Automotriz:**  
    - BMW Group Costa Rica y Continental Automotive implementan soluciones embebidas para control de vehículos.
    - **BMW Group Costa Rica:** fabricación y pruebas de componentes automotrices.  
    - **Continental Automotive:** tecnología y electrónica para vehículos.  

  - **Salud:**  
    - Hospitales y startups tecnológicas desarrollan dispositivos médicos conectados.
    - **InnovaTec:** soluciones médicas y tecnología para hospitales.  
    - **Hospital Clínica Bíblica:** equipos médicos conectados y sistemas inteligentes.  

  - **Domótica:**  
    - **Smart Home Costa Rica:** automatización residencial y comercial.  
    - **Tecnosoluciones CR:** integración de dispositivos inteligentes en hogares y oficinas.  

  - **Industria 4.0:**  
    - Boston Scientific y Abbott aplican sistemas embebidos en maquinaria y monitoreo de procesos.
    - **Boston Scientific:** dispositivos médicos con control embebido.  
    - **Abbott:** automatización y monitoreo de procesos industriales.
 

---

## VII. Conclusiones
*(Desarrollar contenido aquí)*  

---

## VIII. Bibliografía en formato IEEE


