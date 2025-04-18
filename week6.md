# Introduction to Python Programming - Part I 
versatile language 
> Python IDE : Spyder,pycharm,etc..

# Introduction to Python Programming - Part II

## File Read Write Operations

```
file=open('data.txt','r')
file.read()
file.write("writing to the file")
file.close()
```

> Using **with** to open a file:
- Good pratice to handle exception while file read/write operation 


```
with open("data.txt","w") as file:
file.write("writing to the text file")
```
>> CSV

```
reader=csv.reader(csv_file)
for row in reader:
  print("".join(row))

writer =csv.writer(csv_file,delimiter=',')
for line in data:
  writer.writerow(line)
```

## Image read/write operation
- Python support PIL library for image operation
- install PIL(Python image library) through PIP : sudo pip install pillow 
- PIL is supported till python version 2.7. Pillow supports the 3x version of python 

```
from PIL import Image
image=Image.open(image_name)
image.show()
image.resize(255,255)
image.rotate(90)
```

- Format,Size(give a tuple:width,height in pixels )
- Mode(give a band of the iamge,'L' for grey scale,'RGB' for true colour image)

```
print(image.format,image.size,image.mode)
```

> Convert image to diff mode 

```
con_image =image.convert('L')
con_image.save('greyscale.jpg')
```

## Networking in python
 
s=socket.socket(family,type,protocol=0)
- family-AF_UNIX or AF_INET
- type - SOCK_STREAM or SOCK_DGRAM
- protocol-default '0'
- neccceary imports: socket,sys 
> simple server

***bind the socket to the port***

```
server_address = ('10.14.88.82', 2017)
sock.bind(server_address)

sock.listen(1)
connection, client_address = sock.accept()
data = connection.recv(1024)
print(data)
sock.close()
```

> simple client 

```
client_socket.connect(("10.14.88.82",2017))
client_socket.send('message')
```

# Introduction to Raspberry Pi- Part I

- single board computer 
- low cost 
- easy to access 
- ex:raspberry pi 3 model B ,raspberry pi 2 model B ,raspberry pi zero 

## basic setup for raspberry PI 

- HDMI cable
- Monitor 
- key board 
- Mouse 
- 5volt power adapter for raspberry Pi
- lab cable 
- Min-2 GB micro sd card 

## raspberry Pi GPIO (General Purpose input and output )

- these pins are used to send input and output signals 
- output : turn a GPIO pin high or low
- Input : detect a GPIO pin high or low 
 
## OS for PI

- official supported : Raspbian ,NOOBS
- third party OS : Ubuntu mate,snappy ubuntu core ,windows 10 core ,pinet ,risc os 

## Raspbian OS setup 

> Write Raspbian in SD card 

- Install “Win32 Disk Imager” software in windows machine .
- Run Win32 Disk Imager
- Plug SD card into your PC
- Select the “Device”
- Browse the “Image File”(Raspbian image)
- Write


## Basic Intiial Configuration

> Enable SSH 

- Open command prompt and type sudo raspi-config and press enter.
- Navigate to SSH in the Advance
- Enable SSH

> Expand the file system 
- Open command prompt and type sudo raspi-config and press enter.
- navigate to expand filesystem 
- press enter to expand 

- Default installed lang(c,c++,python,java,scratch,ruby)
- any language that will compile for armv6 can be used with pi 
- popular app: Media streamer,Home automation,Controlling BOT,VPN,Light weight web server for IOT,Tablet computer


# Introduction to raspberry Pi - Part II

## **Blinking LED**
The LED blinks in a loop with delay
of 1 and 2 seconds.

> requirements:Pi,LED,100 ohm resistor,bread board,jumper cables 

> Installing GPIO library:

```
sudo apt-get install python-dev to install python development
sudo apt-get install python-rpi.gpio to install GPIO library.
```

> connection 

- Connect the negative terminal of the LED to the ground pin of Pi
- Connect the positive terminal of the LED to the output pin of Pi


sudo nano filename.py
Ctrl+O: Writes the code to the file
Ctrl+X: Exits the editor 

> Code:

```
import RPi.GPIO as GPIO #GPIO library
import time
GPIO.setmode(GPIO.BOARD)#set type of board for pin numbering 
GPIO.setup(11, GPIO.OUT) #Set Gpio pin 11 as output pin
for i in range (0,5):

  GPIO.output(11, True) #Turn on GPIO pin 11
  time.sleep(1)
  GPIO.output(11, False)
  time.sleep(2)
  GPIO.output(11, True)

GPIO.cleanup()
```

## capture image using raspberry PI

> requirements: PI,PI camera

> raspberry Pi camera

- pi specific camera module 
- dedicated Csi(camera serial interface ) slot in pi for connection 
- the cable slot is placed between ethernet port and HDMI port 
- Boot the pi once the camera is connnected to pi

> Configurating pi for camera

```
sudo raspi-config
```

Navigate to "Interfacing Options" option and Option press enter,
Navigate to "Camera" option,
Enable the camera,
Reboot Raspberry pi

> capture Image 

```
raspistill -o image.jpg 
```

- this will store the image as image.jpg
- picam can also be processed using python camera module python-picamera


```
Import picamera
camera = picamera.PiCamera()
camera.capture('image.jpg')
```

# Implementation of IOT with raspberry Pi:Part I

- IOT(Internet of things )
  - creating an interactive environment 
  - network of devices connected together 

- Sensor (ex:DHT sensor)
  - Electric element
  - converts physical quantity into electrical signals 
  - can be analog or digital

- Actuator (ex: Relay )
  - mechnical/electro-mechanical device 
  - converts energy into motion 
  - used to provide controlled motion to other components

## Temperature Dependent Auto Cooling System 

- DHT22 sensor 
  - Digital and humidty and Temperature sensor
  - Pin 1(power supply),2(data),3(null),4(ground)

- Relay 
  - mechnical/electro-mechanical switch 
  - 3 output terminal (normal open:NO,common,Normal close:NC)

> Relay interface with raspberry pi

- Connect pin 1 of DHT sensor to the 3.3V pin of Raspberry Pi
- Connect pin 2 of DHT sensor to any input pins of Raspberry Pi, here we have used pin 11
- Connect pin 4 of DHT sensor to the ground pin of the Raspberry Pi
- adafruit provides a library to work with DHT22 sensor 
- Install the library in your Pi:git clone https://github.com/adafruit/Adafruit_Python_DHT.g...
- cd Adafruit_Python_DHT
- Install the library : sudo python setup.py install

> Code 

```
import RPi.GPIO as GPIO
from time import sleep
import Adafruit_DHT #importing the Adafruit library
GPIO.setmode(GPIO.BOARD)
GPIO.setwarnings (False)
GPIO.setup(13,GPIO.OUT)
sensor =Adafruit_DHT.AM2302 # create an instance of the sensor type
print ('Getting data from the sensor') #humidity and temperature are 2 variables that store the values received from the sensor
humidity, temperature = Adafruit_DHT.read_retry(sensor,17)
print ('Temp={0:0.1f}*C humidity={1:0.1f}%'.format(temperature, humidity))
if temperature > 30:
  GPIO.output(13,0) # Relay is active low
  print('Relay is on')
  sleep(5)
  GPIO.output(13,1) # Relay is turned off after delay of 5 seconds
```
> connection 

Connect the Li-po battery in series with the fan
NO terminal of the relay -> positive terminal of the Fan.
Common terminal of the relay -> Positive terminal of the battery
Negative terminal of the battery -> Negative terminal of the fan.


