
void setup() {
  // put your setup code here, to run once:
pinMode(3,OUTPUT);
pinMode(2,INPUT);
digitalWrite(3,HIGH);
}

void loop() {
  // put your main code here, to run repeatedly:
if(digitalRead(2)==0)
{
  digitalWrite(3,LOW);
}
小黑豆 按下恆亮按第二下滅
int a=1,jj=1;
void setup() {
  // put your setup code here, to run once:
pinMode(3,OUTPUT);
pinMode(2,INPUT);
digitalWrite(3,HIGH);
digitalWrite(2,HIGH);
}

void loop() {
  // put your main code here, to run repeatedly:
if(!digitalRead(2))
{
  while(digitalRead(2)==0)delay(20);
  jj=0;
}
else
{
  if(jj==0)
  {
    jj=1;
    a^=1;
  }
}
digitalWrite(3,a);

按一下由左至右 按第二下由右至左按第三下全滅
byte ledpin[8]={3,4,5,6,7,8,9,10};
int a=-1,jj=1;
void setup() 
{
  for(int i=0;i<8;i++)pinMode(ledpin[i],OUTPUT);
  for(int i=0;i<8;i++)digitalWrite(ledpin[i],1);
  pinMode(2,INPUT);
  digitalWrite(2,1);
}

void loop() 
{
  if(!digitalRead(2)) 
  {
    while(!digitalRead(2))delay(10);
    if(!jj)
    {
      a++;
      jj=1;
    }
  }
  else
  {
    jj=0;
    switch(a)
    {
      case 0:
        for(int i=0;i<8;i++)
        {
          for(int j=0;j<8;j++)digitalWrite(ledpin[j],1);
          digitalWrite(ledpin[i],0);
          delay(100);
        }
      break;
      case 1:
        for(int i=7;i>-1;i--)
        {
          for(int j=0;j<8;j++)digitalWrite(ledpin[j],1);
          digitalWrite(ledpin[i],0);
          delay(100);
        }
      break;
      case 2:
        for(int i=0;i<8;i++)digitalWrite(ledpin[i],1);
      break;
      case 3:
        a=0;
      break;
    }
  }

}
