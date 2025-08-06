### Webscraping using Python

_Packages_: BeautifulSoup, Requests, Pandas

Steps;

- Import packages
- Get html from website in a usable state
- Query html

Import packages needed from module bs4.
Specify where the html is coming from i.e the url.
Use the get() function on requests imploring requests library to send a get request to url and return a response object.
Use the BeautifulSoup package to get html and assign variable to it.
Have a basic understanding of html e.g. tags, class etc. to be able to narrow down elements needed from website.
Inspect website to narrow down information needed.
Use find() and find_all() to query the html and get information needed from website.
Import pandas to input the data collected into its dataframe.
Convert data into csv and save.
