# Diretrizes
Pirmeira diretriz: Ler do Final para o Começo
# 18/07
## Erros e testes de paginação
Após preencher todos os campos da paginação e clicar no atualizar, deve ser realizado o teste clicando no testar.

Este teste pode demorar até em torno de 1 min e chega a retornar que a página não etá funcionando. Nesse caso, não adianta clicar novamente em testar, pode ir fazer outra coisa e voltar em uns 3 min... que provavelemtne o teste deu certo.

Para o teste dar certo, temos que obter de retorno a planilha do download preenchida.

Apenas para entender, a lista de URLs que aparecem na pagina, é tudo o que foi encontrado com o tag `a`, e ai ele filtra com base no que preenchemos do que é lote e o que é leilão.

Para agilizar nosso trabalho precisamos identificar corretamente o erro da paginação, os principais observados até agora são:

1) O link na página principal está incompleto. Ex.: deveria estar www.zuk.com/leilão/001, porém está /leilão01.

Neste caso pode identificar o erro como: prefixo pendendete.

2) Caso verifique na página principal que o problema não é o relatado anteriormente, ai devemos inserir o link da paginação no campo URL Teste, com o número da página se for o caso (não o {pagina}) clicar em atualizar e ver o preview, para ver se está puxando os links corretos.
   ![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/d7498aa9-73df-453d-9f3f-63278ff8140e)

Caso os links não carreguem, ai pode colocar o erro como: Java

3) Vi um caso de redirecionamento, na página principal os links estão como .../detalhe_leilao/xxxx, e quando clica ele vai para .../detalhe_lote/xxxx

Neste caso apenas fiz o cadastro do leilão com a nomeclatura correta e do lote com a nomeclatura correta e funcionou.

Caso encontrem outros erros vamos conversar, tentar descobrir a origem e registrar aqui.

### Apenas lembrando a respeito dos outros campos.

#### Identificar os erros de visuzalição de acordo com o problema, ex.: 

Se não carrega alguns campos apenas, identificar o erro como java.

Se a tela retornou em banco, colocar tela em branco.

Se deu internal server error, clicar no atualizar e tentar novamente, caso não tenha dado certo em 2 tentativas ai anotar internal server error.

#### No seletor relatar erro apenas se for um problema exclusivo de seletor e não de visualização de página. 

# 17/07

## Complemento sobre paginação

#### No caso abaixo:

https://www.mrleiloes.com.br/lotes/1234/abcd

Onde 1234 e abcd são variáveis, devemos preencher da seguinte maneira

https://www.mrleiloes.com.br/lotes/{slug} - SIM

Podemos preencher também das maneiras abaixo. Mas vamos simplificar e usar a de cima.

https://www.mrleiloes.com.br/lotes/{slug2}/{slug1} - SIM

https://www.mrleiloes.com.br/lotes/{numeros}/{letras} - SIM

#### O que não devemos fazer: 

Não pode usar vazio {}

e não pode usar 2 {slug} {slug} na mesma url, mas da pra usar {slug1} {slug2} por exemplo

https://www.mrleiloes.com.br/lotes/{} - NAO

https://www.mrleiloes.com.br/lotes/{}/{} - NAO

https://www.mrleiloes.com.br/lotes/{slug}/{slug} - NAO

#### No caso abaixo na URL paginação, onde há alteração de páginas por um número na URL:

https://www.mrleiloes.com.br/lotes/1conteúdo#

https://www.mrleiloes.com.br/lotes/2conteúdo#

https://www.mrleiloes.com.br/lotes/3conteúdo#
 
Nesses casos deve ser usado https://www.mrleiloes.com.br/lotes/{pagina}conteúdo#

#### Caso o teste retorne erro:

- Verificar se o link do lote presente página principal está completo, caso não eteja, anotar que o erro da paginação é link incompleto
  

# 14/07

## Captura de informação de endereço a partir do iframe do maps.
Quando não tiver a informação de endereço (Lembrando que endereço deve conter além da rua o município pelo menos), podemos capturar a informação através do iframe do google maps.

Sempre que necessário usar este método, capturar o link do maps, depois trataremos ele no backend para extrair o endereço.

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/f63d2e97-533b-415a-88cc-7dd0fbfd1881)

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/a7409706-b020-4f35-b5f5-392e06b88bf7)


## Atualizada diretriz de paginação:
Devemos preencher o campo de paginação da seguinte maneira, com {pagina} substituindo o número da página. Anteriormente havia falado para colocar {n}
#### Paginação: https://agostinholeiloes.com.br/lotes/imovel?tipo=imovel&page={pagina}

## Atualizada diretriz de leileiro com conteúdo diverso:
Quando o leiloeiro não possuir lotes, ou lotes alheios (gado, livros..), vamos cadastrar o que tiver de informação.

