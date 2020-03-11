# Nightlogs and Daylogs
### jlyke 2020-03-11
Keck maintains a ticket database to record nighttime issues and daytime changes called the nightlog or daylog.

The database contains the following tables

* K1 nightlog
* K2 nightlog
* K1 daylog
* K2 daylog
* HQ daylog

[Main Nightlog/Daylog Page](https://www.keck.hawaii.edu/software/ndlog/webForm/index.php)

[Recently Modified Tickets](https://www.keck.hawaii.edu/software/ndlog/webForm/recentMods.php)

[Search Page (K1)](https://www.keck.hawaii.edu/software/ndlog/search/ndlogSearch.php?table=K1_Nightlog)

Fields on the search page are:

* Case insensitive
* Each field is treated as a single string (double quotes)
* Multiple fields are logically anded

Some fields that I find useful for searches

* Create_date
  * handles specific dates in mm/dd/yyyy format
  * handles between 10/01/2019 and 03/11/2020
* Details 
  * This is the body of the ticket
  * Single search term gives most results as the box is “double quoted"
* Dialog
  * Response to the ticket
* From_x
  * Sometimes you know who wrote that ticket you want to find
* Keyword
  * A decent proxy for “Instrument”, which is not a search field
  * **_Should_** be from a pull-down list so search terms are finite
* Topic
  * The ticket title
  * Free-form so sometimes hard to search
* UDate
  * Not as useful as “Create_date"
  * mm/dd/yy
  * Entering “20” will give you tickets only from 2020 and the 20th of any month
* Example
    * Keyword = mosfire
        * 745 results
    * Keyword = mosfire, Details = sidecar
        * 23 results
    * Keyword = mosfire, Details = sidecar, Create_date = between 8/1/2019 and 3/11/2020
        * 2 results