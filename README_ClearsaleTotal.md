[checkmark]: https://raw.githubusercontent.com/mozgbrasil/mozgbrasil.github.io/master/assets/images/logos/logo_32_32.png "MOZG"
![valid XHTML][checkmark]

[url-method]: http://portal.clearsale.com.br/solucoes/e-commerce/total
[requerimentos]: http://mozgbrasil.github.io/requerimentos/
[contact-clearsale]: http://portal.clearsale.com.br/solucoes/e-commerce/total
[tickets]: https://cerebrum.freshdesk.com/support/tickets/new
[preco]: http://www.cerebrum.com.br/preco/
[getcomposer]: https://getcomposer.org/
[uninstall-mods]: https://getcomposer.org/doc/03-cli.md#remove
[artigo-composer]: http://mozg.com.br/ubuntu/composer
[ioncube-loader]: http://www.ioncube.com/loaders.php
[acordo]: http://mozg.com.br/acordo-licenca-usuario-final/

# Mozg\ClearsaleTotal

## Sinopse

Integração a [Clearsale][url-method]

## Demonstração

[![Clique para visualizar o vídeo](https://img.youtube.com/vi/G0H8SXe1lec/0.jpg)](https://youtu.be/G0H8SXe1lec "Clique para visualizar o vídeo")

## Motivação

Atender o mercado de módulos para Magento oferecendo melhorias e um excelente suporte

## Suporte / Dúvidas

Para obter o devido suporte [Clique aqui][tickets], relatando o motivo da ocorrência o mais detalhado possível e anexe o print da tela para nosso entendimento

## Preço

[Clique aqui][preco]

## Recursos

Análise de registro

## Característica técnica

No frontend no /checkout/ é carregado o profiling onde é passado o session_id

No backend na visualização do pedido é possível disparar analise do registro do pedido

No backend na grade de dados dos pedidos é possível disparar ações em massa dos registros dos pedidos

Foi implementado a possibilidade de analisar em massa o status do retorno da Clearsale para os pedidos previamente selecionado

Dessa forma pode ser feito a captura manualmente de cada pedido, acessando a fatura do pedido e clicando no botão "Capturar"

## Testando na Heroku

Gostaria de apresentar o aplicativo que disponibilizei para a plataforma Heroku

Com apenas 1 clique, o aplicativo cria sua loja virtual usando a plataforma de comércio eletrônico Magento e instala os módulos da MOZG

[https://github.com/mozgbrasil/heroku-magento#descrição](https://github.com/mozgbrasil/heroku-magento#descrição)

## Instalação - Atualização - Desinstalação - Desativação

--

Sugiro "printar" as telas com todos os procedimentos executados

Envie para nós as imagens das telas na eventualidade de quaisquer dificuldades

--

Este módulo destina-se a ser instalado usando o [Composer][getcomposer]

Execute o seguinte comando no terminal, para visualizar a existencia do Composer e sua versão

	composer --version

Caso não tenha o Composer em seu ambiente, sugiro ler o seguinte artigo [Clique aqui][artigo-composer]

--

É necessário que o servidor tenha o suporte a extensão [ionCube PHP Loader][ioncube-loader]

Para visualizar a existência da extensão nesse ambiente denominado PHP CLI, execute o seguinte comando no terminal

	php -v

Para visualizar se essa extensão está ativa em seu servidor no ambiente denominado PHP WEB

Certique se da presença do arquivo phpinfo.php na raiz do seu projeto

	<?php phpinfo(); ?>

Caso não exista o arquivo phpinfo.php na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

Acesse o arquivo pelo browser

Em seguida pesquise pelo termo "ionCube PHP Loader"

Caso o seu servidor não tenha o suporte a extensão, entre em contato com sua empresa de hospedagem e peça para que eles ativem a extensão

Caso tenha a permissão e queira ativar a extensão, [Clique aqui][ioncube-loader]

Em "Loader Downloads API", efetue download do pacote compatível com o seu servidor

Descompacte o pacote e faça upload do arquivo "loader-wizard.php" para seu servidor, onde será demonstrado o passo a passo para a ativação da extensão

[Clique aqui](https://youtu.be/GZ2J6MLkko4) para ver os processos executados

--

Na presença do "ionCube PHP Loader" efetue o download do seguinte arquivo e coloque na raiz do seu servidor e acesse, se funcionar quer dizer que o "ionCube" está lendo esse tipo de encriptação

https://raw.githubusercontent.com/mozgbrasil/heroku-magento/master/phpinfo-ioncube-encoder10-x86-64-php_72.php

--

Para utilizar o(s) módulo(s) da MOZG é necessário aceitar o [Acordo de licença do usuário final][acordo]

--

Sugiro manter um ambiente de testes para efeito de testes e somente após os devidos testes aplicar os devidos procedimento no ambiente de produção

--

Sugiro efetuar backup da plataforma Magento e do banco de dados

--

Antes de efetuar qualquer atualização no Magento sempre mantenha o Compiler e o Cache desativado

--

Certique se da presença do arquivo composer.json na raiz do seu projeto Magento e que o mesmo tenha os parâmetros semelhantes ao modelo JSON abaixo

	{
	  "minimum-stability": "dev",
	  "prefer-stable": true,
	  "license": [
	    "proprietary"
	  ],
	  "repositories": [
	    {
	      "type": "composer",
	      "url": "https://packages.firegento.com"
	    }
	  ],
	  "extra": {
	    "magento-root-dir": "./",
	    "magento-deploystrategy": "copy",
	    "magento-force": true
	  }
	}

Caso não exista o arquivo composer.json na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

### Para instalar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer require mozgbrasil/magento-clearsale-php_72:dev-master

Você pode verificar se o módulo está instalado, indo ao backend em:

	STORES -> Configuration -> ADVANCED/Advanced -> Disable Modules Output

--

### Para atualizar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

Antes de efetuar qualquer processo que envolva atualização no Magento é recomendado manter o Compiler e Cache desativado

	composer update

Na ocorrência de erro, renomeie a pasta /vendor/mozgbrasil e execute novamente

Para checar a data do módulo execute o seguinte comando

	grep -ri --include=*.json 'time": "' ./vendor/mozgbrasil

--

### Para [desinstalar][uninstall-mods] o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer remove mozgbrasil/magento-clearsale-php_72

--

### Para desativar o módulo

1. Antes de efetuar qualquer processo que envolva atualização sobre o Magento é necessário manter o Compiler e Cache desativado

2. Caso queira desativar os módulos da MOZG renomeie a seguinte pasta app/code/local/Mozg

A desativação do módulo pode ser usado para detectar se determinada ocorrência tem relação com o módulo

--

## Como configurar o método de antifraude

Para configurar o método de antifraude, acesse no backend em:

	∞ MOZG ∞ -> Anti-Fraud Methods ->  Total ClearSale, Total Guaranted & Application - (powered by MOZG)

Você terá os campos a seguir

### • **Licença para uso comercial**

Informe a Licença para uso comercial

### • **Ativar**

Para "ativar" ou "desativar" o uso do método

### • **Modo teste/produção**

Deve ser informado o devido ambiente

### • **Entity code - ambiente de teste**

Entity code relativo ao ambiente de teste

### • **Entity code - ambiente de produção**

Entity code relativo ao ambiente de produção

### • **Tipo do e-commerce**

Tipo do e-commerce

### • **Relacionamento de pagamentos**

Informe a relação do seu método de pagamento ativo com o método de pagamento da ClearSale

### • **Nome da ação**

Para ser exibido o debug do módulo informe na URL o seguinte parametro ?debug=true

Deve ser mapeado as UrlAction relativa

### • **Nome do bloco**

Para ser exibido o debug do módulo informe na URL o seguinte parametro ?debug=true

Deve ser mapeado o nome do bloco relativo

### • **FingerPrint App**

A ClearSale deverá informar qual valor deve ser utilizado. Essa informação serve para identificar o seu website no sistema da ClearSale.

## Perguntas mais frequentes "FAQ"

## Fluxo de integração

Este fluxo é responsável por demonstrar a integração entre o cliente e a ClearSale:

    Loja                                                                 ClearSale
     |                                                                       |
     |----- (A) solicitação de análise de risco (sendOrders) --------------->|
     |                                                                       | (B) realiza processamento
     |<---- (C) envia resposta ----------------------------------------------|
     |                                                                       |
     |----- (D) realiza a cobrança / cancela a compra / tenta novamente ---->|

* (A) A loja realiza uma solicitação de análise de risco, informando os dados da compra e do comprador.
* (B) A ClearSale processa a requisição.
* (C) A ClearSale responde a requisição.
* (D) Caso a resposta de (C) seja aprovada, a loja deverá realizar a cobrança.
* (D) Caso a resposta de (C) seja reprovada, a loja não deverá realizar a cobrança.
* (D) Caso a resposta de (C) seja aguardando aprovação, a loja deverá realizar novas consultas na plataforma na
ClearSale até que o status da análise mude para aprovado ou reprovado.

## Processo de Homologação

* No Frontend

Efetue a geração de 10 novos pedidos, na finalização de cada pedido efetue o logout da conta e repita novamente o processo de geração do novo pedido e nova conta.

Obs. No formulário de cadastro, caso o nosso módulo de clientes esteja ativo o mesmo tem automação de criação de conta ficticia para isso segure a tecla "Shift" em seguido de um "Duplo click" sobre o campo "Cidade", dessa forma deve ser auto-preenchido o formulário de cadastro com dados ficticios.

Se possível utilize o máximo de browsers simultâneo para agilizar o processo da criação dos pedidos.

* No Backend

Acesseo menu, Vendas -> Pedidos

Ao selecionar o(s) pedido(s) é possível disparar o processo para a "checagem de fraude" em massa

Sendo exibido o retorno da ClearSale

Caso não seja exibido o retorno da ClearSale, entre em contato conosco para que seja feita a analise da ocorrência

* Solicitando a homologação

Crie e-mail

Enviar assunto no seguinte formato:

Projeto: https://www.com.br/ / Sobre: Homologação T-ClearSale

Em seguida envie e-mail para "integracao@clearsale.com.br" e informe

	Boa Tarde

	Sobre o projeto: https://www.com.br/

	Acabo de enviar 10 pedidos em massa para a ClearSale

	Favor efetuar homologação

	Fico no aguardo do EntityCode do ambiente de produção

	Conforme imagem vemos a integração do Fingerprint no /checkout/

	Os parâmetros "Prazo de Entrega" e "Dados do Cartão" devem ser enviado, caso tenha o registro armazenado

* FAQ

O parâmetro "Fingerprint" deve ser enviado para todos os pedidos pois o script é integrado no /checkout/ se o mesmo não foi recebido de forma intermitente provavelmente pode ter ocorrido alguma instabilidade no serviço da ClearSale

O parâmetro "Prazo de Entrega" deve ser enviado, caso no método de entrega houver o registro do prazo  

Os parâmetros para "Dados do Cartão" deve ser enviado caso o método de pagamento armazene o número do cartão de crédito e suas demais informações no padrão da plataforma Magento como é o caso do método nativo "Cartão de crédito salvo", tambêm é possível mapear atributos de módulos de terceiros

### Teste de integração

Podemos efetuar o testes de integração acessando

	http://homologacao.clearsale.com.br/integracaov2/service.asmx

	http://www.clearsale.com.br/integracaov2/service.asmx

ou

	http://homologacao.clearsale.com.br/integracaov2/service.asmx?wsdl

	http://www.clearsale.com.br/integracaov2/service.asmx?wsdl

Podemos fazer o teste de integração pelo ambiente da ClearSale

	http://homologacao.clearsale.com.br/integracaov2/service.asmx?op=SendOrders

E informe o seguinte conteudo para cada campo

	entityCode: ???
	xml: <string xmlns="http://www.clearsale.com.br/integration">string</string>

### Dados de contato - Clearsale

Para entrar em contato com a [Clearsale][contact-clearsale]

integracao@clearsale.com.br

Indira Marcela Borges O. dos Santos | Sustentação Técnica | Integração | +55 11 3728-8788 ramal 1332

## Manual

Total ClearSale, Total Guaranteed & Application - Versão 3.4

http://portal.clearsale.com.br/downloads/total-tg-application-manual-integracao.pdf

:cat2:
