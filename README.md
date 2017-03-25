# FPGA-control-PID

Este proyecto trata de aprovechar las posibilidades de las FPGAs libres en el proceso de control de sistemas dinámicos.

La idea surge en este [hilo](https://groups.google.com/d/msg/fpga-wars-explorando-el-lado-libre/D1TdQdAvjIg/9_1YKhvoAQAJ) de _FPGA Wars_ creado por *José Pico* y estáis todos invitados a participar.

Se trabajará con las placas __ICEStick__ y __iceZUM Alhambra__ y el primer objetivo es conseguir implantar en Verilog un _PID digital_ que haga funciones similares de control de las que realiza un _PID Analógico_.

Se parte del trabajo de _Democrito_ (ver este [hilo](https://groups.google.com/d/msg/fpga-wars-explorando-el-lado-libre/nu64aty75MI/0wGDTYJPDQAJ) del grupo FPGA Wars) donde se consigue el control de posición de un motor DC mediante un control comparativo numérico.

Para ello seguiremos la siguiente _hoja de ruta_ que se compone de los siguientes hitos:
  
 1. Primero probar el [módulo PWM](https://github.com/FPGAwars/icestudio-examples/tree/master/icestick/PWM) de _Jesús Arroyo_. Cargar en _icestudio_ y visualizar la señal por un osciloscopio.
 2. Crear un módulo donde el PWM varie con valores digitales pasados al PWM.
 3. Pasar a este módulo PWM una serie de valores digitales que van desde 000000 a 1111111 y ver que el PWM en el osciloscopio es el correcto.
 4. Llevar esa señal PWM a un motor DC con un Mosfet de forma que veamos que podemos dar o bajar la velocidad del  motor.
 5. Utilizar un motor con sensor de _efecto Hall_ (los ventiladores de CPU actuales lo llevan) e introducir la señal por un pin de la FPGA y en ésta implementar un contador de las vueltas que da, de aquí viendo las vueltas que da por ciclo de reloj sabremos a que velocidad está girando.
 6. Una vez con la señal de realimentación de velocidad implementar una realimentación de consigna e intentar por comparación controlar la velocidad de giro (rpm).
 7. Implementar la parte proporcional (P) y del integrador (I) del PID digital y sustituir la comparación anterior para eliminar el error en la velocidad.
 8. Implementar la parte derivativa (D) y completar el PID digital.
 9. Aplicar el PID a un control de posición del motor.
 10. Duplicar el PID digital y tratar de controlar posición y velocidad.
 11. Integrar el PID digital en un bloque de código para _icestudio_ y comenzar una colección de bloques para *control automático*.
 12. Trabajar con otros bloques de control digitales (Lógica borrosa, redes neuronales...).
 13. Experimentar con otros sistemas dinámicos más complejos.
 
 Estos son los hitos de inicio, conforme se vayan completando se dejará constancia del logro en el hilo de _FPGA Wars_ para animar al resto de la resistencia.
 Los hitos no son únicos ni estáticos y quién quiera puede incluir los que considere necesario editando el fichero README.md.
 
 ¡Que el _hardware libre_ os acompañe! :)
