# Lista de Dart

## 1 
Faça um programa que converta uma medida de temperatura de Fahrenheit para Celsius. A partir 
da fórmula de conversão de Fahrenheit para Celsius, que é C=(F-32)*(5/9) para que você possa resolver 
o problema.
```dart
import 'dart:io';

void main() {
  print("Digite a temperatura em Fahrenheit ");
  double fahrenheit = double.parse(stdin.readLineSync()!);
  double celsius = (fahrenheit - 32) * (5 / 9);
  print("$fahrenheit Fahrenheit = $celsius Celsius");
}
```
## 2
Escreva um programa que leia a quantidade de tempo dada em horas, minutos e segundos. Após 
isso converta os valores dados pelo usuário para segundos e mostre na tela o resultado.
```dart
import 'dart:io';
void main() {
  print("Digite a hora ");
  int hora = int.parse (stdin.readLineSync()!);
  print("Digite os minutos ");
  int minutos = int.parse (stdin.readLineSync()!);
  print("Digite os segundos ");
  int segundos = int.parse (stdin.readLineSync()!);
  int soma = (hora * 3600) + (minutos * 60) + segundos ;
  print("o total de segundos é $soma");
}

```
## 3
Faça um programa que receba o custo de um espetáculo teatral e o preço do convite desse 
espetáculo. Esse programa deverá calcular e mostrar a quantidade de convites que devem ser vendidos 
para pelo menos, o custo do espetáculo seja alcançado. 
```dart
import 'dart:io';
void main() {
  print("digite o custo ");
  double custo = double.parse (stdin.readLineSync()!);
  print("digite o preço do convite ");
  double convite = double.parse (stdin.readLineSync()!);
  double conta = custo / convite;
  print("preciso vender pelo menos $conta convites");
}

```
## 4
Um funcionário recebe um salário fixo mais 12% de comissão sobre as vendas. Faça um programa 
que receba o salário fixo do funcionário e o valor de suas vendas, calcule e mostre a comissão e seu 
salário final. 
```dart
import 'dart:io';
void main() {
  print("digite o salario");
  double salario = double.parse (stdin.readLineSync()!);
 print("digite o valor das vendas");
  double vendas = double.parse (stdin.readLineSync()!); 
  double soma = salario + (vendas * 0.12);
  print("o salario final foi $soma");
}

```
## 5
Uma firma contrata um encanador a R$ 38,00 por dia. Escreva um programa que leia o número de 
dias trabalhados pelo encanador e imprima o valor da diária, o total do salário bruto, o valor do 
imposto de renda, sabendo-se que são descontados 6%, e o salário líquido, já com o imposto 
descontado. 
```dart
import 'dart:io';
void main() {
  print("digite o numero de dias de trabalho");
  double dias = double.parse (stdin.readLineSync()!);
 double diaria = 38;
 double bruto = dias * diaria;
 double imposto = bruto * 0.06;
 double liquido = bruto  - imposto;
 print("valor da diaria $diaria");
 print("O valor do salario bruto $bruto");
 print("o valor do liquido é $liquido");
print("o valor do imposto é $imposto"); 
}

```
## 6
Uma companhia telefônica opera com a seguinte tarifa: uma chamada telefônica com duração de 3 
minutos custa R$ 4,59. Cada minuto adicional custa R$ 1,30. Escreva um programa que leia a duração 
total de uma chamada em minutos, faça o cálculo e exiba total a ser pago. 
```dart
import 'dart:io';
void main() {
  print('Digite a duração da chamada em min');
  int duracao = int.parse(stdin.readLineSync()!);
  double custo = calcularCustoChamada(duracao);
  print('O total foi de  $custo');
}
double calcularCustoChamada(int duracao) {
  double precoBase = 4.59;
  double custoTotal = precoBase;
  if (duracao > 3) {
    custoTotal += (duracao - 3) * 1.30;
  }
  return custoTotal;
}

```
## 7
Uma lanchonete vende produtos como refrigerante, salgado e sorvete, onde cada um vale R$ 8,00, 
R$ 12,00 e R$9,00 respectivamente. Faça um programa em que o usuário peça a quantidade de 
produtos e exiba o quanto ele deverá pagar. 
```dart
import 'dart:io';
void main() {
double precoRefrigerante = 8.00;
double precoSalgado = 12.00;
double precoSorvete = 9.00;
stdout.write('Quantidade de refrigerantes: ');
int Refrigerante = int.parse(stdin.readLineSync()!);
stdout.write('Quantidade de salgados: ');
int Salgado = int.parse(stdin.readLineSync()!);
stdout.write('Quantidade de sorvetes: ');
int Sorvete = int.parse(stdin.readLineSync()!); 
double totalPagar = (Refrigerante * precoRefrigerante) + (Salgado * precoSalgado) +
(Sorvete * precoSorvete);
print('Total a pagar: R\$ ${totalPagar.toStringAsFixed(2)}');
}
```
## 8
Uma lanchonete vende produtos como refrigerante, salgado e sorvete, onde cada um vale R$ 8,00, 
R$ 12,00 e R$9,00 respectivamente. Faça um programa em que o usuário peça a quantidade de 
produtos desejada, e quantidade de pessoas que irão pagar o valor total, exiba o total a ser pago e o 
valor de cada pessoa. Utilize funções para resolução do problema. 
```dart
import 'dart:io';

double calcularTotal(int quantRefrigerante, int quantSalgado, int quantSorvete) {
  double precoRefri = 8.00;
  double precoSalgado = 12.00;
  double precoSorvete = 9.00;
  double total = (quantRefrigerante * precoRefri) +
      (quantSalgado * precoSalgado) +
      (quantSorvete * precoSorvete);
  return total;
}
double calcularValorPorPessoa(double total, int quantPessoas) {
  return total / quantPessoas;
}
void main() {
  stdout.write('Quantos refrigerantes deseja? ');
  int quantRefrigerante = int.parse(stdin.readLineSync()!);
  stdout.write('Quantos salgados deseja? ');
  int quantSalgado = int.parse(stdin.readLineSync()!);
  stdout.write('Quantos sorvetes deseja? ');
  int quantSorvete = int.parse(stdin.readLineSync()!);
  stdout.write('Quantas pessoas vão participar? ');
  int quantPessoas = int.parse(stdin.readLineSync()!);
  double total = calcularTotal(quantRefrigerante, quantSalgado, quantSorvete);
  double valorPorPessoa = calcularValorPorPessoa(total, quantPessoas);
  print('Total a ser pago: R\$ ${total.toStringAsFixed(2)}');
  print('Valor por pessoa: R\$ ${valorPorPessoa.toStringAsFixed(2)}');
}

```
## 9
Uma empresa de aluguel de carros precisa cobrar pelos seus serviços. O aluguel de um carro custa 
R$90 por dia para carro popular e R$150 por dia para carro de luxo. Além disso, o cliente paga por Km 
percorrido. Faça um programa que leia o tipo de carro alugado (popular ou luxo), quantos dias de 
aluguel e quantos Km foram percorridos. No final mostre o preço a ser pago de acordo com as 
descrições abaixo: 
- Carros populares (aluguel de R$90 por dia) 
● Até 100Km percorridos: R$0,20 por Km 
● Acima de 100Km percorridos: R$0,10 por Km 
- Carros de luxo (aluguel de R$150 por dia) 
● Até 200Km percorridos: R$0,30 por Km 
● Acima de 200Km percorridos: R$0,25 por Km
```dart
import 'dart:io';

void main() {
double precoPopular = 90.00;
double precoLuxo = 150.00;

stdout.write('Tipo de carro, selecione popular ou luxo: ');
String Carro = stdin.readLineSync()!.toLowerCase();

stdout.write('por quantos dias quer alugar? ');
int dias = int.parse(stdin.readLineSync()!);
stdout.write('Quantos km foram percorridos? ');
int kmPercorrido = int.parse(stdin.readLineSync()!);

double precoTotal = 0.0;

if (Carro == 'popular') {
    precoTotal += precoPopular * dias;
    if (kmPercorrido <= 100) {
      precoTotal += kmPercorrido * 0.20;
    } else {
      precoTotal += (100 * 0.20) + ((kmPercorrido - 100) * 0.10);
    }
  } else if (Carro == 'luxo') {
    precoTotal += precoLuxo * dias;
if (kmPercorrido <= 200) {
      precoTotal += kmPercorrido * 0.30;
    } else {
      precoTotal += (200 * 0.30) + ((kmPercorrido - 200) * 0.25);
    }
  }

print('O preço total é de R\$ ${precoTotal.toStringAsFixed(2)}');
}

```