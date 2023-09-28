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

