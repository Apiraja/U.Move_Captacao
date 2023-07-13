# Diretrizes


# 12/07
## Cadastro de leiloeiros com problema
Como muitos sites estão apresentando erros na visualização e captação, por hora podem criar um "leiloeiro teste" com o nome de vocês: A_TESTE_Seu Nome. Lá dentro não precisa necessariamente preencher tudo sempre, podem só abrir onde coloca as variáveis, inserir o link, informações se é ajax, atualizar e testar.

Para testar podem usar o ponto antes de uma classe ou # antes de um id, lembrando que só valem para quando o id ou a class não contém espaço

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/fe4b1d23-19a5-4bfd-a273-726577b1862a)

Ai podem inserir apenas no controle "- Erro site não cadastrado", assim perdemos menos tempo.


# 11/07

## Nomeclatura de leiloeiros aleatórios
Quando o leiloeiro não possuir lotes, ou lotes alheios (gado, livros..): Z_SL_Nome_do Leiloeiro, ou apenas inserir no controle.
Carros e eletronicos, vamos cadastrar.
Se tiver dúvidas, pergunte

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

