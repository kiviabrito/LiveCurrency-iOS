# Live Currency para iOS - Swift5

## Funcionalidade

Calcular valores em diferente moedas.

## Estrutura:

O aplicativo foi criado utilizando:

- [ ] 1 - ViewModel
- [ ] 2 - ViewControllers

O ViewModel está procurando dados e conectando / trocando dados entre os dois ViewControllers. 

Para usar o aplicativo no modo offline, o SQLite está sendo usado, onde é possível armazenar os dados localmente no dispositivo. Para serialização, Codable está sendo usado e, para solicitação de rede, URLSession está sendo usado.


## Modelos:

Foram avaliados 3 diferentes models como resposta do Rest API.

>Live Request - >
- [ ] Success = true && QuoteData
- [ ] Success = false && Error

>List Request - >
- [ ] Success = true && CurrencyData
- [ ] Success = false && Error

Os 3 models estão sendo manuseados/definidos no file ClientAPI para evitar erros/crash no momento do request.

## Visualizações:

ResultViewController:

![alt text](https://github.com/kiviabrito/LiveCurrency-iOS/blob/master/Screenshot_ResultViewController.png) 

SelectionViewController:

![alt text](https://github.com/kiviabrito/LiveCurrency-iOS/blob/master/Screenshot_SelectionViewController.png) 


#### Note: Para que o offline mode funcione é necessário que o usuário tenha tido pelo menos uma "SuccessResponse" do network request.

## Executar o app

O app utiliza o [API CurrencyLayer](https://currencylayer.com/documentation) para a API, será necessário fazer um cadastro no plano gratuito para obter uma chave de acesso e atualizar a "key" variável no arquivo "ClientAPI.kt".
