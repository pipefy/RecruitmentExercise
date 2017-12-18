# Exercício de Recrutamento - Pipefy

O objetivo deste exercício é avaliar o conhecimento de React e suas bibliotecas relacionadas para desenvolvimento front-end.

Você deve construir uma aplicação React que renderize um formulário do Pipefy. Esta aplicação deverá:

* Ter uma única página, que mostra todos os campos deste formulário;
* Armazenar os valores destes campos conforme forem preenchidos;
* Submetê-los à API do Pipefy quando o formulário for enviado (lembrando de validá-los se houverem mensagens de erro).

A aplicação final deverá se parecer com isso:

![screen shot 2017-12-18 at 16 34 05](https://user-images.githubusercontent.com/465990/34122868-f39dae42-e414-11e7-9df0-8e287759dc98.png)

**Obs**: Esta é apenas uma imagem de referência para ajuda visual. O importante neste exercício não é o layout e a organização visual, e sim o código em si.

## Regras

* O exercício deverá ser feito em um novo repositório público no GitHub;
* Você pode usar qualquer biblioteca que desejar;
  * Caso use uma biblioteca com boilerplate como o create-react-app, um commit com os arquivos de boilerplate deve ser feito separado do resto do seu código
* Você deve escrever testes automatizados, usando a biblioteca e a forma que preferir;
* Sua aplicação deve ser hospedada no [Heroku](https://dashboard.heroku.com/);

## Acesso à API

O Pipefy usa uma API [GraphQL](http://graphql.org/learn/) para a consulta e modificação das suas informações. A API para acessar o formulário se encontra neste endpoint: https://app.pipefy.com/public_api

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
      __typename
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

**Obs**: Este exemplo contempla somente o valor do primeiro campo. Porém, a estrutura básica se mantém. Além do mais, recomendamos que use variáveis GraphQL para fazer a inclusão dos valores dos campos

## Recomendações

Recomendamos que use o [Redux](https://github.com/reactjs/redux) para facilitar o gerenciamento do estado da sua aplicação.

## Prazos

Este exercício deverá ser completado em até **uma semana** contando a partir do dia em que ele foi enviado para você.

## Boa sorte!

Fique à vontade para tirar _quaisquer dúvidas_ conosco, caso elas surjam.

Obrigado!
