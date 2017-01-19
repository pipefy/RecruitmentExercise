# Pipefy's Recruitment Exercise

Your job in this exercise is to build a new Rails application from scratch which will connect via Pipefy's API to download, store and display a list of cards.

This app should have a single page, the root page, and it should display something similar to this:

![](https://raw.githubusercontent.com/pipefy/RecruitmentExercise/master/exercise_page_output_example.png)

As you can see in the image above, there are multiple tables displaying **Cards**. Every table is grouped by it's **Pipe** name. And at the top of the page there is the name of the **Organization**.

At the top right corner there is the [Fetch new data] button. When the user clicks it, the application connects to the API and fetch everything that will need to build the interface.

At Pipefy, each organization can have multiple pipes. Each pipe have its own unique configuration including **Phases** and **Fields**. Each phase can have multiple fields. Both phases and fields are fully customizable by the user.

Within the pipe the user creates **Cards** which will run through the pipe's process following his rules and specifications. The card displays a dynamic form where the user can input values in pipe's custom fields. So the each card holds the *Field Values* of the fields of every phase from the pipe. :)

The goal of this page is to display a complete list of cards of every pipe in the organization. The cards table must follow the pipe settings and display fields in columns and each card show its field values.

## Requirements and Rules:

* The application must be a completely new Rails application;
* You should use a new Github public repository to version the application's source code;
* You are free to use any Gem or Library you want;
* The page should not hit the API everytime it's loaded, only when the[Fetch new data] is clicked;
* You need to create a database structure to store the data you need to build the interface;
* You need to PostgreSQL and deploy the application to [Heroku](www.heroku.com);
* When you are done, send us the link to the GitHub reposity and the live application running at Heroku;
* You should write automated tests using what you prefer;

## How to access Pipefy's API?

[You can find the API documentation here.](https://www.gitbook.com/book/pipefy/pipefy-api-docs/details)

Here is the credentials you will need to connect via API:

| E-Mail                                     | Token                |
|--------------------------------------------|----------------------|
| pipefydevrecruitingfakeuser@mailinator.com | piBag2uUBesD6X1q78FR |

The Pipefy's organization you will displays the card is:

| Organization ID |
|-----------------|
| 49232           |

## Finding what you need among the endpoints:

To gather the data you need to complete the exercise you will consume different endpoints of this API. Some endpoints you will need to call several times and some will be useless. Feel free to use everyone you need.

You may noticed that, given the customizable structure Pipefy have, the structure of the data returned by the API is a bit complex. So here is some tips to help you gather what you will need:

* Inside the pipe, you will have the `id`s of its Phases;
* Requesting each phase will give you the `fields` of every phase;
* Inside the phases lives the `cards` too;
* To get the field values you will need to look in 2 card properties: `current_phase_detail` and `other_phase_details`;


## Good Luck!

Take your time to build the exercise and feel **free to ask** any questions you may have.

Thanks!