Seja apenas o título, ou o título, da e preço... por que se algum desses leiloeiros oficiais um dia tiver um imóvel teremos essa informação.

*Não precisa fazer o que já passou, vamos adotar essa premissa daqui para frente.

# 13/07
## Leiloeiros com erro de carregamento e visualização
Vamos dar andamento nos seletores de leiloeiros com problema de visualização pegando os seletores pelo console mesmo

Preenchimento no controle:

Parâmetros - ok, Paginação - ok, Carregamento - Erro (especificar o erro, como vêm fazendo, ou colocar o ok se der certo)

## Botão testar

Ao clicar no botão testar, o "crawler" irá rodar e capturar todos os links conforme indicado na paginação. Será identificado o que é lote, o que é leilão.

Ele mostra disponibiliza no final 5 páginas cadastradas.

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/967469e1-e3e6-4a70-8627-e4421ad75615)

Ao clicar neles será exibida a página em nosso servidor. (Interessante clicar em uma para ver a exibição)

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/e0cda1ec-8850-4c10-a746-c8b8db93bc17)

Na planilha disponível no fim da página em download, podemos ver alguns links e o resultado da busca dos seletores. (Este é interessante analisar para validar o preenchimento)

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/a4efa3b4-38c6-4e34-85e1-0007cda86627)

Colocar a informação de paginação ok no controle, quando o resultado do botão testar for correto.

Usar só com o cadastro de página concluído conforme item abaixo.

## Cadastro de páginas

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/ee680ddc-db02-470a-8b67-7323ad1d604b)


### Paginação

As páginas onde estão os lotes tem a seguinte nomeclatura:

https://agostinholeiloes.com.br/lotes/imovel?tipo=imovel&page=1

https://agostinholeiloes.com.br/lotes/imovel?tipo=imovel&page=2

https://agostinholeiloes.com.br/lotes/imovel?tipo=imovel&page=3

Devemos preencher o campo de paginação da seguinte maneira, com {pagina} substituindo o número da página. 

#### Paginação: https://agostinholeiloes.com.br/lotes/imovel?tipo=imovel&page={pagina}

### Leilão x Lote

Um leilão pode ter vários lotes, um lote é um item a ser leiloado. Em muitas páginas os quadros podem representar tanto leilões quanto lotes.

### Leilão
Neste caso a página dos leilões se chama:

https://agostinholeiloes.com.br/leilao/570/lotes

Iremos inserir a informação no campo de leilão da seguinte maneira: 

https://agostinholeiloes.com.br/leilao/{slug}/lotes

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/09bc9ee9-9e37-4a03-b3a8-6781bd6a47c6)

### Lotes

Neste caso a página dos lotes se chama:

https://agostinholeiloes.com.br/item/2339/detalhes?page=1

Iremos inserir a informação no campo de leilão da seguinte maneira: 

https://agostinholeiloes.com.br/item/{slug}/detalhes?page=1

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/d99dde08-640f-467f-83ba-efe9f3760124)

### Outros Exemplos

### https://www.deonizialeiloes.com.br
#### URL Inicial: https://www.deonizialeiloes.com.br

#### Onde estão os lotes: https://www.deonizialeiloes.com.br/externo/
URL Paginação: https://www.deonizialeiloes.com.br/externo/

#### Como se chamam os leilões: https://www.deonizialeiloes.com.br/externo/lotes/39856
URL Leilão: https://www.deonizialeiloes.com.br/externo/lotes/{slug}

#### Como se chamam os lotes: https://www.deonizialeiloes.com.br/externo/lote/detalhes/2541212
URL Lote: https://www.deonizialeiloes.com.br/externo/lote/detalhes/{slug}

### https://www.hastavip.com.br/
#### URL Inicial: https://www.hastavip.com.br/
#### URL Paginação: https://www.hastavip.com.br/pesquisa?

#### Como se chamam os leilões: https://www.hastavip.com.br/leilao/3207-190720-00
URL Leilão: https://www.hastavip.com.br/leilao/{slug}

#### Como se chamam os lotes: https://www.hastavip.com.br/lote/imovel-lotes-capivari-campos-do-jordao-sao-paulo-608952
URL Lote: https://www.hastavip.com.br/lote/{slug}

Interessante procurar leilão com 2 lotes

![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/5a683114-fd12-458b-a4b6-e67049cb3a13)

### Próximos Exemplos
#### URL Inicial:
#### URL Paginação:
#### URL Leilão:
#### URL Lote: 


# 12/07
## Cadastro de leiloeiros com problema
Como muitos sites estão apresentando erros na visualização e captação, por hora podem criar um "leiloeiro teste" com o nome de vocês: A_TESTE_Seu Nome. Lá dentro não precisa necessariamente preencher tudo sempre, podem só abrir onde coloca as variáveis, inserir o link, informações se é ajax, atualizar e testar.

