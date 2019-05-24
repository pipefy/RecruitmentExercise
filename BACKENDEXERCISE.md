# Pipefy's Recruitment Exercise

Your job in this exercise is to build a new application from scratch which will connect via Pipefy's API to retrieve, store and display a list of cards. You may use any stack you're comfortable with, but it would be better if it where either Ruby or Elixir based.

This app should have a single page and it should display a table similar to this:

![](https://github.com/pipefy/RecruitmentExercise/blob/master/backend-example.png)

As you can see in the image above, at the top of the page there's the name of the **Organization**. Followed by the name of the **Pipe** and a table with his cards.

At the top right corner there is the `Fetch new data` button. When the user clicks it, the application connects to the API and fetches everything that it will need to build the interface.

At Pipefy, each organization can have multiple pipes. Each pipe has its own unique configuration including **Phases** and **Fields**. Each phase can have multiple fields. Both phases and fields are fully customizable by the user.

Within the pipe the user creates **Cards** which will run through the pipe's process following his rules and specifications. The card displays a dynamic form where the user can input values in the pipe's custom fields. So each card holds the _Field Values_ of the fields of every phase from the pipe.

The goal of this page is to display a complete list of cards from a specific pipe in the organization. The cards table must follow the pipe's settings and display fields in columns and each card shows its field values.

## Preparing for the test

Create a new account on the platform at (https://app.pipefy.com/) and select _Sales Pipeline_ as your template. This pipe will be used later for the test.

## How to access Pipefy's API?

[You can find the API documentation here.](https://pipefy.docs.apiary.io/)

## Rules and Objectives:

- You should use a new GitHub public repository to version the application's source code
- You're free to use any library you want
- The application should have automated tests
- The page should not hit the API everytime it's loaded, only when the `Fetch new data` button is clicked
- You need to create a database structure to store the data
- When fetching new data, the data in the database must be updated -- The strategy is up to you (e.g. overriding, even event-sourcing the data...).
- The database must be PostgreSQL

## Optional objectives

- Use Docker
- Make the target Pipe configurable (the strategy is up to you)

When you're done, send us the link to the GitHub reposity with a readme on how to run the application.

## Finding what you need among the endpoints:

To gather the data you need to complete the exercise you will consume our GraphQL API. Feel free to use whatever endpoints you need.

You may have noticed that, given the customizable structure Pipefy has, the structure of the data returned by the API is a bit complex. So here are some tips to help you gather what you will need:

- Organizations are the top level inside Pipefy
- Pipes can have multiples Phases and Fields
- Each Field is nested under a specific Phase
- Inside each Phase you can find his Cards too
- You'll find `fields` under Cards that returns all Field Values

## Good Luck!

You've one week to build the exercise and feel **free to ask** any questions you may have.

Thanks!
