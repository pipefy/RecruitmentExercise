# Pipefy's Development Exercise

You job in this exercise is to build a new Rails application from scratch which will connect via Pipefy's API to download, store and display a list of cards.

This app should have a single page, the root page, and it should display something similar to this:

![](https://raw.githubusercontent.com/pipefy/RecruitmentExercise/master/exercise_page_output_example.png)

As you can see in the above image, there are multiple tables displaying **Cards**. Every table is grouped by it's **Pipe** name. And at the top of the page there is the name of the **Organization**.

At Pipefy, each organization can have multiple pipes. Each pipe is have its own unique configuration including **Phases** and **Fields**. Each phase inside can have different fields. Both phases and fields are fully customizable by the user.

When Pipe is all set, the user creates **Cards** which will run through the pipe's process following his rules and specifications.

The goal of this page is to display a complete list of cards in the organization. Each pipe must have his own table of cards and the columns of the table must follow the fields of every phase in the pipe.


## Requirements and Rules:

* The application must be a completely new Rails 5 application;
* You should use a new Github public repository to version the application's source code;
* You are free to use any Gem or Library you want;
* The page should not hit the API everytime it's loaded;
* The **[Fetch new data]** button should connect to the API and download everything the application need to its own database;
* You are free to choose whatever database you want;

## How to access Pipefy's API?

[You can find the API documentation here.](https://www.gitbook.com/book/pipefy/pipefy-api-docs/details)

Here is the credentials you will need to connect via API:

| E-Mail                                     | Token                | Organization ID |
|--------------------------------------------|----------------------|-----------------|
| pipefydevrecruitingfakeuser@mailinator.com | piBag2uUBesD6X1q78FR | 49232           |

You must hit this url domain to access the api: **[https://app.pipefy.com/](https://app.pipefy.com/)**

## Finding what you need among the endpoints:

To gather the data you need to complete the exercise you will consume different endpoints of this API. Some endpoints you will need to call several times and some will be useless. Feel free to use everyone you need.





