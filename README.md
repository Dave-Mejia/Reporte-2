# Reporte-2 David Mejía
Programación de un ESP32 con un sensor de temperatura DHT11
## Introducción
## Descripción
Utilizaremos l plataforma WOKWI para simular la adquisición de datos de temperatura y humedad del ambiente mediante un sensor DTH11 y la porgramación del mismo en un microcontrolador ESP32

## Material Necesario
Para realizar esta practica necesitas lo siguiente

Plataforma WOKWI
Tarjeta ESP 32
Sensor de temperatura y húmedad modelo DHT11

## Instrucciones
1. Abrir la plataforma WOKWI.
2. Ir a la pestaña de sketch.ino y borrar el codigo e programación predeterminado
3. Abrir la terminal de programación y colocar la siguente programación:

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

4. Ir a la pestaña "Library manager" haer clic sobre el icon "+", buscar la libreria "DHT sensor library for ESPx" y agregarla
5. Ir al esquema de simulacón, dar clic al icono "+ (add new part)", buscar el sesnor DTH11 y agregar
6. Colocar el sensor sobre el esquema de simulación y 

