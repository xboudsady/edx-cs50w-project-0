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

When you open this page in a browser.
