
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include<reg51.h> 
void main(void) 
{ 
TMOD=0X20;//TIMER 1,MODE 2 
TH1=0XFA; 
SCON=0X50; 
TR1=1; 
while(1) 
{ 
SBUF='A'; 
while(TI==0); 
TI=0; 
} 
}

```
### (ii) Serial Port to Transfer a Message

```
void main(void) 
{ 
unsigned char msg[]="Avinash"; 
unsigned char i; 
TMOD=0X20;//TIMER 1,MODE 2 
TH1=0XFA; 
SCON=0X50; 
TR1=1; 
for (i=0; i<17;i++) 
{ 
SBUF= msg[i]; 
while(TI==0); 
TI=0; 
} 
while(1); 
} 



```

### OUTPUT:
![WhatsApp Image 2025-11-11 at 21 00 35_f86eec82](https://github.com/user-attachments/assets/306a80ec-dd10-41a4-820c-f9274eb70e9c)
![WhatsApp Image 2025-11-11 at 21 03 47_a5bbfec4](https://github.com/user-attachments/assets/d22baed8-c505-470f-aef2-b67db18d2c6a)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
