# Sensores IR

<h3>¿Qué es un Sensor Infrarrojo (IR)?</h3>

Imaginen el espectro de luz que el ojo humano puede ver: desde el violeta hasta el rojo. Ahora, si siguen más allá del color rojo, hay un tipo de luz que nosotros NO podemos ver, pero que sí podemos sentir como calor. Esa es la luz infrarroja.

Un sensor infrarrojo es, entonces, un dispositivo electrónico diseñado específicamente para detectar esta luz invisible que emiten todos los cuerpos calientes (incluidos nosotros, un muro o el sol).

<img width="960" height="588" alt="image" src="https://github.com/user-attachments/assets/56111a13-6c70-457d-80fb-8c906a1168d3" />

<h3>¿Cómo Funcionan? (El Principio Físico)</h3>

La clave está en el fototransistor o fotorreceptor. La mayoría de los sensores IR que usamos tienen dos partes:

<b>· Un Emisor de IR (LED Infrarrojo):</b> Es un diodo LED normal, pero en lugar de emitir luz visible, emite luz infrarroja. Es como una linterna invisible.

<b>· Un Receptor de IR (Fototransistor):</b> Es un componente que es "ciego" a la luz visible, pero se activa o conduce electricidad cuando le llega luz infrarroja.

<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/555fb7a5-e295-43dc-9173-5b14e6914ae8" />

<h3>¿Cómo trabajan juntos? </h3>

Se usan principalmente de dos formas:
Detección por Reflexión (Tipo Pozo Óptico):
El emisor y el receptor están uno al lado del otro. El emisor lanza constantemente luz IR. Si hay un objeto delante, esta luz rebota y una parte es captada por el receptor. Cuanto más cerca está el objeto, más luz rebota y más fuerte es la señal en el receptor. Así funcionan los robots seguidores de línea o los que evitan obstáculos.

Detección por Interrupción (Tipo Barrera):
El emisor y el receptor están enfrentados. El emisor lanza luz IR continuamente hacia el receptor. Si un objeto se interpone en medio, interrumpe el haz de luz. El receptor deja de detectar IR y lo interpreta como "algo ha pasado por aquí". Así funcionan las puertas automáticas o los contadores de objetos.
<br>

<img width="649" height="345" alt="image" src="https://github.com/user-attachments/assets/961d67a0-f58a-47bb-b054-d628993c12ea" />

<h3>¿Cómo se Comunican con un Microcontrolador (como Arduino o Raspberry Pi)?</h3>

Esta es la parte práctica. La comunicación es casi siempre a través de señales analógicas o digitales.

<b>· Señal Analógica (Para medir distancia o intensidad):</b>
  El receptor de IR no da un "sí" o "no", sino un voltaje variable (por ejemplo, entre 0V y 5V). Este voltaje cambia dependiendo de la cantidad de luz IR que recibe.
  · ¿Cómo se lee? Conectamos la patita de señal del sensor a una entrada analógica (ADC) del microcontrolador (ej: pin A0 en Arduino). El microcontrolador lee ese voltaje y lo convierte en un número (ej: de 0 a 1023). Un número alto significa "objeto muy cerca", un número bajo significa "objeto lejos o no hay objeto".
  <br>
<b>· Señal Digital (Para detección de "sí/no" o "on/off"):</b>
  Algunos sensores tienen un circuito extra que "decide" por nosotros. Si la señal supera un umbral, envía un LOW (0V), y si no lo supera, envía un HIGH (5V).
  · ¿Cómo se lee? Conectamos la patita de señal a una entrada digital del microcontrolador (ej: pin 2 en Arduino). En nuestro código, solo debemos comprobar si el pin está en HIGH o LOW.

<b>Caso Especial: Comunicación de Datos (Como el Mando a Distancia)</b>
Aquí es más sofisticado.El emisor IR no se enciende de forma continua, sino que parpadea muy rápido en un patrón específico de pulsos (un código binario). El receptor especializado (como el TSOP382) decodifica ese patrón y lo convierte en una señal digital que el microcontrolador puede interpretar como "subir volumen", "cambiar canal", etc. 
<br>

<img width="800" height="267" alt="image" src="https://github.com/user-attachments/assets/1e722886-f3aa-4855-bed0-178cd91180c8" />

<h3>GP2Y0A21YK</h3>
<img width="500" height="366" alt="image" src="https://github.com/user-attachments/assets/1a16c63b-bb46-4eed-9045-a09fc7b456d3" />

<br>Usan el principio de "triangulación" para medir distancias con mucha más precisión que un módulo simple. Dan una salida analógica muy estable.

<h3>QTR</h3>
<img width="634/2" height="480/2" alt="image" src="https://github.com/user-attachments/assets/daa745cd-d01d-428f-b5c9-0b62fade7080" />
<img width="458" height="458" alt="image" src="https://github.com/user-attachments/assets/478dcdc5-31af-4ae6-8c2f-236f1047b0c0" />

<img  width="312*2" height="161*2" alt="image" src="https://github.com/user-attachments/assets/8bab99c7-e2a5-4a81-9556-c0d7e9933ecc" />

<h3>TSOP382</h3>
<img width="600" height="450" alt="image" src="https://github.com/user-attachments/assets/39b419f8-a801-4098-98fd-3b3305439035" />
<br>Un encapsulado de 3 patas que solo sirve para recibir y decodificar las señales de los mandos de TV, etc.<br>

<img style="max-width:75%" width="1685" height="825" alt="image" src="https://github.com/user-attachments/assets/e5ac3745-a23c-4198-80f7-143448d7aebf" />

<img style="max-width:60%" width="1280" height="1043" alt="image" src="https://github.com/user-attachments/assets/f4d355f8-2081-4863-b5b0-960ad98f5690" />

