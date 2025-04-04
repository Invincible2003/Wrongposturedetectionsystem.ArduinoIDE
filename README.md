# Wrongposturedetectionsystem.ArduinoIDE   (Project Description)
The Wrong Posture Detection System is a smart and efficient project designed to help users maintain a healthy sitting posture using Arduino Uno, a flex sensor, and a breadboard. The system is programmed in C++ using the Arduino IDE. The core component, the flex sensor, is placed on the user's back, typically integrated into a wearable belt or strapped to a chair. This sensor detects bending by varying its resistance when the user's back curves or slouches.

The flex sensor is connected to the Arduino via a breadboard, forming a voltage divider circuit. The Arduino reads the analog values from the sensor and compares them to a predefined threshold. When the user maintains a correct posture, the resistance remains within a certain range. However, when the user slouches or bends incorrectly, the resistance changes significantly, crossing the threshold value. This triggers an alert mechanism such as a buzzer or LED, notifying the user to correct their posture.

This system is simple, low-cost, and highly effective for students, professionals, or anyone who sits for extended periods. It promotes better spinal health by providing immediate feedback, encouraging the user to maintain proper posture throughout their activities.
# Wrong Posture Detection System using Arduino

A simple and effective posture monitoring system built with Arduino Uno and a flex sensor to detect poor sitting posture and provide real-time alerts.

## Features

- Detects incorrect (slouched) posture using a flex sensor
- Real-time feedback using a buzzer or LED
- Low-cost and easy to assemble
- Great for students, professionals, and office setups

## Components Used

- Arduino Uno
- Flex Sensor
- Breadboard
- Jumper Wires
- 10kΩ Resistor
- Buzzer or LED
- USB Cable
- Arduino IDE


## Working Principle

1. The flex sensor is attached to the user's back.
2. When posture is correct, the sensor remains straight and provides a stable analog value.
3. When the user slouches, the sensor bends, altering its resistance.
4. Arduino reads this change, and if it crosses a threshold, it triggers an alert (buzzer or LED).

## Arduino Code
// Constants:
const int ledPin = 13;   // LED pin
const int flexPin = A0;  // Flex sensor pin
const int flexPin1 = A1;  // Flex sensor pin
const int threshold = 130; // Set a threshold value for LED blinking
const int threshold1 = 315; // Set a threshold value for LED blinking

// Variables:
int value; // Variable to store sensor value
int value1; // Variable to store sensor value

void setup() {
  pinMode(ledPin, OUTPUT);  // Set LED pin as output
  Serial.begin(9600);       // Start serial communication
}

void loop() {
  value = analogRead(flexPin); // Read flex sensor value
  //Serial.print("Flex Sensor 1 Value: ");
  //Serial.println(value); // Print the sensor value
  value1 = analogRead(flexPin1); // Read flex sensor value
  Serial.print("Flex Sensor 2 Value: ");
  Serial.println(value1); // Print the sensor value

  if (value > threshold || value1 > threshold1) {  // If value is greater than threshold
    Serial.println("Bending detected! Blinking LED...");
    digitalWrite(ledPin, HIGH);  // Turn LED ON
    delay(200);                  // Wait
    digitalWrite(ledPin, LOW);   // Turn LED OFF
    delay(200);                  // Wait
  } else {
    Serial.println("No bending detected.");
    digitalWrite(ledPin, LOW);   // Keep LED OFF
  }

  delay(100); // Small delay before next reading
}



## Installation

1. Connect components as per the circuit diagram.
2. Open Arduino IDE.
3. Select the correct board and port.
4. Upload the code provided above.
5. Observe serial output and buzzer alert on wrong posture.

## Applications

- Office workstations
- Study desks
- Ergonomic training tools
- Smart wearables (basic prototype)

## License

This project is open-source and available under the MIT License.




 
