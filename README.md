# busca-processos-inpi
Estudando o módulo  xml.etree.ElementTree para análise de arquivos .xml

## Sobre o arquivo .xml utilizado para este estudo:

Trata-se de versão reduzida da Revista de Propriedade Industrial - RPI número 2617 - Sessão V Marcas, publicada em 02/03/2021:
http://revistas.inpi.gov.br/txt/RM2617.zip

O arquivo original possui 394343 linhas, que foram reduzidas à 5272.
Para validar a estrutura final do .xml foi utilizado o Validador de XML (1.1) disponibilizado gratuitamente pela Aptools:
https://server01.aptools.com.br/xml/upload

## Aprendendo a extrair informações de arquivos .xml
Comece na primeira célula >>> In [1]

https://github.com/camila0909/analise-arquivos-xml/blob/main/busca-processos.ipynb

1. Conhecendo a tag do elemento raíz e seus atributos >>> In [2]

2. Conhecendo a tag do primeiro filho e seus atributos >>> In [5]

   2.1 Criando uma lista de atributos (dicionários) >>> In [7]
   
   2.2 Criando uma lista de nºs de processos >>> In [8]
   
3. Conhecendo os filhos do filho, seus atributos e seus filhos >>> In [9]

   3.1 Percorrendo cada uma das tags encontradas >>> In [11]
   
       3.1.1 Despachos
       3.1.2 Titulares
       3.1.3 Marcas
       3.1.4 Classes-Vienna
       3.1.5 Lista-Classe-Nice
       3.1.6 Procurador
       
## Busca de Processos na Revista de Propriedade Industrial - RPI
Dada uma lista com vários números de processos e preciso pesquisar manualmente um a um. O objetivo aqui é automatizar essa tarefa.

1. Criando uma lista com os nºs de processos que desejo buscar >>> In [22]

2. Importando e lendo o arquivo .xml >>> In [23]

3. Verificando se alguns dos processos da 'lista_processos' estão no arquivo >>> In [24]

   *Caso encontre, retornará o número do processo encontrado e seu respectivo titular e situação*
   
## Ilustrando a nomenclatura utilizada
  
          <revista> elemento raíz 
                   <processo>  = <filho> primeiro filho           
                            <despachos> = <filhos> filho do filho                    
                                      <despacho> neto                              
                            <titulares> = <filhos> filho do filho                    
                                      <titular> neto                             
                            <marca> = <filhos> filho do filho                   
                                      <nome> neto                              
                            <classes-vienna> = <filhos> filho do filho                    
                                      <classe-vienna> neto                              
                            <lista-classe-nice> = <filhos> filho do filho                    
                                      <classe-nice> neto                              
                            <procurador> = <filhos> filho do filho
                    
 Onde chamamos de neto, deveria ser bisneto :sweat_smile::stuck_out_tongue_winking_eye:
 
 **>>> Não utilizamos todos os elementos do arquivo, logo, a estrutura acima é meramente ilustrativa**
   
## Referência
Para aprender mais sobre o módulo xml.etree.ElementTree as et acesse:

https://docs.python.org/pt-br/3/library/xml.etree.elementtree.html
   
