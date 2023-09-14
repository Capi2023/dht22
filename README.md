# DHT22
## Por Emiliano García Cordero - 20211779

# Objectivo
### El principal objectivo de esta pagina es dar a conocer el sensor DHT22, cuales son sus principales funciones y como esta puede ser implementada en nuestra carrera
# Marco teorico
### Nombres
* Sensor de Humedad y Temperatura DHT22
* AM2302

![](https://aelectronics.com.mx/2172-large_default/modulo-dht22.jpg)

#### El sensor DHT22 es un dispositivo utilizado para medir la temperatura y la humedad relativa del aire. Es ampliamente utilizado en proyectos de electrónica y automatización, así como en aplicaciones de monitoreo ambiental y meteorología amateur.

![](https://static4.arrow.com/-/media/arrow/images/820-x-410/0/0118-rp3-vs-arduino_main.jpg?mw=734&hash=6C0F11BCA1132689B72D1C7B3D8A724F)

### Caracteristicas
* Bajo consumo de energía
* Comunicación de datos mediante un solo cable de señal
* Fácil de usar y compatible con una amplia variedad de placas de desarrollo y microcontroladores
* Proporciona valores de temperatura y humedad en un solo paquete

### Aplicaciones comunes:
* Monitoreo del clima en estaciones meteorológicas caseras
* Control de ambiente en sistemas de automatización del hogar
* Monitoreo de condiciones ambientales en invernaderos
* Control de climatización en sistemas de HVAC
* Monitorización de la calidad del aire interior
* Aplicaciones de domótica y proyectos de Internet de las Cosas

![](https://nutricontrol.com/wp-content/uploads/2016/08/invernadero1.jpg)

# Ficha tecnica
* Rango de medición de temperatura: -40°C a 80°C
* Precisión de la temperatura: ±0.5°C
* Rango de medición de humedad: 0% a 100% HR
* Precisión de la humedad: ±2% HR
* Resolución de temperatura: 0.1°C
* Resolución de humedad: 0.1% HR
* Tensión de alimentación: 3.3V a 5V DC
* Corriente en funcionamiento: <1mA
* Salida de datos: Digital (Arduino, Raspberry PI, etc...)
* Tiempo de respuesta típico: 2 segundos

![](https://static.wixstatic.com/media/819900_0b88d24cc9a6431581efe8f9e98c2741~mv2.png/v1/fill/w_925,h_460,al_c,q_90,usm_0.66_1.00_0.01,enc_auto/819900_0b88d24cc9a6431581efe8f9e98c2741~mv2.png)

# Codigo
### El siguente codigo es para una lectura simple de humedad y temperatura en Celsius y Fahrenheit en arduino:

```c++
#include "DHT.h"
#define DHTPIN 2
#define DHTTYPE DHT22
DHT dht(DHTPIN, DHTTYPE);
void setup() {
  Serial.begin(9600);
  Serial.println("Iniciando...");
  dht.begin();
}
void loop() {
  delay(2000);
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  float f = dht.readTemperature(true);
  Serial.print("Humedad ");
  Serial.print(h);
  Serial.print(" %t");
  Serial.print("Temperatura: ");
  Serial.print(t);
  Serial.print(" *C ");
  Serial.print(f);
  Serial.println(" *F");
}
```
### Diagrama de como conectar el DHT22 a un arduino
![](https://naylampmechatronics.com/img/cms/Blog/Tutorial%20DHT11%20y%20DHT22/conexion%20arduino%20y%20dht22.jpg)

### Bibliografia
* https://naylampmechatronics.com/blog/40_tutorial-sensor-de-temperatura-y-humedad-dht11-y-dht22.html
* https://www.hwlibre.com/dht22/
* https://naylampmechatronics.com/sensores-temperatura-y-humedad/58-sensor-de-temperatura-y-humedad-relativa-dht22-am2302.html

![](https://media.es.wired.com/photos/649c7320532fc59e0e8d4fea/16:9/w_1920,c_limit/AmongUsTV.jpg)
