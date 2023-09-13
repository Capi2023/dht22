# DHT22
## Por Emiliano García Cordero

# Objectivo
### El principal objectivo de esta pagina es dar a conocer el sensor DHT22, cuales son sus principales funciones y como esta puede ser implementada en nuestra carrera
# Marco teorico
### Nombres
* Sensor de Humedad y Temperatura DHT22
* AM2302

![Esoyam](https://github.com/Capi2023/dht22/blob/main/imagenes/modulo-dht22.jpg)

#### El sensor DHT22 es un dispositivo utilizado para medir la temperatura y la humedad relativa del aire. Es ampliamente utilizado en proyectos de electrónica y automatización, así como en aplicaciones de monitoreo ambiental y meteorología amateur.

![](https://github.com/Capi2023/dht22/blob/main/imagenes/soil_sampling.png)

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

![](https://github.com/Capi2023/dht22/blob/main/imagenes/invernadero1.jpg)

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

### Aqui tambien


![](https://github.com/Capi2023/dht22/blob/main/imagenes/AmongUsTV.webp)
