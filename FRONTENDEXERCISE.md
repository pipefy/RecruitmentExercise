# Recruitment Exercise - Pipefy

The objective is to evaluate your knowledge and experience with React and related libraries for front-end development.

You will build a React application that will render a Pipey form. This application must:

* Be a single page application, displaying all the form fields;
* Store internally the values of those fields, as the user fills them up;
* Submit the form to Pipefy's API;
* Display any error messages sent by the API.

![screen shot 2017-12-18 at 16 34 05](https://user-images.githubusercontent.com/465990/34122868-f39dae42-e414-11e7-9df0-8e287759dc98.png)

**Obs**: This is only a reference. The most important part of the application is not the layout and visual structure, but the the JavaScript code.

## Rules

* Your code must be hosted on a public GitHub repository;
* You may use whatever libraries you want, besides React (check out the Recommendations sections below);
  * In case you use a boilerplate library, such as `create-react-app`, you must create a separated git commit for the files created by this library;
* You must write automated tests, using the library of your choice;
* You must publish your application at [Heroku](https://dashboard.heroku.com/).

## API Access

Pipefy uses a [GraphQL](http://graphql.org/learn/) API to get and change data. The API's endpoint you will use is at: https://app.pipefy.com/public_api. You must use the `POST` HTTP method.

To **get the form data**, you will use the following **query**:

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

To **submit the form**, you will use the following **mutation**:

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

**Obs**: This example handles only the value for the first form's field, but the structure is the same for all of them. You must change it accordingly. Besides, we recommend the use of [GraphQL variables](http://graphql.org/learn/queries/#variables) for the fields values.

## Recommendations

We recommend [Redux](https://github.com/reactjs/redux) to help on managing the state of all your application.

## Deadline

This exercise must be completed within **one week** from the day it was sent to you.

## Good luck!

Feel free to ask **any questions** you might have during the development of your app.

Thank you!
