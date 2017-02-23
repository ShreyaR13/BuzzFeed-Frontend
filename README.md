# BuzzFeed-Frontend
 BuzzFeed Front End Developer
The following functions loads and displys BuzzFeed articles using the BuzzFeed API in infinite loop. 25 feeds are displayed per page. 
Use of CROS API has been done to fetch data from cross-origin domain. The functions use CROS API url.

The CROS url:
CROS url: https://cors-anywhere.herokuapp.com/

Loading JSON data:
//Following function fetches JSON data from BuzzFeed API URL for specified Page and saves it to feedData.
To fetch data from cross-origin domain this function uses CROS API url.

function getJSONforPage(url, page) {
                tmpData = "Error";
                tmpURL = CROS_URL + url + "?p=" + page;
                $("#feedsContainer").append("<img class='loadingSelector' src='img/loading.gif' alt='Loading' style='width:50px;height:50px;display:block;margin:auto;'>");

                $.ajax({
                    url: tmpURL,
                    dataType: 'JSON',
                    type: 'GET',
                    async: false,
                    success: function (data) {
                        feedData = data['buzzes'];
                    }
                });
            }
            
Displaying JSON feed data:
//It is used to display feeds on page as well as it can load next page if all feed displayed from current page.

function displayFeeds() {
                if (diplayed_post < 25) {
                    var step;
                    for (step = diplayed_post; step < diplayed_post + 5; step++) {
                        bigimgURL = feedData[step].images['big'];
                        feedDescription = feedData[step].description;

                        var $tmp = "<div class='block-grid__item fill-white xs-border'>";
                        $tmp = $tmp + "<img class='xs-col-12 xs-block' src='" + bigimgURL + "'><div class='xs-p1'>";
                        $tmp = $tmp + "<h5 class='xs-mb1'>" + feedDescription + "</h5></div></div>";
                        $("#feedsContainer").append($tmp);
                    };

                    diplayed_post += 5;
                }