Para testar podem usar o ponto antes de uma classe ou # antes de um id, lembrando que só valem para quando o id ou a class não contém espaço

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/fe4b1d23-19a5-4bfd-a273-726577b1862a)

Ai podem inserir apenas no controle "- Erro site não cadastrado", assim perdemos menos tempo.


# 11/07

## Nomeclatura de leiloeiros aleatórios
<s> Quando o leiloeiro não possuir lotes, ou lotes alheios (gado, livros..): Z_SL_Nome_do Leiloeiro, ou apenas inserir no controle.
Carros e eletronicos, vamos cadastrar.
Se tiver dúvidas, pergunte
<\s>
# 10/07

## Nunca utilizar data de abertura, sempre encerramento

...Sempre encerramento

Quando o código para data de leilão único, é o mesmo da primeira praça, não precisa preencher leilão único

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/58e9dddf-f5f0-4fbe-ad0e-e174372084cd)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/5c1eca76-5f57-4f28-8f91-922f4065d53f)


## Informação de último lance
Essa informação de último lance é muito importante, podem pegar mesmo que seja um texto indicando que não houve lance.

Depois quando tivermos tudo rodando podemos achar imóveis que tiveram lances e melhorar o seletor.

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e193259c-5995-4426-a96a-232e76f020f7)

## Endereço na descrição 
Neste caso abaixo, onde o endereço não aparece em nenhum campo específico, mas está na descrição. É interessante usar o campo da descrição, ou parágrafos específicos como endereço. Normalmente o google maps retorna alguma coisa bem próxima do endereço específico. Ou trataremos no back depois.

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/24f6a049-cf4b-4c16-9021-d66bb977fe1f)

## Endereço em campos 

Neste caso abaixo se pegarmos apenas o nome da rua, o maps não irá identificar, pois esta rua existe em vários municípios, precisamos de mais informação.

O ideal seria pegar de cidade para frente. 

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/829752a0-0591-4b51-b4c4-692127bc567f)


## Data e Preço se alteram com a data do leilão
A informação que está como text passa a ser `<s>`, quando vencida a data do primeiro leilão.

Neste caso podemos pegar o pai e usar substring para pegar o que vem depois de R$

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/90a48e53-462f-44b8-9c86-b24f433c80c9)

# Anterior

## Pontos importantes para efetuar o cadastro

### Nomeclatura Painel:
Novo site: A_Seu_nome_Nome_do Leiloeiro

Quando revisado o nome será alterado para: R_Seu_nome_Nome_do Leiloeiro

Quando validado no banco de dados: Nome_do_Leiloeiro

Quando houver problemas que restrinjam o cadastro: Z_Hold_Nome_do Leiloeiro

Quando o leiloeiro não possuir lotes, ou lotes alheios (gado, etc): Z_SL_Nome_do Leiloeiro

### Controle lista de sites

(Atualização) Criada a Lista de Sites 02, quando pegar um lote, pode escrever o nome dele em cima dos links com seu nome na frente

Preenchimento finalizado: - ok

Preenchimento com pendência: - Pendente "especificação do campo, ou do problema"

Erro: - Erro "especificação do erro" (em branco, cloudflare, falha no servidor.... seguir o padrão que já está)

### Outros erros

Caso seja identificado um erro de funcionamento que afete vários sites, abrir um issue no github especificando e dando links e nomes para melhor resolver

## Erros no preview

Quando clicar no preview do link que está testando (olho ao lado do link) e der erro no retorno da página, testar se as variáveis realmente não estão funcionando, neste caso, colocar o hold no nome do site e relatar erro na lista de controle.

## Ajax

Sempre que abrir o primeiro link de leiloeiro para testar, desabilitar o  javascript clicando nas configurações do console do navegaor (engrenagem a direita, ai lá no final... pelo menos no chrome) e atualizar a página.

Caso alguma informação não seja mostrada, é necessário alterar o cadastro do leiloeiro para Tipo de Paginação: AJAX e Delay para 2, ou testar delay maior caso ache necessário

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b13358d5-7531-47d7-8d2b-658f06099586)


![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/39fcc1ea-29a7-4f6a-b0fb-866bf3f32bb2)


## Tutoriais

Cadastro de sites: https://youtu.be/q2n6GNkcuLE

Introdução xPath: https://youtu.be/hB1BdqHLXT0

Exemplo 01 Zuk: https://youtu.be/INwSHZwfIjc

Exemplo 02 Biasi: https://youtu.be/GkxmZVA7mvA

Exemplo 03 Brame: https://youtu.be/s_E3Vas3WjE

