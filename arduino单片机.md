# arduino单片机

## 1.LED闪烁

![image-20230908103605587](C:\Users\29853\AppData\Roaming\Typora\typora-user-images\image-20230908103605587.png)

```c
int led = 13;//led引脚定义到13

void setup() {
  // put your setup code here, to run once:
  pinMode(led,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(led,HIGH);//led引脚置为高电平
  delay(1000);//延时1秒
  digitalWrite(led,LOW);//led引脚置为低电平
  delay(1000);//延时1秒
}
```

## 2.LED流水灯

![image-20230908105609674](C:\Users\29853\AppData\Roaming\Typora\typora-user-images\image-20230908105609674.png)

```c
int ledBase = 13;//led引脚定义到13
int num = 6;

void setup() {
  // put your setup code here, to run once:
  for(int i = 0;i < num;++i){
    pinMode(ledBase-i,OUTPUT);
  }
}

void loop() {
  // put your main code here, to run repeatedly:
  for(int i = 0;i < num;++i){
    digitalWrite(ledBase-i,HIGH);
    delay(1000);
  }
  for(int i = 0;i < num;++i){
    digitalWrite(ledBase-i,LOW);
    delay(1000);
  }
}
```

## 3.交通灯

![image-20230915104306392](C:\Users\29853\AppData\Roaming\Typora\typora-user-images\image-20230915104306392.png)

```c
int green = 13;//绿灯引脚定义到13
int yellow = 12;//黄灯引脚定义到13
int red = 11;//红灯引脚定义到13

void setup() {
  // put your setup code here, to run once:
  pinMode(green,OUTPUT);
  pinMode(yellow,OUTPUT);
  pinMode(red,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(green,HIGH);//绿灯亮，红灯灭
  digitalWrite(red,LOW);
  delay(1000);
  digitalWrite(yellow,HIGH);//黄灯亮，绿灯灭
  digitalWrite(green,LOW);
  delay(1000);
  digitalWrite(red,HIGH);//红灯亮，黄灯灭
  digitalWrite(yellow,LOW);
  delay(1000);
}
```

## 4.温控

![image-20231011184856724](D:\Resources\Typora\assets\image-20231011184856724.png)

```c++
int potPin = 14;//接口A0连接LM35

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);//设置波特率
  pinMode(13,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(11,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  int val;
  int dat;

  val = analogRead(potPin);//读取传感器的模拟值并赋值val
  dat = (125*val)>>8;//温度计算公式
  Serial.print("Tep:");//输出显示字符串
  Serial.print(dat);//输出dat
  Serial.println("C");//输出并换行
  delay(500);//延时0.5s

  if(dat <= 31){
    digitalWrite(13,HIGH);
    digitalWrite(12,LOW);
    digitalWrite(11,LOW);
  }else if(dat >=32 && dat <= 40){
    digitalWrite(13,LOW);
    digitalWrite(12,HIGH);
    digitalWrite(11,LOW);
  }else{
    digitalWrite(13,LOW);
    digitalWrite(12,LOW);
    digitalWrite(11,HIGH);
  }
}
```

## 5.光敏

![image-20231011185120322](D:\Resources\Typora\assets\image-20231011185120322.png)

```c++
int PotPin = 14;//定义接口A0 连接光敏电阻
int LedPin = 11;//定义LED接口，PWM调节亮度
int val = 0;//定义变量

void setup() {
  // put your setup code here, to run once:
  pinMode(LedPin,OUTPUT);//LED接口为输出
  Serial.begin(9600);//设置波特率
}

void loop() {
  // put your main code here, to run repeatedly:
  val = analogRead(PotPin);//读取值并返回
  Serial.println(val);//输出val
  analogWrite(LedPin,val);//打开LED并设置亮度
  delay(10);//延时
}

```

## 6.继电器

![image-20231020103357172](D:\Resources\Typora\assets\image-20231020103357172.png)

```c++
int ledPin = 8;

void setup() {
  // put your setup code here, to run once:
  pinMode(ledPin,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(ledPin,HIGH);
  delay(1000);
  digitalWrite(ledPin,LOW);
  delay(1000);
}

```

## 7.光敏加继电器

![image-20231020110210216](D:\Resources\Typora\assets\image-20231020110210216.png)

```c++
int LedPin = 8; // LED串口8
int Light = 14; // 光敏电阻串口A0
int val; // 获取变量

void setup() {
  // put your setup code here, to run once:
  pinMode(LedPin,OUTPUT);//LED串口为输出模式
  Serial.begin(9600);//设置波特率
}

void loop() {
  // put your main code here, to run repeatedly:
  val = analogRead(Light);//读取值并返回
  Serial.println(val);//输出val
  if(val > 500)digitalWrite(LedPin,HIGH);
  else digitalWrite(LedPin,LOW);
  delay(100);//延时
}

```



