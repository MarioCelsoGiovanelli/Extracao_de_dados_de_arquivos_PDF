![Badge Concluido](http://img.shields.io/static/v1?label=STATUS&message=%20CONCLUIDO&color=GREEN&style=for-the-badge)

# :robot:  Extração de dados de arquivos PDF

Uma automação que extrai dados consolidando os arquivos sem comprometer as informações.

Com este script será possível extrair dados de mais de um arquivo PDF. A automação passará para um arquivo excel os dados extraídos, fazendo o armazenamento no arquivo como um banco de dados.

Primeiro devemos fazer uma análise exploratória nos PDFs. Nesta análise, verificaremos se a estrutura deles é a mesma e se as informações contidas nos PDFs são do mesmo tipo.

:film_strip:

<img src=".\Animação2.gif" alt="Código 2 funcionando" width="600px" heidth="400px">


## :gear: Funcionalidades básicas do **openpyxl**:

Para carregando o arquivo excel, criamos uma variável que vai receber um método **openpyxl.load_workbook** com o nome do arquivo que será carregado entre (‘Nome do arquivo’):

````python
excel = openpyxl.load_workbook(‘Base de Dados Inspeções.xlsx’)
````
Ativando o sheet (aba):

````python
aba = excel.active
````

Mostrar dados da célula **A1**:
````python
aba[‘A1’].value
````

Mostrar todos os dados da coluna **A1**:

````python
len(aba[‘A1’])
````

Mostrar dados da linha e coluna:

````python
aba.cell(row=1, column=1).value
````

Adicionar dados no arquivo excel:

````python
aba.cell(row=2, column=2).value = ‘Inspeção’
````

Após adicionar dados no arquivo, devemos salvar o arquivo para que ele receba esses dados.

````python
excel.save(‘Base de Dados Inspeções.xlsx’)
````

## :gear: Funcionalidades básicas do **pdfplumber**:

Para ler um arquivo PDF, criamos uma variável que receba o método ** pdfplumber.open ** e entre **( )** passamos o caminho do arquivo.

````python
pdf = pdfplumber.open(‘pdfs\Relatório de Inspeção Empresa A.pdf’)
````

Para acessar os dados do PDF, criamos uma variável que vai receber o arquivo que foi aberto, passando a receber o método ** pdf.pages**. Usamos o **[ ]** para indicar como parâmetro a página da qual queremos extrair os dados.

````python
pagina = pdf.pages[0]
````

Com o método **extract_table()** retorna uma lista com os dados do PDF e armazenamos em uma variável.

````python
dados = pagina.extratc_table()
````

Verificar o tamanho da lista com **len(dados)**

````python
len(dados)
````

O módulo **os** fornece diversas funções e métodos para interagir com o Sistema Operacional.
Ele é usado para manipular arquivos e pastas.
Como ele é nativo do Python não é necessário instalar, é só importar

````python
import os
````

## 📁 Como utilizar o código:
O arquivo **script.py** pode ser usado em um terminal
````python
python script.py
````

:movie_camera:

<img src=".\Animação1.gif" alt="Código funcionando" width="600px" heidth="400px">



## :bookmark_tabs: Arquivo Requirements:
É um arquivo de texto formato **.txt**. Neste arquivo está especificado todos os pacotes e bibliotecas que são utilizados no projeto; isso ajuda como garantia que, se o projeto for usado por outro desenvolvedor, não ocorram erros ou problemas causados por alguma atualização na versão do pacote ou descontinuidade na linguagem Python.

Para instalar, entre no terminal **Ctrl + ‘** e instale o requirements para usar todos os pacotes na mesma versão que foi utilizada no projeto. 

````python
pip install -r requirements.txt
````

:film_projector:

<img src=".\Animação03.gif" alt="Código 2 funcionando" width="600px" heidth="400px">




## :computer: Técnicas e Tecnologias utilizadas:

- Método **os**
- Tratamento de erros
-  Estrutura condicional if  
    
    - **Python**
   - **Jupter Notebook**

## :books: Bibliotecas usadas:

- pdfplumber
- os
- openpyxl
  - já vem instalada no Anaconda

## :electric_plug: Como instalar:

- Pip install openpyxl
- Pip install pdfplumber
- import os
