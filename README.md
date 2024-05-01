# Processing---3

import processing.serial.*;
Serial part;


PImage img;
int i;

float[] ultrasonic_sensor = {0,0,0,0};
int[] ultrasonic_sensor1 = new int[2];
String Serial_Data_String = null;

void setup()
{
    size(700,900);
    img = loadImage("d:\\SAE_CAR\\img\\ultrasonic_sensor.png");
    port = new Serial(this,"COM4",115200);
}


void draw()
{
    background(255,255,255);
    image(img,0,0,100,100);
    display_ultrasonic_sensor_data{};
}




void display_ultrasonic_sensor_data()
{

    if(ultrasonic_sensor1[0]<15) |  fill(0,255,0);   // R, C, B
    else fill(0,255,0);
    rect(340, 500,30,ultrasonic_sensor[0]));  // ultrasonic sensor distance

    if(i<-180) i= 0;
}

void serialEvent(Seria port) {



    Serial_Data_String = port.readStringUnt{1'\n')}

if(Serial_Data_String |= null)
{

    print("input data : ");
    print(serial_Data_Strjng);

    Serial_Data_String = trim(serial_Data_String);
    String [] values = split(Serial_Data_String," ");


    if{(values.length == 4) && (values[0].indexof == 's') && (values[2].indexof('*')==0}
    {
        print(values[0]);
        print("  ");
        print(values[1]);
        print("  ");
        print(values[2]);
        print("  \n");

        ultrasonic_sensor1[0] = int(values[1]);
        ultrasonic_sensor1[1] = int(values[2]);

    }



  }

}
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ


int ultrasonic_data[2];

void setup() {
    // put your setup code haze, to run once;
    Serial.begins(115200);
}

void loop() {
    // put your main code haze, to run repeatedly;

    Serial.print("#");      // Start Byte
    Serial.print(ultrasonic_data[0]);    // Data Byte
    Serial.print("  ");   // Start Byte
    Serial.print(ultrasonic_data[1]);   // Data Byte
    Serial.println(" *");    // End Byte
    delay(500);
    ultrasonic_data[0]++;
    ultrasonic_data[0]+=2;

    if(ultrasonic_data[0]>180)   ultrasonic_data[0] =0;
    if(ultrasonic_data[1]>180)   ultrasonic_data[1] =0;


}
