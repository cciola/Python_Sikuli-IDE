# Gerador de CPF ranômico

Declare esta biblioteca no topo do script:
```
import random
```

Abaixo temos a variável numCPF que recebe a função <i>cpf_funcional()</i>:
```
numCPF = cpf_funcional()
```

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
#Variáveis
import random
numCPF = cpf_funcional()

#Função para gerar CPF válido de forma randômica
def cpf_funcional():                                                                                             
    n = [random.randrange(10) for i in xrange(9)]                                                                                            
# calcula digito 1 e acrescenta ao numero
    s = sum(x * y for x, y in zip(n, range(10, 1, -1)))
    d1 = 11 - s % 11
    if d1 >= 10:
        d1 = 0
    n.append(d1)                                                                                                
# calcula digito 2 e acrescenta ao numero
    s = sum(x * y for x, y in zip(n, range(11, 1, -1)))
    d2 = 11 - s % 11
    if d2 >= 10:
        d2 = 0
    n.append(d2)                                                                                         
    return "%d%d%d%d%d%d%d%d%d%d%d" % tuple(n)

wait(2)
popup('Script de teste finalizado com sucesso! CPF gerado: ' + numCPF)
print ('CPF gerado: ' + numCPF)
wait(1)
exit()
```

Costumo declarar o trecho de código abaixo (que imprime o texto desejado no log do Sikuli) logo após a variável que receberá o CPF gerado, pois caso o script dê erro ao executar e não chegue a exibir o popup, é possível verificar qual CPF foi utilizado.

```
print ('CPF gerado: ' + numCPF)
```

Dúvidas me contate carol.ciola@gmail.com