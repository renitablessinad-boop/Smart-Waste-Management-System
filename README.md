// Smart Garbage Management System - Pixel Pioneers [cite: 6]
#include <CurieWiFi.h> // Arduino 101 WiFi Shield kaga 

// Pin Definitions
const int irSensorPin = A0; // IR sensor connected to Analog pin A0 
const int thresholdLevel = 200; // Bin full aagiruchunu kandupidika oru limit

void setup() {
  Serial.begin(9600); // PC la data pakkurathuku 
  pinMode(irSensorPin, INPUT); // IR sensor data-vai edukka 
  
  Serial.println("System Starting...");
  Serial.println("Google Developer Group On Campus - TechSprint"); [cite: 1, 3]
}

void loop() {
  // IR Sensor reading edukka 
  int sensorValue = analogRead(irSensorPin); 
  
  // Trash accumulates aagum pothu distance kuraiyum 
  Serial.print("Current Garbage Level Value: ");
  Serial.println(sensorValue);

  // Check if dustbin is full [cite: 65]
  if (sensorValue > thresholdLevel) {
    // YES - Send message to control room [cite: 74, 75]
    Serial.println("STATUS: DUSTBIN FULL!");
    Serial.println("Action: Sending message to control room..."); [cite: 76]
    Serial.println("Action: Requesting cleaning vehicle..."); [cite: 77]
  } else {
    // NO - Dustbin is not full yet [cite: 66]
    Serial.println("STATUS: Dustbin space available.");
  }

  delay(2000); // 2 seconds gap la check pannum [cite: 122]
}
