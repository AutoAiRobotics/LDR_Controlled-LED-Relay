# LDR_Controlled-LED-Relay
This code uses a Light-Dependent-Resistor to turn on or off a LED and/or relay based on the light intensity/brightness value given by the LDR



/* LDR Relay Demo
  Uses LDR to trigger relay module in low light
  Relay module is active LOW
*/
 
//Integers for LDR input pin and value
//Don't forget 10K resistor between A0 and GND
int ldrPin = A0;
int ldrValue = 0;
 
// Integer for Relay module output pin
int relayOut = 8U;
 
// Integer for threshold point (change as required)
int thresholdPoint = 700;
 
void setup() {
 
  // Setup relay pin as output
  pinMode(relayOut, OUTPUT);
 
  // Setup serial monitor begin
  Serial.begin(9600);
 
}
 
void loop() {
 
  // Read sensor value
  ldrValue = analogRead(ldrPin);
 
  // Print value to serial monitor
  Serial.println(ldrValue);
 
  // See if value is below threshold
  if (ldrValue < 700) {
    // Turn module on (active LOW)
    digitalWrite(relayOut, HIGH);
  } else {
    // Turn module off (active LOW)
    digitalWrite(relayOut, LOW);
  }
 
  // Short delay
 
 delay(300);// Originally 100
 
}
