
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
