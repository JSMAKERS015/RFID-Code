**[  WEBSITE Opening Uising RFID ](url)**
using this code you can open any favourite website using the RFID Module.

**[Steps:](url)**

1. First you have to get your RFID Card Unique ID. The code to scan your card's unique ID is below:


`#include <SPI.h>
#include <MFRC522.h>
#define RST_PIN         9          // Configurable, see typical pin layout above
#define SS_PIN          10         // Configurable, see typical pin layout above
MFRC522 mfrc522(SS_PIN, RST_PIN);  // Create MFRC522 instance
void setup() {
Serial.begin(115200);                       // Initialize serial communications with the PC
while (!Serial);                       // Do nothing if no serial port is opened (added for Arduinos based on ATMEGA32U4)
            SPI.begin();                             // Init SPI bus
            mfrc522.PCD_Init();              // Init MFRC522
            delay(4);                                             // Optional delay. Some board do need more time after init to be ready, see Readme
            mfrc522.PCD_DumpVersionToSerial();      // Show details of PCD - MFRC522 Card Reader details
            Serial.println(F("Scan PICC to see UID, SAK, type, and data blocks..."));
}
void loop() {
            // Reset the loop if no new card present on the sensor/reader. This saves the entire process when idle.
            if ( ! mfrc522.PICC_IsNewCardPresent()) {
                        return;
            }
            // Select one of the cards
            if ( ! mfrc522.PICC_ReadCardSerial()) {
                        return;
            }
            // Dump debug info about the card; PICC_HaltA() is automatically called
            mfrc522.PICC_DumpToSerial(&(mfrc522.uid));
}`


2.  After Uploading the code open serial monitor and scan your card . Below you can find your Unique ID copy and store the id  somewhere safe.
![Capture](https://github.com/user-attachments/assets/1d88e45c-1b48-466b-960c-a3896438e54c)


3. Next, open VS Code Application to run the python code to open website using RFID.
4. Create new folder and open as Project.
5. Inside the folder create new file with .py extention.
6. Paste the code which I provided.
![2](https://github.com/user-attachments/assets/6ebd9f38-4acb-4a85-8553-4b0d7ced7280)

7.Replace the Unique ID with your card id and also replace the website like with your particular website. 

8. Before run the code you have to install some scripts:

- Install the pyserial package: Open a terminal or command prompt and run:

[pip install pyserial](URL)

- Verify the Installation: After installation, verify that the package is installed by running:

[pip show pyserial](URL)
This should display details about the installed pyserial package.

9. After installing the scrips run the program. you will get scan card message on your terminal, as shown below:
![3](https://github.com/user-attachments/assets/00c29f0b-4c6e-4c8b-80e8-1c6b021f7971)









**[Screenshots:](url)**

