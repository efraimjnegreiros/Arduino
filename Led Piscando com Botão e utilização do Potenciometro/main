//Efraim José Negreiros dos Santos

const byte led_vm = 9; //led vermelho
const byte led_az = 10; //led azul
const byte led_vd = 11; //led verde
const byte led_vmp = 12; //led vermelho pedestre
const byte led_vdp = 13; //led verde pedestre
//pullup serve para garantir que o led sem esta presionado está no nível lógico alto
const byte botao = 2; //botao no pino digital 2
const byte pot = A0; //potenciometro na porta analógica A0
int brilho = 255;

//A entrada analógica do arduino uno é 10 bits

//O setup é a definição das entradas e saídas;
//O botão reset vai voltar para as variaveis, setup e loop;
void setup() {
	pinMode(led_vm, OUTPUT);
  	pinMode(led_az, OUTPUT);
  	pinMode(led_vd, OUTPUT);
  	pinMode(led_vmp, OUTPUT);
  	pinMode(led_vdp, OUTPUT);
  	pinMode(botao, INPUT_PULLUP);
  	pinMode(pot, INPUT);
  	Serial.begin(9600);
  	pedestre(1,1);
  	carro(brilho,brilho,brilho);
  	delay(1000);
}

void pedestre(byte vm, byte vd) {
	digitalWrite(led_vmp, vm);
  	digitalWrite(led_vdp, vd);
}

void carro(byte vm, byte vd, byte az) {
	analogWrite(led_vm, vm);
  	analogWrite(led_vd, vd);
  	analogWrite(led_az, az);
}

void loop() {
    //conversao dos valores de entrada para os que o led pode receber
  	brilho = map(analogRead(pot),0,1023,0,255);
  	Serial.println(brilho);
  	delay(1000);
  	if (digitalRead(botao) == 0) {
  		pedestre(1,0); //pedestre vermelho
      	carro(brilho,brilho,0); //carro amarelo R + G
      	delay(1000);
      	pedestre(0,1);
      	carro(brilho,0,0);
      	delay(3000);
      for (byte n = 1; n < 10; n++) {
      	pedestre(n%2,0);
        delay(500);
      }
    }
      	carro(0,brilho,0);
      
    
    }
