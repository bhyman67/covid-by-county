<h1>
    <p align="center">Covid by County Flask App</p>
</h1>

<h1></h1>

<p align="center"> <big>Click <a href="https://covid-by-county.herokuapp.com" target = "_blank">here</a> to run the app</big> </p>

### Description
The user can select both a state and county and then generate a line graph of daily confirmed cases. 

### Data

I used data from the COVID-19 [repository](https://github.com/CSSEGISandData/COVID-19) owned by the CSSE at Johns Hopkins University.

### Code

This application has two endpoints. Both endpoints show the state and county dropdowns. The user can select a location and then hit submit to pull up the graph. Hitting the submit button in both endpoints will take you to the graph endpoint with a query string specifying the selected location.

* The root endpoint shows only the location web form.
  * GET: ``` / ```
* The graph endpoint will show both the location web form and the time series chart of the location specified in the query string.
  * GET: ``` /graph/ ```
  * **Requires** a query string with two parameters:
    * State
    * County
  * The data pull from the CSSEGISandData COVID-19 repo happens every time this endpoint gets requested. Not ideal...  

There's only one function:

* pull_data()
  * makes a web request (GET) to the CSSEGISandData COVID-19 repo and uses the pandas read_csv funct to read in time_series_covid19_confirmed_US.csv. 
  * Some columns also get dropped and renamed

<p align="right">Click <a href="https://github.com/bhyman67/Covid-by-County">here</a> to view this project's repository<p>