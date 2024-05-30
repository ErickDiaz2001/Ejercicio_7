INTRODUCCIÓN

El presente informe describe un sistema de control de velocidad para un motor DC,
el cual permite ajustar la velocidad del motor de manera precisa y remota desde una computadora personal (PC).
El sistema se basa en el uso de un microcontrolador y técnicas de modulación por ancho de pulso (PWM) para regular la potencia suministrada al motor.
La comunicación entre el PC y el microcontrolador se realiza mediante una interfaz serial, permitiendo el control remoto del motor desde una interfaz gráfica sencilla.

CONFIGURACIÓN 

La señal PWM para controlar los motores, para este caso un motor brushless, deberá ser de frecuencia constante y de ancho de pulso variable en función de la velocidad de giro que queramos obtener. Controlar un motor sin escobillas es tan simple como controlar un servo. Los ESC usan el mismo tipo de señal de control que el servo y esa es la señal PWM estándar de 50 Hz.

El system clock del microcontrolador se configuro a 72Mhz.
Se utilizará el timer 1, se configuro el APB2 a 9MHz, un prescaler a 180-1 y el counter period de 1000 para obtener una frecuencia de 50Hz. Para la comunicación se utilizó el USART3, con interrupción para la recepción de datos. 

![image](https://github.com/ErickDiaz2001/Ejercicio_7/assets/169405943/c2081e0d-42d4-4820-bd19-7cdd54c1726e)

![image](https://github.com/ErickDiaz2001/Ejercicio_7/assets/169405943/8f0dcbc8-d0fa-4fe6-8ced-4e510cde7530)

COMPONENTES DEL SISTEMA

El sistema se compone de los siguientes elementos:

•	MICROCONTROLADOR: Un microcontrolador, es el cerebro del sistema. Se encarga de generar la señal PWM para controlar la velocidad del motor, así como de recibir y procesar los comandos enviados desde el PC.

•	INTERFAZ SERIAL: Una interfaz serial, como USB o RS232, se utiliza para la comunicación entre el PC y el microcontrolador.

•	SOFTWARE DE CONTROL: Un software de control, instalado en el PC, permite enviar comandos al microcontrolador para ajustar la velocidad del motor.

FUNCIONAMIENTO DEL SISTEMA

El microcontrolador genera una señal PWM con una frecuencia fija y un ciclo de trabajo variable. 
El ciclo de trabajo determina la cantidad de tiempo que el motor permanece encendido durante un período determinado. 
Cuanto mayor sea el ciclo de trabajo, mayor será la potencia suministrada al motor y, en consecuencia, mayor será su velocidad.
El software de control en el PC se conecta al microcontrolador a través de la interfaz serial.
El usuario puede ingresar valores de velocidad deseados en el software, los cuales se envían al microcontrolador. 
Para cambiar los valores recibidos de 0 – 100 a 0 – 1000 correspondiste al tiempo en estado alto, se utilizará la función map para convertir números de un rango a otro
y guardarlos en el registro CCR1 y ajusta el ciclo de trabajo de la señal PWM en consecuencia, controlando así la velocidad del motor.

ANÁLISIS DE RESULTADOS 

![image](https://github.com/ErickDiaz2001/Ejercicio_7/assets/169405943/6e5dc245-b0b1-4cc3-8d8a-2acb349dde05)

https://youtu.be/N4J-vz5Ius4

CONCLUSIÓN

El controlador de velocidad para motor DC con control desde PC es una herramienta versátil y útil para controlar la velocidad de motores DC de manera precisa y remota. 
El sistema es fácil de implementar, económico y tiene una amplia gama de aplicaciones.
