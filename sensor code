# Sustainability-Wellness

#include <SoftwareSerial.h>
#include "Timer.h"
#include <PulseSensorPlayground.h>     
Timer t;
PulseSensorPlayground pulseSensor;
SoftwareSerial esp8266(10,11);   
#define USE_ARDUINO_INTERRUPTS true           
#define DEBUG true
#define SSID "*********"      
#define PASS "**********" 
#define IP "184.106.153.149"    
String msg = "GET /update?key=Your Api Key"; 
void setup()
{
  Serial.begin(9600);
  esp8266.begin(115200);
    pulseSensor.analogInput(PulseWire);   
  pulseSensor.blinkOnPulse(LED13);       
  pulseSensor.setThreshold(Threshold);   
   if (pulseSensor.begin()) {
    Serial.println("We created a pulseSensor Object !");  
  }
  Serial.println("AT");
  esp8266.println("AT");
  delay(3000);

  if(esp8266.find("OK"))
  {
    connectWiFi();
  }
  t.every(10000, getReadings);
   t.every(10000, updateInfo);
}
