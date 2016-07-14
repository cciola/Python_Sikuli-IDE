# Gerador de CPF randômico

Declare esta biblioteca no topo do script:
```
import random
```
<br></br>
Abaixo temos a variável <i>numCPF</i> que recebe a função <i>cpf_funcional()</i> (lembrando que deve ser declarada <b>APÓS</b> a função):
```
numCPF = cpf_funcional()
```
<br></br>
Esta é a função que calcula e gera o CPF válido de forma randômica, ou seja, CPFs diferentes a cada vez que a função <i>cpf_funcional()</i> for declarada.
```
def cpf_funcional():                                                                                             
    n = [random.randrange(10) for i in xrange(9)]                                                                                            
#calcula digito 1 e acrescenta ao numero
    s = sum(x * y for x, y in zip(n, range(10, 1, -1)))
    d1 = 11 - s % 11
    if d1 >= 10:
        d1 = 0
    n.append(d1)                                                                                                
#calcula digito 2 e acrescenta ao numero
    s = sum(x * y for x, y in zip(n, range(11, 1, -1)))
    d2 = 11 - s % 11
    if d2 >= 10:
        d2 = 0
    n.append(d2)                                                                                         
    return "%d%d%d%d%d%d%d%d%d%d%d" % tuple(n)
```

# Veja o script funcionando

Copie e cole o script abaixo no Sikuli e execute. O resultado será a exibição de um popup contendo o CPF gerado.

```
#Biblioteca
import random

#Função para gerar CPF válido de forma randômica
def cpf_funcional():                                                                                             
    n = [random.randrange(10) for i in xrange(9)]                                                                                            
#Calcula dígito 1 e acrescenta ao número
    s = sum(x * y for x, y in zip(n, range(10, 1, -1)))
    d1 = 11 - s % 11
    if d1 >= 10:
        d1 = 0
    n.append(d1)                                                                                                
#Calcula dígito 2 e acrescenta ao número
    s = sum(x * y for x, y in zip(n, range(11, 1, -1)))
    d2 = 11 - s % 11
    if d2 >= 10:
        d2 = 0
    n.append(d2)                                                                                         
    return "%d%d%d%d%d%d%d%d%d%d%d" % tuple(n)

numCPF = cpf_funcional()

wait(2)
popup('Script de teste finalizado com sucesso! CPF gerado: ' + numCPF)
print ('CPF gerado: ' + numCPF)
wait(1)
exit()
```
<br></br>
Costumo declarar o trecho de código abaixo (que imprime o texto desejado no log do Sikuli) logo após a variável que receberá o CPF gerado, pois caso o script dê erro ao executar e não chegue a exibir o popup, é possível verificar qual CPF foi utilizado.

```
print ('CPF gerado: ' + numCPF)
```
<br></br><br></br>
Dúvidas me contate! carol.ciola@gmail.com
