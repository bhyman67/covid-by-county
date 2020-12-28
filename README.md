<h1>
    <p align="center">Covid by County Flask App</p>
</h1>

<h1></h1>

<p align="center"> <big>Click <a href="https://covid-by-county.herokuapp.com">here</a> to run the app</big> </p>

### Description
The user can select both a state and county and then generate a line graph of daily confimed cases. 

### Data

I used data from the COVID-19 [repository](https://github.com/CSSEGISandData/COVID-19) owned by the CSSE at Johns Hopkins University.

### Code

The code for this project is in [here](https://github.com/bhyman67/Covid-by-County).

This application has two endpoints, on of which is parameterized:

* The root url. Shows State and county drop downs along with the submit button.
  * GET: ``` / ```
* Graph endpoint accessed by the submit button. URL path is defined by what was submited in the dropdowns. 
  * GET: ``` /graph/ ```
  * This endpoint **requires** a query string with two parameters:
    * State
    * County
  * The data pull from the repo happens everytime this endpoint gets requested. Not ideal :(  

There's only one function:

* pull_data()
  * makes a web request (GET) to the CSSEGISandData COVID-19 repo and uses pandas read_csv funct to read in time_series_covid19_confirmed_US.csv. 
  * Some columns also get droped and renamed

<p align="right">Back to <a href="https://bhyman67.github.io/">BHyman Analytics<a><p>