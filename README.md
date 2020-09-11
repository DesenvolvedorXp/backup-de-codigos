# backup-de-codigos
comprimentoPista = float(input('Comprimento da pista(m): ')) / 1000 # vai receber o comprimento da pista em (m), e converter para Km

numVoltas = int(input('Número de Voltas: '))

numReabastecimento = int(input('Número de reabastecimentos: ')) + 1

consumoCombustivel = float(input('Comsumo do combustivel(Km/L): '))

if comprimentoPista <= 0 or consumoCombustivel <= 0:
    print('O comprimento da pista ou o consumo km/L estão invalidos.')
else:
    kmTotal = comprimentoPista * numVoltas # comprimento total da pista

    litrosTotal = kmTotal / consumoCombustivel # valor em litros, para o gasto total de gasolina para toda a corrida.

    litrosMininos = litrosTotal / numReabastecimento # vai calcular os litros 'minimos' até o primeiro reabastecimento

    print('''
    Para percorrer {}Km, parando para reabastecer {} vezes, será necessário {:.2f}L, até o primeiro reabastecimento
    '''.format(kmTotal, numReabastecimento-1, litrosMininos))

-------------------------------questão2------------------------------------------------------------------------------------------------
numConta = input("Informe o número da conta:")
tipo = int(input('''
[1]Residencial
[2]Comercial
[3]Industrial
Qual a sua opção (1/2/3): '''))

consumo = float(input("Informe o consumo de água em metros cúbicos"))

limiteComercial = 80
limiteIndustrial = 100

if tipo <= 0 or (tipo > 3):
    print('Consumo ou Tipo consumidor inválidos. ')

elif tipo == 2:
    if consumo <= limiteComercial:
        pagar = 500
    else:
        pagar=500 + (consumo - limiteComercial)*0.25
        
elif tipo == 3:
    if consumo <= limiteIndustrial:
        pagar=800
    else:
        pagar= 800 + (consumo - limiteIndustrial)*0.04
        
elif tipo == 1:
    pagar= 50 + consumo * 0.05
    
print('''
----------------------------------------------------------------------
 |NÚMERO DA CONTA |  Tipo de consumidor:|   CONSUMO(m3)  |  VALOR R$ |
   {}                    {}                    {}           R${}
-----------------------------------------------------------------------
'''.format(numConta, tipo, consumo, pagar))
-------------------------------------------questão3-----------------------------------------------------------------------------

lista = [] 
contador = 0

ntermos= int(input("Número de termos:"))

razao= float(input("Razão:"))

a1=int(input("Primeiro termo da serie:"))
lista.append(a1)

while contador < ntermos:
    a1= a1 + razao
    lista.append(a1)
    contador = contador + 1
    
print('Segue',ntermos,'termos da progressão da P.A:',lista)
    
    -------------------------------------------questão4------------------------------------------------------------------------
    
    c = 0 # contador do while

contador2 = 0 # contador do while do controle de login.

nome = str(input('Nome: ')).upper() #o comando upper, vai deixar todas as letras maiusculas.

senha = str(input('Senha: ')).upper()# para não ocorrer: nome = fulano e senha = Fulano

#Abaixo, será verificado se o nome e a senha são iguais, e se os campos foram preenchidos, se não forem, vai entrar no laço while
if nome == senha or nome == '' or senha == '':
    while c < 3:
        
        print('Login e senha iguais, ou os campos não foram preenchidos.')
        nome = str(input('Nome: ')).upper()
        
        senha = str(input('Senha: ')).upper()
        
        if nome == senha or nome == '' or  senha == '':
            c += 1
        # esse bloco vai analisar se o nome e senha são diferentes, se for, ele vai sair do while por causa do comando break.
        elif nome != senha :
            break
        
        else:
            c += 1
if c == 3:
    print('Infelizmente, seu acesso foi bloqueado, tente novamente daqui a 3 dias úteis.')
    
else:
    print('Cadastro concluindo com sucesso!!')
#-----------------------------------------------------------------------------------------------------------------
print('\n')
print('Login de Usúario:')
print('\n')
    
#teste de login
usuario = str(input('Usúario: ')).upper()
password = str(input('Senha: ')).upper()

if  nome != usuario and senha != password:
    while contador2 < 2:
        print('Usúario ou senha inválidos.')
        usuario = str(input('Usúario: '))
        password = str(input('Senha: '))
    
        if nome == usuario and senha == password:
            break
            
        else:
            contador2 += 1
        
if contador2 == 2:
    print('Infelizmente, seu acesso foi bloqueado, tente novamente daqui a 3 dias úteis.')
    
else:
    print('Cadastro concluindo com sucesso!!')
    

        
-------------------------------calculadora-------------------------------------------
def soma(x, y):
    return x + y

def sub(x, y):
    return x - y

def multi(x, y):
    return x * y

def divi(x, y):
    return x / y
operacao = int(input(
'''
Operações:
[1]Soma
[2]Subtração
[3]Multiplicação
[4]Divisão
Qual a sua opção(1/2/3/4): '''))

num1 = float(input('Informe o primeiro número: '))
num2 = float(input('Informe o segundo número: '))

if operacao == 1:
    print(num1,'+',num2,'=',soma(num1, num2))
    
elif operacao == 2:
    print(num1,'-',num2,'=',sub(num1, num2))
    
elif operacao == 3:
    print(num1,'*',num2,'=',multi(num1, num2))
                                  
elif operacao == 4:
    print(num1,'/',num2,'=',divi(num1, num2))
                                  
else:
    print('Operação inválida')

        
