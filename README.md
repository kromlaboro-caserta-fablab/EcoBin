# EcoBin
Automated garbage can with Arduino and 3D printing.

Progetto sviluppato per: <a href= "https://www.convittogiordanobruno.edu.it/">Convitto Nazionale Giordano Bruno - Maddaloni (Ce) </a>

Licenza Progetto: <a href= "https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/b58ac2ec3b1155eefaae648031c3f0876af7aa45/license%20CC-BY-SA-4.0"> <b>CC-BY-SA-4.0 Attribution-ShareAlike 4.0 International </a>





![immagine](https://github.com/user-attachments/assets/8fdb28a8-8ad6-4c4b-931d-22ca9a52df43)
![immagine](https://github.com/user-attachments/assets/de6bdf51-ef27-4ee7-b3c0-f3af4b56e369)
![immagine](https://github.com/user-attachments/assets/f89ce07a-431a-471a-944b-7f9198147d8f)

Questo è il circuito sviluppato con Thinkercad. Codice Arduino scritto con Blocchi
![immagine](https://github.com/user-attachments/assets/18dcd670-c597-4b7b-946e-4e0aafb44374)

Questo il link al progetto pubblico su Thinkercad:
https://www.tinkercad.com/things/aCw9f9vkpth-copy-of-eco-bin


CODICE a blocchi:

![immagine](https://github.com/user-attachments/assets/799ef6be-fb60-4ed8-9dff-29d24a1f7134)

Questa invece è la versione con codice Arduino scritto con Testo (Linguaggio di programmazione C++)
![immagine](https://github.com/user-attachments/assets/ef321b78-7839-41f8-8cfb-3488fb37a923)

Questo il link al file di progetto e allo schema elettrico:
https://www.tinkercad.com/things/cWEtUcsoJDk-eco-bin

#Nota
In questo circuito è presente il sensore di Distanza ad Ultrasuoni a 3PIN anzichè Il sensore ad ultrasuoni HCSR04 con 4 PIN. Il funzionamento è analogo.
![immagine](https://github.com/user-attachments/assets/1c1a7de3-b3e6-41f0-9e85-ba235ef4340b)

In questo repository è presente il file Arduino di questo progetto:
https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/f6444a3bfa870dd5421165e39c96db20ecbf079f/Codice-eco_bin1.ino

Questo il Codice:

<code> 

// C++ code
//
#include <Servo.h>

int ultras = 0;

int i = 0;

int j = 0;

long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT);  // Clear the trigger
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);
  // Sets the trigger pin to HIGH state for 10 microseconds
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT);
  // Reads the echo pin, and returns the sound wave travel time in microseconds
  return pulseIn(echoPin, HIGH);
}

Servo servo_3;

void setup()
{
  pinMode(LED_BUILTIN, OUTPUT);
  servo_3.attach(3, 500, 2500);
}

void loop()
{
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
  if (0.01723 * readUltrasonicDistance(9, 10) <= 15) {
    servo_3.write(-90);
  } else {
    servo_3.write(90);
  }
}

</code>

Componenti Stampati in 3D:

1) https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/b58ac2ec3b1155eefaae648031c3f0876af7aa45/bidone.stl

2) https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/b58ac2ec3b1155eefaae648031c3f0876af7aa45/coperchio%20arduino.stl

3) https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/b58ac2ec3b1155eefaae648031c3f0876af7aa45/coperchio%20bidone.stl

4) https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/b58ac2ec3b1155eefaae648031c3f0876af7aa45/coperchio%20ultrasuono.stl

5) https://github.com/kromlaboro-caserta-fablab/EcoBin/blob/b58ac2ec3b1155eefaae648031c3f0876af7aa45/levetta.stl







