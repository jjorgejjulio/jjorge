# jjorge
Calculadora de propagação de erros
print('Calculadora de propagação de erros.')
print('')
print('')
print('Para começar, Digite suas variáveis','Use a seguinte ordem', '(a+-b)',',', 'a é o valor da média e b é o valor do erro da média.')
print('')
print(' Para funcionar, sempre digite o número mais alguma casa decimal (usando ponto), exemplo:, 3.14.')
print(' Caso não seja necessário preencher alguma das variáveis preencha ela apenas com no número {1}, mesmo que não vá utilizar.')
print('')
print(' Nos casos de área ou volume envolvendo circunferências, sempre utilize o valor do raio e insira na primeiro média.')
print('')
print( 'Após isso, inserira as variáveis de acordo com a operação desejada')
print('')
print('1.0 = soma;', '   ','2.0 = subtração;','   ','3.0 = produto;','   ','4.0 = divisão;', '   ','5.0 = Quadrado',  '   ','6.0 = cubo','','7.0 = seno','',
      '8.0 = Área do quadrado','','9.0 = Área do retângulo','','10 = Área da circunferência','','11 = Área do triângulo','','12 = Volume do cilíndro','','13 = Volume da esfera','')
print('')
print('')
import math

a1 = float(input('Valor da primeira média'))
b1 = float(input('Valor do primeiro erro da média'))
a2 = float(input('Valor da segunda média'))
b2 = float(input('Valor do segundo erro da média'))

R1 =( (b1 ** 2) + (b2 ** 2) ) ** (1/2)
R2= (((b1/a1) ** 2) + ((b2/a2) ** 2)) ** (1/2)

varsoma= a1 + a2
varsub= a1-a2

varmult1= a1 * a2
varmult2= varmult1 * R2

vardiv1= a1/a2
vardiv2= vardiv1 * R2

varsq1= a1 ** 2
varsq2= 2*a1*b1

varcub1= a1 ** 3
varcub2= 3 * (a1**2) * b1

varsin1= math.sin(math.radians(a1))
varsin2= math.cos(math.radians(a1))
varsin3= varsin2 * (b1 * (math.pi/180))

varcirc1= math.pi * varsq1
varcirc2= math.pi * varsq2

vartri1= varmult1 / 2
vartri2=varmult2  / 2

varcil1= (varsq1 * a2) * math.pi
varcil2= (varsq2/varsq1) ** 2
varcil3= (b2/a2) ** 2
varcil4= (varcil2 + varcil3)**(1/2)
varcil5= (varcil4) * (varcil1)

vares1= varcub1 * 4 * (1/3) * math.pi
vares2= varcub2 * 4 * (1/3) * math.pi

cod = float(input('Insira seu código'))

if cod == 1.0:
    print('Programa para calcular a propagação de erros ( modo Soma)')
    print('Resultado do erro médio é', R1)
    print('O Resultado final é', '{',varsoma, '+-', R1, '}', )
    
elif cod == 2.0:
    print('Programa para calcular a propagação de erros(modo subtração')
    print('Resultado do erro médio é',R1)
    print('O Resultado final é',varsub,'+-',R1)
    
elif cod == 3.0:
    print('Programa para calcular a propagação de erros (modo produto)')
    print('Resultado da propagação do erro (modo produto) é',varmult2)
    print('O Resultado  final é',varmult1,'+-',varmult2)

elif cod == 4.0:
    print('Programa para calcular a propagação de erros (modo divisão)')
    print('Resultado da propagação do erro (modo divisão) é',vardiv2)
    print('O Resultado  final é',vardiv1,'+-',vardiv2)

elif cod == 5.0:
   print('Programa para calcular a propagação de erros (modo quadrado)')
   print('Resultado da propagação do erro (modo quadrado) é', varsq2)
   print('O Resultado final é',varsq1,'+-',varsq2)
   
elif cod == 6.0:
   print('Programa para calcular a propagação de erros (modo cubo)')
   print('Resultado da propagação do erro (modo cubo) é', varcub2)
   print(' O Resultado final é',varcub1,'+-',varcub2)

elif cod == 7.0:
   print('Programa para calcular a propagação de erros (modo seno)')
   print('Resultado da propagação do erro (modo seno) é', varsin3)
   print(' O Resultado final é','(',varsin1,'+-',varsin3,')')

elif cod == 8.0:
   print('Programa para calcular a propagação de erros (modo área do quadrado)')
   print('Resultado da propagação do erro (modo área do quadrado) é',varsq2 )
   print(' O Resultado final é','(',varsq1,'+-',varsq2,')')

elif cod == 9.0:
    print('Programa para calcular a propagação de erros (modo área do retângulo)')
    print('Resultado da propagação do erro (modo área do retângulo) é',varmult2)
    print('O Resultado  final é',varmult1,'+-',varmult2)

elif cod == 10:
   print('Programa para calcular a propagação de erros (modo Área da circunferência)')
   print('Resultado da propagação do erro (modo Área da circunferência) é',varcirc2 )
   print('O Resultado final é',varcirc1,'+-',varcirc2)

elif cod == 11:
    print('Programa para calcular a propagação de erros (modo Área do triângulo)')
    print('Resultado da propagação do erro (modo Área do triângulo) é',vartri2)
    print('O Resultado  final é',vartri1,'+-',vartri2)

elif cod == 12:
    print('Programa para calcular a propagação de erros(modo volume do cílindro')
    print('Resultado do erro médio é',varcil5)
    print('O Resultado final é',varcil1,'+-', varcil5)

elif cod == 13:
    print('Programa para calcular a propagação de erros(modo volume da esfera')
    print('Resultado do erro médio é',vares1)
    print('O Resultado final é',vares1,'+-', vares2)

else:
    print('Algo deu errado com os comandos inseridos, tente novamente!!!')
