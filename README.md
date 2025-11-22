# Reporte-2 David Mejía
Programación de un ESP32 con un sensor de temperatura DHT22
## Introducción
## Descripción
Utilizaremos l plataforma WOKWI para simular la adquisición de datos de temperatura y humedad del ambiente mediante un sensor DTH22 y la porgramación del mismo en un microcontrolador ESP32

## Material Necesario
Para realizar esta practica necesitas lo siguiente

a. Plataforma WOKWI

b. Tarjeta ESP 32

c. Sensor de temperatura y húmedad modelo DHT22

## Instrucciones
PREVIO
1. Abrir la plataforma WOKWI.

PREPARACION

3. Ir a la pestaña de sketch.ino y borrar el codigo e programación predeterminado
   
4. Abrir la terminal de programación y colocar la siguente programación:

```
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
```
5. Ir a la pestaña "Library manager" haer clic sobre el icon "+", buscar la libreria "DHT sensor library for ESPx" y agregarla
![](https://github.com/Dave-Mejia/Reporte-2/blob/main/Libreria%20DHT.png?raw=true).

6. Ir al esquema de simulacón, dar clic al icono "+ (add new part)"
   
![](https://github.com/Dave-Mejia/Reporte-2/blob/main/Add%20new%20part.png?raw=true)


8. Buscar el sensor DTH11 y agregar
   
![](https://github.com/Dave-Mejia/Reporte-2/blob/main/Add%20new%20part%202.png?raw=true)

10. Conectar el sensor DTH11 en la tarjeta ESP32 como indica la figura de abajo
    
![](https://github.com/Dave-Mejia/Reporte-2/blob/main/Tarjeta%20ESP32%20con%20sensor%20DTH11.png?raw=true)

OPERACION
9. Iniciar simulador dando clic en el icono "start simulation"![](https://github.com/Dave-Mejia/Reporte-2/blob/main/play.png?raw=true)
10. Visualizar los datos en el monitor serial.
11. Colocar la temperatura y humedad dando doble click al sensor DHT11

## Resultados
Cuando haya funcionado, verás los valores dentro del monitor serial como se muestra en la siguente imagen.
![](https://github.com/Dave-Mejia/Reporte-2/blob/main/Simulacion%20de%20Tarjeta%20ESP%2032%20con%20sensor%20DTH11.png?raw=true)

## Créditos
Ralizado por el Ingeniero David Mejía

