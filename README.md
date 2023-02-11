# ph-sensor-code-in-arduino
#This code is for the ph sensor 


const int pH_sensor_pin = A0; // analog pin for pH sensor

void setup() {
  Serial.begin(921600); // start serial communication
}

void loop() {
  int sensor_value = analogRead(pH_sensor_pin); // read analog value from pH sensor
  float voltage = sensor_value * 5.0 / 1024.0; // convert analog reading to voltage
  float pH = 3.5 * voltage; // convert voltage to pH
  
  Serial.println("pH: " + String(pH)); // print pH value to serial monitor
  delay(5000); // wait 5 second before next reading
}


