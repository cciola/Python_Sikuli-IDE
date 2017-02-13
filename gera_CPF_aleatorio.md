# Gerador de CPF aleatório

Declare esta biblioteca no topo do script:
```python
import random
```
<br>
Esta é a função que calcula e gera o CPF válido de forma randômica, ou seja, CPFs diferentes a cada vez que a função <i>cpf_funcional_func()</i> for declarada.
```python
def cpf_funcional_func():                                                                                             
    n = [random.randrange(10) for i in xrange(9)]                                                                                            
#calcula o dígito 1 e acrescenta ao número
    s = sum(x * y for x, y in zip(n, range(10, 1, -1)))
    d1 = 11 - s % 11
    if d1 >= 10:
        d1 = 0
    n.append(d1)                                                                                                
#calcula o dígito 2 e acrescenta ao número
    s = sum(x * y for x, y in zip(n, range(11, 1, -1)))
    d2 = 11 - s % 11
    if d2 >= 10:
        d2 = 0
    n.append(d2)                                                                                         
    return "%d%d%d%d%d%d%d%d%d%d%d" % tuple(n)
```

# Veja o script funcionando

Copie e cole o script abaixo no Sikuli e execute. O resultado será a exibição de um popup contendo o CPF gerado.
```python
import random

#Função para gerar CPF válido de forma randômica
def cpf_funcional_func():                                                                                             
    n = [random.randrange(10) for i in xrange(9)]                                                                                            
#calcula o dígito 1 e acrescenta ao número
    s = sum(x * y for x, y in zip(n, range(10, 1, -1)))
    d1 = 11 - s % 11
    if d1 >= 10:
        d1 = 0
    n.append(d1)                                                                                                
#calcula o dígito 2 e acrescenta ao número
    s = sum(x * y for x, y in zip(n, range(11, 1, -1)))
    d2 = 11 - s % 11
    if d2 >= 10:
        d2 = 0
    n.append(d2)                                                                                         
    return "%d%d%d%d%d%d%d%d%d%d%d" % tuple(n)

cpf_funcional_func()

wait(2)
popup('Script de teste finalizado com sucesso! \nCPF gerado: %s' %cpf_funcional_func())
print ('CPF gerado: %d' %cpf_funcional_func)

wait(1)
exit()
```
<br>
Costumo declarar o trecho de código abaixo (que imprime o texto desejado no log do Sikuli) logo após a variável que receberá o CPF gerado, pois caso o script dê erro ao executar e não chegue a exibir o popup, é possível verificar qual CPF foi utilizado.
```python
print ('CPF gerado: %d' %numCPF)
```
<br></br>
Dúvidas me contate! carol.ciola@gmail.com
