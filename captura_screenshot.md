# Captura de screenshot

Declare esta biblioteca no topo do script:
```
import shutil
```
<br></br>
Abaixo temos as variáveis <i>numCPF</i>, que indica o caminho da pasta a qual os arquivos de screenshot serão armazenados (lembre-se sempre de informar duas barras invertidas "\\" no caminho), e temos a variável <i>numPrint</i>, que é um mero contador para incrementar o número da imagem a ser salva:
```
screenshotsPasta = "C:\\Users\\cciola\\Desktop\\Sikuli IDE\\Screenshots_Sikuli\\"
numPrint = 0
```
<br></br>
Esta é a função que:
- captura o screenshot shutil.move(capture(Screen())
- armazena o arquivo na pasta indicada no caminho informado anteriormente screenshotsPasta
- renomeia o arquivo conforme desejado, incrementando o valor de <i>numPrint</i> e convertendo-o para <i>string</i>, já que foi declarado como <i>int</i> na variável
- define a exrtensão do arquivo .png
```
shutil.move(capture(Screen()), screenshotsPasta + 'NomeDoArquivo_' + (str(int(numPrint))) + '.png')
```

# Veja o script funcionando

Copie e cole o script abaixo no Sikuli e execute. O resultado será a exibição de um popup informanfo o caminho no qual o arquivo com o screenshot gerado.
```
import shutil

screenshotsPasta = "C:\\Users\\cciola\\Desktop\\Sikuli IDE\\Screenshots_Sikuli\\"
numPrint = 0

shutil.move(capture(Screen()), screenshotsPasta + 'NomeDoArquivo_' + (str(int(numPrint))) + '.png')

popup('Script de teste finalizado com sucesso! Veja o print gerado no caminho ' + screenshotsPasta)
print ('Arquivo gerado: ' + numPrint)

wait(1)
exit()
```
<br></br>
Costumo declarar o trecho de código abaixo (que imprime o texto desejado no log do Sikuli) logo após a variável que efetuará o screenshot, pois caso o script dê erro ao executar e não chegue a exibir o popup, é possível verificar qual foi o último screenshot capturado.
```
print ('Arquivo gerado: ' + numPrint)
```
<br></br><br></br>
Dúvidas me contate! carol.ciola@gmail.com
