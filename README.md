# BuzzFeed-Frontend
 BuzzFeed Front End Developer
The following functions loads and displys BuzzFeed articles using the BuzzFeed API in infinite loop. 25 feeds are displayed per page. 
Use of CROS API has been done to fetch data from cross-origin domain.

CROS url: https://cors-anywhere.herokuapp.com/

Loading JSON data:
//Following function fetches JSON data from BuzzFeed API URL for specified Page and saves it to feedData.
To fetch data from cross-origin domain this function uses CROS API url.

function getJSONforPage(url, page)

Displaying JSON feed data:
//It is used to display feeds on page as well as it can load next page if all feed displayed from current page.

function displayFeeds()

# To Run
Open index.html file with browser with supported file in same folder.
