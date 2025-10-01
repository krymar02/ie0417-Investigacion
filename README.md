# Curso: Diseño de Software para Ingeniería  
## Tema: Ingeniería de Software para Sistemas Embebidos e IoT  
### Grupo 6  

---

## Estudiantes
- María José Guevara Matarrita C13476 
- Daylan Pereira Arroyo
- Kryssia Martínez Martínez B84636

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
- Los lenguajes de programación proporcionan instrucciones al microprocesador, lo que permite que el dispositivo realice operaciones. El compilador actúa como puente entre las instrucciones y el microcontrolador que las ejecuta. La selección de un lenguaje de programación apropiado es fundamental para dar forma a las capacidades y funcionalidades del producto final en sistemas embebidos.

## Lenguajes comunes en sistemas embebidos
- C
- C++
- Assembly
- BASIC
- Java
- JavaScript.

- **C**:  
  - Lenguaje compilado utilizado para crear aplicaciones de bajo nivel para microcontroladores.
  - Se utiliza ampliamente en aplicaciones industriales. 
  - Requiere que los desarrolladores tengan un alto nivel de conocimiento de técnicas de codificación complejas. 
  - Su dominio en el campo se atribuye a su eficiencia y al control que ofrece sobre los recursos del sistema.

- **C++**:
    - Lenguaje eficiente con una rica biblioteca estándar. 
    - Una ventaja de este lenguaje es su capacidad para simplificar el proceso de codificación.
    - Permite una codificación rápida y sencilla. Sin embargo, puede -Se destaca por sus características orientadas a objetos, lo que permite un desarrollo de código más complejo y modular.

- **Python**:  
  - Se utiliza ampliamente en automatización.
  - Incluye el aprendizaje automático, la inteligencia artificial (IA) y el análisis de datos debido a su versatilidad. 
  - Es de código abierto y gratuito.
  - Es fácil de aprender y utilizar. 
  - Permite un rendimiento fluido incluso con recursos informáticos limitados. 
   - Facilidad de uso de Python y sus amplias bibliotecas lo convierten en una opción cada vez más popular para sistemas embebidos, especialmente en creación de prototipos y aplicaciones de IoT.
  
  - Desventajas:
    - Velocidad lenta de ejecución y sus restricciones de diseño.

## Como elegir el lenguaje adecuado
 - La elección del lenguaje de programación integrado depende de la familiaridad del programador con el lenguaje, el tipo de proyecto y la industria involucrada, así como los requisitos. Los sistemas embebidos requieren un enfoque estratégico, que equilibre los requisitos del sistema con las capacidades y limitaciones del lenguaje de programación.

### Plataformas
- **Arduino**:  
  Fácil de usar en educación y prototipado. Gran comunidad y librerías.  
- **Raspberry Pi**:  
  Mini-computadora versátil que ejecuta Linux, ideal para proyectos más complejos.  
- **ESP32**:  
  Microcontrolador potente con Wi-Fi y Bluetooth integrados, económico y ampliamente usado en IoT.  

### Actividad sugerida
- **Demostración**: encender un LED con un sensor en Arduino o ESP32.  
- **Simulación**: usar Tinkercad Circuits para mostrar un circuito con sensor y LED.  

---

## V. Caso práctico

*(Desarrollar contenido aquí)*  

---

## VI. Áreas laborales

*(Desarrollar contenido aquí)*  

---

## VII. Conclusiones
*(Desarrollar contenido aquí)*  

---

## VIII. Bibliografía en formato IEEE