## 8.LCD1602

![image-20231124103820535](D:\Resources\Typora\assets\image-20231124103820535.png)

```c++
int DI = 12;
int RW = 11;
int DB[] = { 3, 4, 5, 6, 7, 8, 9, 10 };  //使用数组来定义总线需要的管脚
int Enable = 2;
void LcdCommandWrite(int value) {
  // 定义所有引脚
  int i = 0;
  for (i = DB[0]; i <= DI; i++)  //总线赋值
  {
    digitalWrite(i, value & 01);  //因为1602液晶信号识别是D7-D0(不是D0-D7)，这里是用来反转信号。
    value >>= 1;
  }
  digitalWrite(Enable, LOW);
  delayMicroseconds(1);
  digitalWrite(Enable, HIGH);
  delayMicroseconds(1);  // 延时1ms
  digitalWrite(Enable, LOW);
  delayMicroseconds(1);  // 延时1ms
}

void LcdDataWrite(int value) {
  // 定义所有引脚
  int i = 0;
  digitalWrite(DI, HIGH);
  digitalWrite(RW, LOW);
  for (i = DB[0]; i <= DB[7]; i++) {
    digitalWrite(i, value & 01);
    value >>= 1;
  }
  digitalWrite(Enable, LOW);
  delayMicroseconds(1);
  digitalWrite(Enable, HIGH);
  delayMicroseconds(1);
  digitalWrite(Enable, LOW);
  delayMicroseconds(1);  // 延时1ms
}

void setup(void) {
  int i = 0;
  for (i = Enable; i <= DI; i++) {
    pinMode(i, OUTPUT);
  }
  delay(100);
  // 短暂的停顿后初始化LCD
  // 用于LCD控制需要
  LcdCommandWrite(0x38);  // 设置为8-bit接口，2行显示，5x7文字大小
  delay(64);
  LcdCommandWrite(0x38);  // 设置为8-bit接口，2行显示，5x7文字大小
  delay(50);
  LcdCommandWrite(0x38);  // 设置为8-bit接口，2行显示，5x7文字大小
  delay(20);
  LcdCommandWrite(0x06);  // 输入方式设定
  // 自动增量，没有显示移位
  delay(20);
  LcdCommandWrite(0x0E);  // 显示设置
  // 开启显示屏，光标显示，无闪烁
  delay(20);
  LcdCommandWrite(0x01);  // 屏幕清空，光标位置归零
  delay(100);
  LcdCommandWrite(0x80);  // 显示设置
  // 开启显示屏，光标显示，无闪烁
  delay(20);
}

void loop(void) {
  LcdCommandWrite(0x01);  // 屏幕清空，光标位置归零
  delay(10);
  LcdCommandWrite(0x80 + 3);
  delay(10);
  // 写入欢迎信息
  LcdDataWrite('W');
  LcdDataWrite('e');
  LcdDataWrite('l');
  LcdDataWrite('c');
  LcdDataWrite('o');
  LcdDataWrite('m');
  LcdDataWrite('e');
  LcdDataWrite(' ');
  LcdDataWrite('t');
  LcdDataWrite('o');
  delay(10);
  LcdCommandWrite(0xc0 + 1);  // 定义光标位置为第二行第二个位置
  delay(10);
  LcdDataWrite('Y');
  LcdDataWrite('i');
  LcdDataWrite('x');
  LcdDataWrite('f');
  LcdDataWrite('o');
  LcdDataWrite('n');
  LcdDataWrite('g');
  LcdDataWrite('-');
  LcdDataWrite('a');
  LcdDataWrite('r');
  LcdDataWrite('d');
  LcdDataWrite('u');
  LcdDataWrite('i');
  LcdDataWrite('n');
  LcdDataWrite('o');
  delay(5000);
  LcdCommandWrite(0x01);  // 屏幕清空，光标位置归零
  delay(10);
  LcdDataWrite('Q');
  LcdDataWrite('Q');
  LcdDataWrite(':');
  LcdDataWrite('1');
  LcdDataWrite('6');
  LcdDataWrite('5');
  LcdDataWrite('6');
  LcdDataWrite('3');
  LcdDataWrite('8');
  LcdDataWrite('3');
  LcdDataWrite('9');
  LcdDataWrite('0');
  LcdDataWrite('4');
  delay(3000);
}

```



## 光控声音（蜂鸣器）

```c++
```

