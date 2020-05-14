# APP iOS em Swift 5

## Estrutura:
O aplicativo foi criado utilizando:
- [ ] 1 - ViewModel
- [ ] 2 - ViewControllers

O ViewModel está buscando dados e fazendo conexão/troca de dados entre os dois ViewControllers.
Para a utilização do aplicativo em modo offline, esta sendo utilizado SQLite, onde é possível armazenar os dados localmente no aparelho.
Já para a serialização, está sendo utilizado Codable , e para o network request está sendo utilizado URLSession.

## Models:
Foram avaliados 3 diferentes models como resposta do Rest API.

*Live Request - >
- [ ] Success = true && QuoteData
- [ ] Success = false && Error

*List Request - >
- [ ] Success = true && CurrencyData
- [ ] Success = false && Error

Os 3 models estão sendo manuseados/definidos no file ClientAPI para evitar erros/crash no momento do request.

## Layout:
Para uma resposta rápida e melhor eficiência do aplicativo, a página principal consiste em 4 views, dois Buttons, um EditText e um TextView no qual eles tem interação direta entre eles.
Quando o usuário seleciona qualquer moeda o valor atualiza sem que ele/ela tenha que pressionar qualquer outro botão, tendo assim uma resposta rápida à interação do usuário.
Quanto a página de seleção da moeda, foi adicionado um filtro em formato SearchBar para pesquisa pelo nome ou código da moeda e também foi adicionado a opção de organizar por ordem crescente tanto pelo código como pelo nome.

## Testes realizados:

### Online -> Internet Conectada.

- [ ] Abrir aplicativo. (Abre a pagina de resultado.)
- [ ] Clicar na moeda de origem, no caso USD. (Abre a pagina de seleção.)
- [ ] Pesquisar EUR no searchBar.
- [ ] Clicar na moeda EUR. (Fecha a pagina de seleção e abre a de resultado.)
- [ ] No campo de entrar text, adicionar 10000. (Valor visualizado 100.00)
- [ ] Visualizar no campo de resultado o valor 607.29.
- [ ] Permitir rotação de tela e rotar a tela, valores permanecem o mesmo.
- [ ] Rotar a tela para posição inicial, clicar no botāo de destino (BRL). (Abre a pagina de seleção.)
- [ ] Pesquisar USD no searchBar.
- [ ] Clicar na moeda USD. (Fecha a pagina de seleção e abre a de resultado.)
- [ ] Visualizar no campo de resultado o valor 108.96.
- [ ] Clicar na moeda de origem, no caso EUR. (Abre a pagina de seleção.)
- [ ] Clicar no icon (Sort).
- [ ] Clicar na opção "Sort by Name". (A list eh ordenada pelo nome)
- [ ] Clicar no icon (Sort).
- [ ] Clicar na opção "Sort by Code". (A list eh ordenada pelo código)

### Offline -> Airplane Mode (Modo Avião)

- [ ] Abrir aplicativo. (Abre a pagina de resultado e a "Connection Error" toast é visualizada.)
- [ ] Clicar na moeda de origem, no caso USD. (Abre a pagina de seleção.)
- [ ] Pesquisar EUR no searchBar.
- [ ] Clicar na moeda EUR. (Fecha a pagina de seleção e abre a de resultado.)
- [ ] No campo de entrar text, adicionar 10000. (Valor visualizado 100.00)
- [ ] Visualizar no campo de resultado o valor 607.29.
- [ ] Permitir rotação de tela e rotar a tela, valores permanecem o mesmo.
- [ ] Rotar a tela para posição inicial, clicar no botāo de destino (BRL). (Abre a pagina de seleção.)
- [ ] Pesquisar USD no searchBar.
- [ ] Clicar na moeda USD. (Fecha a pagina de seleção e abre a de resultado.)
- [ ] Visualizar no campo de resultado o valor 108.96.
- [ ] Clicar na moeda de origem, no caso EUR. (Abre a pagina de seleção.)
- [ ] Clicar no icon (Sort).
- [ ] Clicar na opção "Sort by Name". (A list eh ordenada pelo nome)
- [ ] Clicar no icon (Sort).
- [ ] Clicar na opção "Sort by Code". (A list eh ordenada pelo código)

#### Note: Para que o offline mode funcione é necessário que o usuário tenha tido pelo menos uma "SuccessResponse" do network request.

## Executar o app

O app utiliza o [API CurrencyLayer](https://currencylayer.com/documentation) para a API, será necessário fazer um cadastro no plano gratuito para obter uma chave de acesso e atualizar a "key" variável no arquivo "ClientAPI.kt".