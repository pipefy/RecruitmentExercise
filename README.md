# Pipefy's Recruitment Exercise

Your job in this exercise is to build a new Rails application from scratch which will connect via Pipefy's API to download, store and display a list of cards.

This app should have a single page, the root page, and it should display something similar to this:

![](https://raw.githubusercontent.com/pipefy/RecruitmentExercise/master/exercise_page_output_example.png)

As you can see in the image above, at the top of the page there's the name of the **Organization**. Followed by the name of the **Pipe** and a table with his cards.

At the top right corner there is the `Fetch new data` button. When the user clicks it, the application connects to the API and fetches everything that it will need to build the interface.

At Pipefy, each organization can have multiple pipes. Each pipe has its own unique configuration including **Phases** and **Fields**. Each phase can have multiple fields. Both phases and fields are fully customizable by the user.

Within the pipe the user creates **Cards** which will run through the pipe's process following his rules and specifications. The card displays a dynamic form where the user can input values in the pipe's custom fields. So each card holds the *Field Values* of the fields of every phase from the pipe.

The goal of this page is to display a complete list of cards from a specific pipe in the organization. The cards table must follow the pipe's settings and display fields in columns and each card shows its field values.

## Requirements and Rules:

* The application must be a completely new Rails application
* The database must be PostgreSQL
* You should use a new GitHub public repository to version the application's source code
* Your first commit should be the Rails scaffold (`rails new your_project`)
* You're free to use any Gem or Library you want
* The page should not hit the API everytime it's loaded, only when the `Fetch new data` button is clicked
* You need to create a database structure to store the data
* You need to deploy the application to [Heroku](www.heroku.com)
* You should write automated tests using what you prefer

When you're done, send us the link to the GitHub reposity and the live application running at Heroku.

## How to access Pipefy's API?

[You can find the API documentation here.](https://pipefy.docs.apiary.io/)

Here are the credentials you will need to connect via API:

| E-Mail                                     | Token                |
|--------------------------------------------|----------------------|
| pipefydevrecruitingfakeuser@mailinator.com | piBag2uUBesD6X1q78FR |

And here're the basic IDs you'll need:

| Organization ID | Pipe ID |
|-----------------|---------|
| 92858           | 335557  |

## Finding what you need among the endpoints:

To gather the data you need to complete the exercise you will consume our GraphQL API. Feel free to use whatever endpoints you need.

You may have noticed that, given the customizable structure Pipefy has, the structure of the data returned by the API is a bit complex. So here are some tips to help you gather what you will need:

* Organizations are the top level inside Pipefy
* Pipes can have multiples Phases and Fields
* Each Field is nested under a specific Phase
* Inside each Phase you can find his Cards too
* You'll find `fields` under Cards that returns all Field Values


## Good Luck!

Take your time to build the exercise and feel **free to ask** any questions you may have.

Thanks!
