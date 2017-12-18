# Exercício de Recrutamento - Pipefy

O objetivo deste exercício é avaliar o conhecimento de React e suas bibliotecas relacionadas para desenvolvimento front-end.

Você deve construir uma aplicação React que renderize um Public Form. Esta aplicação deverá:

* Ter uma única página, que mostra todos os campos deste Public Form;
* Armazenar os valores destes campos conforme forem preenchidos;
* Submetê-los à API do Pipefy quando o formulário for enviado (lembrando de validá-los se houverem mensagens de erro).

## Regras

* O exercício deverá ser feito em um novo repositório público no GitHub;
* Você pode usar qualquer biblioteca que quiser;
  * Caso use uma biblioteca com boilerplate como o create-react-app, um commit com os arquivos de boilerplate deve ser feito separado do resto do seu código
* Você deve escrever testes automatizados, usando a biblioteca e a forma que preferir;
* Sua aplicação deve ser hospedada no [Heroku](https://dashboard.heroku.com/);

## Acesso à API

O Pipefy usa uma API [GraphQL](http://graphql.org/learn/) para a consulta e modificação das suas informações. A API para acessar o Public Form se encontra neste endpoint: https://app.pipefy.com/public_api

Para ler as informações do formulário, você usará a seguinte _query_:

```
{
  publicForm(formId: "1lf_E0x4") {
    publicFormSettings {
      organizationName
      submitButtonText
      title
    }

    formFields {
      ...on ShortTextField {
      	id
        label
      }
      ...on LongTextField {
        id
        label
      }
			...on SelectField {
        id
        label
        options
      }
      ...on RadioVerticalField {
        id
        label
        options
      }
      ...on ChecklistVerticalField {
        id
        label
        options
      }
      ...on DateField {
        id
        label
      }
    }
  }
}
```

Para submeter o formulário, você usará a seguinte _mutation_:

```
mutation {
  submitPublicForm(input: {
    formId: "1lf_E0x4",
    filledFields: [
      {
        fieldId: "your_name",
        fieldValue: "Teste"
      }
    ]
  }) {
    repoItem {
      id
      title
    }
  }
}
```

**Obs**: Este exemplo contempla somente o valor do primeiro campo. Porém, a estrutura básica se mantém.

## Recomendações

Recomendamos que você use o [Apollo Client](https://github.com/apollographql/apollo-client) para facilitar a comunicação da sua aplicação com a API GraphQL do Pipefy.

Também recomendamos que use o [Redux](https://github.com/reactjs/redux) para facilitar o gerenciamento do estado da sua aplicação.

## Prazos

Este exercício deverá ser completado em até **uma semana** contando a partir do dia em que ele foi enviado para você.

## Boa sorte!

Fique à vontade para tirar _quaisquer dúvidas_ conosco, caso elas surjam.

Obrigado!
