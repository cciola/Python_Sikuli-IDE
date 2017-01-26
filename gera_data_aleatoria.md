# Gerador de data aleatória

Declare estas bibliotecas no topo do script:
```
import datetime
import random
```
<br>
Esta é a declaração do intervalo de anos, meses e dias que serão utilizados na <i>datetime.date</i> para gerar datas de forma randômica, ou seja, datas diferentes a cada vez que a variável <i>dtNascto</i> que recebeu a função for declarada.
```
year = random.randint(1950, 2016)
month = random.randint(1, 12)
day = random.randint(1, 28)
```
<br>
Abaixo temos a variável <i>dtNascto</i> que recebe a função que implementa a data no formato <i>aaaa mm dd</i> (não se preocupe, converteremos para <i>dd/mm/aaaa</i> logo mais!):
```
dtNascto = datetime.date(year,month,day)
```
<br>
Não podem faltar as variáveis, que vamos declarar informando o intervalo dos anos, os 12 meses e um calendário de 1 a 28 dias (considerando o menor dia do mês 01 e o maior dia do menor mês, fevereiro). Isto foi feito para que não seja gerada uma data inválida como 31/02/2011, por exemplo.
```
year = random.randint(1950, 2016)
month = random.randint(1, 12)
day = random.randint(1, 28)
data = datetime.date(year,month,day)
```
<br>
Logo depois é necessário converter a data do formato data para string, e aqui também é estipulado o formato da data com as barras:
```
dtNascto = data.strftime('%d/%m/%Y')
```
<br>
# Veja o script funcionando

Copie e cole o script abaixo no Sikuli e execute. O resultado será a exibição de um popup contendo o CPF gerado.
```
import datetime
import random

#Função para gerar data válida de forma randômica
year = random.randint(1950, 2016)
month = random.randint(1, 12)
day = random.randint(1, 28)
data = datetime.date(year,month,day)
dtNascto = data.strftime('%d/%m/%Y')

wait(2)
popup('Script de teste finalizado com sucesso! \nData gerada: %s' %dtNascto, 'Alerta do Sikuli')
print ('Data de nascimento gerada: %s' %dtNascto)

wait(1)
exit()
```
<br>
Costumo declarar o trecho de código abaixo (que imprime o texto desejado no log do Sikuli) logo após a variável que receberá a data gerada, pois caso o script dê erro ao executar e não chegue a exibir o popup, é possível verificar qual data foi utilizada.
```
print ('Data de nascimento gerada: %s' %dtNascto)
```
<br></br>
Dúvidas me contate! carol.ciola@gmail.com
