String dataIn;
int i;
boolean parsing=false;
uint16_t hex1;
uint16_t hex2;

void setup() {
  Serial.begin(115200);
  dataIn="";
}

void loop() {
  if(Serial.available()>0){
    char x=(char)Serial.read();
    dataIn+=x;
    if(x=='\n'){
      parsing=true;
    }
  }
  if(parsing){
    parsingData();
    parsing=false;
    dataIn="";
  }
}

void parsingData(){
  for(i=0;i<dataIn.length();i++){
    if((i==0)||(i==1)){
      Serial.print("");
    }
    else if(i>=18&&i<23){     
      if(i==18){
        hex1=dataIn[i];
        hex1=(hex1<<8)+dataIn[i+1];
        Serial.print(hex1,DEC);
        Serial.print("%");
      }
      else if(i==20){
        hex2=dataIn[i];
        hex2=(hex2<<8)+dataIn[i+1];
        Serial.print(hex2,DEC);
        Serial.print("%");
      }
    }
    else if(i>1&&i<18){
      Serial.print(dataIn[i]);
    }
  }
  Serial.print("\n");
}
