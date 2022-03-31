# CS 50's Web Programming with Python and Javascript

&nbsp;

## Search

Design a front-end for Google Serach, Google Image Search, and Google Advance Search.

&nbsp;

## Bakground

Recall from the lecture that we can create HTML form using `<form>` tag and can add `<input>` tags to create input fields for that form. Later in the course, we'll see how to write web applications that can accept form data as input. For this project, we'll write forms that send data to an existing web server: in this case, Google's.

When you perform a Google search, as by typing in a query into Google's homepage and clicking the "Google Search" button, how does that query work? Let's try to find out.

Navigate to [google.com](https://google.com), in a query like "**Harvard**" into the search field, and click the "**Google Search**" button.

As you probably expected, you should see Google serach results for "**Harvard**." But now, take a look at the URL. It should begin with `https://www.google.com/search`, the route on Google's website that allows for seraching. But following the route is a `?`, followed by some additional information.

&nbsp;

These additional pieces of information in the URL are known as the query string. The query string consist of sequence of `GET` parameters, where each parameter has a name and value. Query strings are generally formatted as

&nbsp;

`field1=value1&field2=value2&field3=value3...`

&nbsp;

Where an `=` separates the name of the parameter from its value, and the `&` symbol separates parameters from one another. These parameters are a way for forms to submit information to a web server, by encoding the form data in the URL.

Take a look at the **URL** for your Google serach results page. It seems there are quite a few parameters that Google is using. Look through the **\*URL** (it may be helpful to copy/paste it into a text editor), and see if you can find any mention of "**Harvard**," our query.

If you look through the **URL**, you should see that one of the **GET** parameters in the **URL** is `q=Harvard`. This suggests that the name for the parameter corresponding to a Google serach is `q` (likely short for "query").

It turns out that, while the other parameters provide useful data to Google, only the `q` parameter is required to perform a serach. You can test this for yourself by visiting `https://www.google.com/search?q=Harvard`, deleting all the other parameters. You should see the Google results!

Using this information, we can actually re-implement a front end for Google's homepage. Pase the below into an **HTML** file called `index.html`, and open it in a browser. You can alternatively download the `index.html` file directly from the "**Getting Started**" section below.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Search</title>
    </head>
    <body>
        <form action="https://www.google.com/search">
            <input type="text" name="q" />
            <input type="submit" value="Google Search" />
        </form>
    </body>
</html>
```

When you open this page in a browser, you should see a (very simple) **HTML** form. Type in a search query like "**HARVARD**" and click "Google Search", and you should be taken to Google's search results page!

How did that work? In this case, the `action` attribute on the `form` told the browser that when the form is submitte, the data should be sent to `https://www.google.com/search`. And by adding an `input` field to the form whose `name` attribute was `q`, whatever the user types into that field is included as **GET** parameter in the **URL**.

Your task in this project is to expand on this site, creating your own front-end for Google Serach, as by exploring Google's interface to indentify what **GET** parameters is expectes and adding the necessary HTML and CSS to your website.

## Getting Started

-   Download the distribution code from https://cdn.cs50.net/web/2020/spring/projects/0/search.zip and unzip it. You can skip this step if you manually created the `index.html` file by following the steps outlined in the "Background" section above.

## Specification

Your website must meet the following requirements:

-   Your website should have at least three pages: one for regular Google Search (which must be called `index.html`, one for Google Image Search, and one for Google Advanced Search).

    -   On the Google Image Search page, there should be three links in the upper-right of the page to go to the Image Search or Advance Search. On each of the other two paes, there should be a link in the upper-right to go back to Google Search.

-   On the Google Search page, the user should be able to type in a query, click "Google Search", and be taken to the Google search results for that page.

    -   Like Google's own, your search bar should be centered with rounded corners. The search button should also be centered, and should be beneath the search bar.

-   On the Google Image Search page, the user should able to type in a query, click a search button, and be taken to the Google Image search results for that page.

-   On the Google Advanced Search page, the user should be able to provide input for the following four fields (take from Google's own [advance search](https://www.google.com/advanced_search) options)

    -   Find pages with... "all these wors:"
    -   Find pages with... "this exact word or phrase:"
    -   Find pages with... "any of these words:"
    -   Find pages with... "none of these words:"

-   Like Google's own Advanced Search page, the four options should be stacked vertically, and all the text fields should be aligned.

    -   Consistent with Google's own CSS, the "Advance Search" button syoud be blue with white text.
    -   When the "Advance Search" button is clicked, the user should be taken to the search results page for their given query.

-   Add an "I'm Feeling Lucky" button to the main Google Search page. Consistent with Google's own behavior, clicking this link should take users directly to the first Google search result for the query, bypassing the normal result page.
    -   You may encounter a redirect notice when using the "I'm Feeling Lucky" button. Not to worry! This is an epxected consequence of a security feature implemented by Google.
-   The CSS you write hsould resemble Google's own aesthetics.

## Hints

-   To determine what the parameter names should be, you're welcome to experinemen
