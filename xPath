# xPath - Funções Principais 

### Básico

//*[@id= 'Leilão'] 

//*[@class = 'Leilão'] 

//span[contains(text(),'Leilão')] 

#### Pesquisa o texto no nome das classes

//*[contains(@class,'Leilão')]

#### Retorna o irmão

//span[contains(text(),'Leilão')]/following-sibling::text()

//span[contains(text(),'Leilão')]/preceding-sibling::spam[3]

### Texto

substring-after(//*[@id= 'Leilão'], 'R$')

substring-before(//*[@id= 'Leilão'], 'R$')

substring-before(substring-after(//*[@id= 'Leilão'], 'R$'), 'R$')

normalize-space(//*[@id= 'Leilão'])

### Outros

Pai: /*[@id= 'Leilão']/.. 

Filho direto: //*[@id= 'Leilão']/div 

Filho: /*[@id= 'Leilão']//div 

Vetor: //*[@id= 'Leilão'][2] 

Atributo: //*[@id= 'Leilão']/@src

Retorna o 3º Elemento span encontrado dentro de uma class chamada Leilão: (//*[@class = 'Leilão'] //span)[3]

Retorna os spans que estão em 3º lugar dentro das class que se chamam Leilão: //*[@class = 'Leilão'] //span[3]

//*[@id= 'Leilão'][2]/..//img/@src

//*[@id= 'Leilão'][2]/..//img/span[contains(text(),'Leilão')]

# Introdução xPath

# Funções Básicas 

### Link

https://www.portalzuk.com.br/imovel/sp/sao-paulo/bras/avenida-alcantara-machado-2978/26961-172938

### Teste dos comandos no console do navegador

`$x("comando XPath")`

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a9e8fbd8-7c10-47be-bccf-c0687a789c76)


## Capturando o texto uma classe

`<h1 class="title">Apartamento à venda em leilão</h1>`

//h1[@class = 'title'] 

//*[@class = 'title']

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b52d1965-6fe5-45e9-8a0a-0a3bbef280de)

#### A captura de um elemento deve começar com `//TAG`, o que pode ser substituído por `//*` em locais que possuem outras referências únicas


## Capturando o texto um ID

`<span id="maior-lance-vlr">0,00</span>`

//span[@id = 'maior-lance-vlr']

//*[@id = 'maior-lance-vlr']

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e3698f3a-da4c-457f-9945-f37c840699cc)


## Capturando um Atributo de Filhos
```html
<figure class="box-action-bank">
<a href="https://www.portalzuk.com.br/leilao-de-imoveis/v/leilao-judicial-sao-paulo-tjsp"> 
<img src="https://imagens.portalzuk.com.br/comitentes/76cf0a7ec37e4a04ec2a614a453fa4a4.webp" alt="Tribunal de Justiça do Estado de São Paulo">
</a>
</figure>
```
//figure[@class="box-action-bank"]/a/@href

//*[@class="box-action-bank"]//@href

//*[@class="box-action-bank"]/a/img/@src

//figure[@class="box-action-bank"]//img/@src

//figure[@class="box-action-bank"]//@alt

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/dfebce97-14c6-473a-8191-f39cf7aca9a0)

#### Chamamos de seletor Tag, ID, Class, etc

#### Seletor A / seletor B` retorna o Seletor B que é filho direto do Seletor A

#### Seletor A // seletor B` retorna o Seletor B que é filho do Seletor A, não importando se é direto.

#### href, alt, src são atributos e quando precisamos obter seus valores devemos utilizar `@nome_do_atributo`  


## Vetores
### Exemplo 01
``` html
<div class="property-documents-items">

<a class="property-documents-item" href="https://documentacaoleilao.portalzuk.com.br/2023/05/14f3d4f29ca2b539d929a71a4ea46fd2.pdf" target="_blank">
<span class="property-documents-item-icon"></span>
<span class="property-documents-item-label">Edital de venda</span>
</a>

<a class="property-documents-item" href="https://documentacao.portalzuk.com.br/I27830lote001divida_ativa.pdf" target="_blank">
<span class="property-documents-item-icon"></span>
<span class="property-documents-item-label">Dívida Ativa</span>
</a>

<a class="property-documents-item" href="https://documentacao.portalzuk.com.br/I27830lote001matricula2.pdf" target="_blank">
<span class="property-documents-item-icon"></span>
<span class="property-documents-item-label">Matricula do Imóvel</span>
</a>

</div>
```

//div[@class="property-documents-items"]/a[position()=2]/@href

//div[@class="property-documents-items"]/*[@class="property-documents-item"][2]/@href

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a39f8471-1aa8-4d1b-9968-cde96a49eb8a)

### Exemplo 02

``` html
<ul class="card-action-items">
          <li class="card-action-item">
            <div class="card-action-item-type-bid">
                    Lance mínimo:
            </div>
        </li>
        <li class="card-action-item">
            <div class="card-action-item-content">
                <span class="card-action-item-text ">1º Leilão</span>
                <span class="card-action-item-date">
                    <s>
                        15/06/23 às 10h40
                    </s>
                </span>
            </div>
                <span class="card-action-item-value">R$ <s>418.190,84</s></span>
        </li>
        <li class="card-action-item">
            <div class="card-action-item-content">
                <span class="card-action-item-text">2º Leilão</span>
                <span class="card-action-item-date">07/07/23 às 10h40</span>
            </div>
              <span class="card-action-item-value">R$ 250.914,51</span>
        </li>
</ul>
```
//*[@class = 'card-action-items']//span[1]
#### Retorna todos os spans que estão em 1º lugar dentro de seus Tags

//*[@class = 'card-action-items']//span[2]
#### Retorna todos os spans que estão em 2º lugar dentro de seus Tags

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/1ff22466-4613-41d2-8d7a-a957f09eb4e2)

#### A solução para capturar o elemento pela ordem é colocar toda a expressão entre parênteses () e sua posição no vetor [n]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/bfac9b85-829d-40b4-aa50-190281920fc3)

#### Ou especificar o caminho

//*[@class = 'card-action-items']//li[1]

//*[@class = 'card-action-items']//li[2]

//*[@class = 'card-action-items']//li[3]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/1a4fb671-024d-4cf2-bd99-e98d9811d24d)

//*[@class = 'card-action-items']//li[2]//span[1]

//*[@class = 'card-action-items']//li[2]//span[2]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/6d86234c-0c4f-4f67-9596-bf992737bad4)

#### Quando queremos capturar um elemento dentro de um vetor, ou seja, quando existem vários elementos com o mesmo seletor e queremos uma posição específica devemos utilizar `[position()=n]` ou apenas [n] onde o n é a posição desejada

## Funções de Pesquisa

``` html
<ul class="card-action-items">
          <li class="card-action-item">
            <div class="card-action-item-type-bid">
                              Lance mínimo:
                          </div>
          </li>
          <li class="card-action-item">
              <div class="card-action-item-content">
                    <span class="card-action-item-text ">1º Leilão</span>
                    <span class="card-action-item-date">
                              <s>
                                        15/06/23 às 10h40
                              </s>
                    </span>
              </div>
              <span class="card-action-item-value">R$ <s>418.190,84</s></span>
          </li>
          <li class="card-action-item">
              <div class="card-action-item-content"><span class="card-action-item-text">2º
              Leilão</span><span class="card-action-item-date">07/07/23 às 10h40</span></div>
              <span class="card-action-item-value">R$ 250.914,51</span>
          </li>
                    
</ul>
```

//div[contains(text(),'Lance mínimo:')]

//*[contains(text(),"Lance m")] * Por hora temos que utlizar Lance m, por hora não estão funcionando todos os caracteres

//ul[.//div[contains(text(),'Lance m')]]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/39086913-362a-4d65-b61d-6e1479fa9c57)

//span[contains(text(),'Leil')]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/40e9a4de-7658-4746-8325-51f841803a38)

#### Utilizar parenteses () e a posição no vetor [n]

(//div[contains(text(),'Lance mínimo:')])[2]

#### Ou especificar o caminho

//ul[@class = 'card-action-items']//span[contains(text(),'Leil')]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/8155d12b-e6db-4004-9106-39b7781d50b4)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a317c7d5-c53d-4c67-9cc1-541ccf2ced37)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/8122c760-1cfe-452f-b554-b3b492ab5c35)

#PEsquisa nos atributos, ou parcial no nome da classe...

### Funções de pesquisas diferentes

//*[contains(@class, 'valor'): Seleciona o texto contido dentro de elementos que possuem a classe contendo o valor especificado.
![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b672acfe-cca2-45ab-856b-03dac5a8ee8d)

//img[contains(@src, 'webp')], captura todos os atributos "src" que contenham o formato de arquivo "webp" 
![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/5aa9a1d4-c44c-4096-893f-95af55a556bd)

## Funções de Deslocamento

### O operador /.. é usado para navegar para o elemento pai direto. Portanto, essa expressão XPath selecionará o elemento div pai do div que contém o texto "1º Leilão:".

//s[contains(text(),'15/06/23')]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/23b1a4ae-0449-4086-8fd3-5cbcd19d9ae7)

//s[contains(text(),'15/06/23')]/..

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/615f3026-23cc-4c20-9a97-b31d6241d1f0)

//s[contains(text(),'15/06/23')]/../..

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/03239972-5e7f-401b-860b-4cbb8c3b5cc7)

//s[contains(text(),'15/06/23')]/../../..

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/4d97f362-6ee7-42a8-9afe-69062855ad38)

#### Outro exemplo

//li[@class = 'card-action-item']//span[contains(text(),'Leil')]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/2533f379-f2a4-4e82-840a-4488670f79e4)

#### Será considerado apenas o primeiro

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/ab07ed57-f2db-4215-8c6a-3e4e5676b279)

#### Para capturar o segundo elemento devemos utilizar a expressão entre parenteses e o número que desejamos do vetor.

(//li[@class='card-action-item']//span[contains(text(),'Leil')])[2]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/2d3af111-f7de-4293-92ab-60cf25788894)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b49c9885-36fa-4575-b861-bafaa28ea3ae)


### Following-sibling e Preceding-sibling

#### Essa expressão retorna todos os irmãos a frente ou atrás

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/7994644b-e71d-460b-8c3e-0bd26ba6b723)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/ff8380fe-7045-4d81-ae36-860b053d4c49)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/2a35f994-43db-43b8-9ad3-ca65ebf5cd0e)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a4bc4036-df6d-44b4-9fb6-98e5d7dab8a7)

#### Grande utilidade para a função Following-sibling

``` html
<div class="mb-3 p-2 border rounded text-justify">
   
<div>
        Lance Inicial: R$ 7.084.704,92 (valor mínimo para a melhor proposta + 5% de comissão)<br>
        Entrada 25% + 30 parcelas  
    </div>

    <br><b>Processo:</b> 65910820184013807
      
    <br><b>Vara:</b> SUBSEÇÃO JUDICIÁRIA DE MONTES CLAROS/MG
    
    <br><b>Comarca:</b> MONTES CLAROS/MG
  
    <div><b>Comissão:</b> 5%</div>
 
</div>
```

Neste exemplo a melhor maneira de capturar o número do processo é com o uso do Following-sibling.

//*[contains(text(),'Processo:')]/following-sibling::text()[1]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/acd64045-22ab-4d6d-8eda-2026e292ab9e)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/d96bd7cc-8f73-49f8-bf84-ebf2d5625aea)


## Funções de Texto

`<span class="card-action-item-date">07/07/23 às 10h40</span>`

Ao capturar //*[@Class='card-action-item-date'] teríamos o resultado 07/07/23 às 10h40 porém quero apenas a data sem o horário

Para isso podemos utilizar

substring-before(//*[@Class='card-action-item-date'], ' às')

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/0cb97745-9cce-4a4d-aa78-b7622fb3ac26)

Se quisermos somente o horário

substring-after(//*[@Class='card-action-item-date'], 's ')

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/f0e2d906-d833-4b75-83f3-250864a44359)

Se eu quiser apenas a hora

"substring-before(substring-after(//*[@Class='card-action-item-date'], 's'), 'h')

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e7f43a34-dead-4196-b39c-6b89cfce6913)


normalize-space(string)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/114b4480-9e5f-45fe-a89a-3a57315bf0dc)

## Outras Funções

https://www.macoratti.net/vb_xpath.htm

#### Outras Funções de String

translate(string, caracteres-de, caracteres-para): Substitui caracteres na string especificada com base em uma tabela de tradução.

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/cb6b1005-3f0c-4a1b-a76f-21cfdc8a22c8)

substring(string, início, comprimento): Retorna uma parte da string especificada com base no ponto de partida e no comprimento especificados.

string-length(string): Retorna o comprimento da string especificada.

lower-case(string): Converte a string especificada para letras minúsculas.

upper-case(string): Converte a string especificada para letras maiúsculas.

concat(string1, string2, ..., stringN): Concatena as strings especificadas em uma única string.

starts-with(string, prefixo): Verifica se a string especificada começa com o prefixo especificado. Retorna true ou false.

ends-with(string, sufixo): Verifica se a string especificada termina com o sufixo especificado. Retorna true ou false.

contains(string, substring): Verifica se a substring especificada está presente na string especificada. Retorna true ou false.

#### Outras Funções Gerais

//tag[last()]: Seleciona o último elemento da tag especificada.

//tag1[@attr1='valor1' and @attr2='valor2']: Seleciona elementos com a tag1 que possuem os atributos e valores especificados.

//tag1 | //tag2: Seleciona elementos da tag1 e da tag2.

//tag[position()<n]: Seleciona os elementos da tag especificada que estão em uma posição inferior a n.

//tag[position()>n]: Seleciona os elementos da tag especificada que estão em uma posição superior a n.

//tag[last()-n]: Seleciona o n-ésimo elemento a partir do último elemento da tag especificada.

//tag[starts-with(@attr, 'valor')]: Seleciona elementos com o atributo especificado que começa com o valor fornecido.

//tag[ends-with(@attr, 'valor')]: Seleciona elementos com o atributo especificado que termina com o valor fornecido.

//tag[not(@attr)]: Seleciona elementos da tag especificada que não possuem o atributo especificado.

//tag[@attr='valor1' or @attr='valor2']: Seleciona elementos com a tag especificada que possuem o atributo com um dos valores especificados.

//tag[@attr1='valor1' and not(@attr2)]: Seleciona elementos com a tag especificada que possuem o atributo1 com o valor1 e não possuem o atributo2.

//tag[position() mod n = 0]: Seleciona elementos da tag especificada em posições múltiplas de n.

# Resumo

/: Indica um descendente direto

//: Indica um direto

@: Indica um atributo, classe, Id...

*: Pode ser utilizado para representar qualquer TAG

[ ]: Deve ser utilizado para inserir funções

//TAG: Captura um TAG

//tag/text(): Retorna o texto contido dentro dos elementos com a tag especificada.

//*[@class = 'escrever a class']: Retorna a classe

//*[@id = 'escrever o id']: Retorna o ID

//TAG/@ATRIBUTO: Retorna o atributo dentro do TAG

//TAG/A/@ATRIBUTO: Retorna o atributo dentro do TAG A que é filho direto do TAG

(//TAG//A)[N]: Retorna o Enésimo TAG A filho direto ou não do TAG

//TAG//A [N]: Retorna um vetor com todos os TAGs A na posição N filhos do TAG (Raro utilizar)

//TAG[contains(text(),'TEXTO DESEJADO')]: Retorna o TAG QUE contém o TEXTO DESEJADO

//s[contains(text(),'15/06/23')]

(//div[contains(text(),'Lance mínimo:')])[2]: Retorna o segundo texto Lance mínimo contido dentro de um tag div

//*[contains(@class, 'valor'): Seleciona o texto contido dentro de elementos que possuem a classe contendo o valor especificado.

//img[contains(@src, 'webp')]: captura todos os atributos "src" que contenham o formato de arquivo "webp"

/..: Retorna o pai do elemento

//s[contains(text(),'15/06/23')]/../../..: Retorna o bisavô do elemento

(//li[@class='card-action-item']//span[contains(text(),'Leil')])[2] Retorna o segundo elemento com o texto Lei contido dentro de um tag span que esteja abaixo de uma li com a classe card...

//*[contains(text(),'Processo:')]/following-sibling::TAG: Retorna todos os elementos TAG que estejam no mesmo nível hierárquicos dentro do TAG que contém o texto Processo 

//*[contains(text(),'Processo:')]/preceding-sibling::text()[1] : Retorna o texto diretamente anterior que esteja no mesmo nível hierárquicos dentro do TAG que contém o texto Processo

substring-before(//*[@Class='card-action-item-date'], ' às'): Retorna todo texto antes de às

substring-after(//*[@Class='card-action-item-date'], 's '): Retorna todo o texto depois de s

"substring-before(substring-after(//*[@Class='card-action-item-date'], 's'), 'h'): Retorna todo o texto depois de s e antes de h

normalize-space(string): Retira os espaços antes e depois do texto





