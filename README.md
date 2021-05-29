# Airline Analysis Project


<sup>GitHub won't show plotly plots (interactive charts), please view them here [nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb) instead.</sup>

<b>Description</b>
------
This is a project based on a made-up scenario: 

<i>"A start-up airline wants you to provide a report that addresses the following criteria prior to its official launch. Conduct data analysis and provide 
visualizations that may assist you with this task."</i>

Criteria:

- Airline is based in the United States, so recommend a US hub/base 🇺🇸
- Propose a fleet, short and long range capabilites ✈️
- Provide some predictions 📈
- Potential routes both domestic and international 🌎
- Include visualizations and a report on cost of purchasing selected aircraft 📊
- And, anything else that may be helpful ✅

<b>Introduction</b>
------
The data sets used have been collated by me off the web. They have been provided. The majority of the code was written in Python through Jupyter Notebooks.
All files related to this project have also been provided in this repository. 

First, we will examine and clean/tidy our data sets. Next with the now relevant/short-listed data, we began to collate our analysis, finalizing our results and final decisions whilst simultaneously addressing the airline's criteria.

For full code, visualizations and analysis, refer to the Jupyter Notebooks (<i>.ipynb</i>) or [nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb).

<b>Cleaning & Short Listing Data</b>
------
Multiple data sets were loaded into MySQL and the process of cleaning and short listing data was done using Python's MySQL Connector library. We addressed multiple criteria to cut down to the final best remaining planes. From this, we produced finalists in aircraft choice and airport choice [<i>see sqlqueries.ipynb</i>]. Most airlines operate both short-range and long-range aircraft so we have decided to do the same. Only two aerospace manufacturers are in contention for both types of aircraft, Airbus (A...) and Boeing (7...).

For short-range and long-range aircraft, the choices will be between:<br>
![Screen Shot 2021-05-27 at 8 57 01 pm](https://user-images.githubusercontent.com/65270652/119814740-16fcd000-bf2e-11eb-85e9-fea0737651ee.png)</br>

For airport, the choice will be:<br>
![Screen Shot 2021-05-27 at 9 06 11 pm](https://user-images.githubusercontent.com/65270652/119815863-5f68bd80-bf2f-11eb-9b34-4ee445547d26.png)</br>

Through this process, we also identified competitors and their bases:<br>
![Screen Shot 2021-05-27 at 9 08 40 pm](https://user-images.githubusercontent.com/65270652/119816153-b79fbf80-bf2f-11eb-85e5-70cf04045547.png)</br>
- where <i>KSEA</i> is the ICAO code for Seattle-Tacoma International Airport, etc ...

<b>Los Angeles International Airport</b>
------
We have determined that the airline will be based at Los Angeles International Airport (LAX). 
<details>
<summary>ICAO</summary>
<p>KLAX</p>
</details>
<details>
<summary>Address</summary>
<p>1 World Way, Los Angeles, CA 90045, United States</p>
<br>
  <img src = https://user-images.githubusercontent.com/65270652/119822596-2df3f000-bf37-11eb-8e25-c93f25f43cde.png>
       </br>
</details>
<details>
<summary>Runways</summary>
<p>4 runways <br>Longest is 12,923ft</br></p>
</details>

Through using Python libaries [<i>see main.ipynb</i>], we created some visualisations displaying total passenger boardings at LAX airport. Further, we also made some predictions about total passenger boardings across the next couple of years.
<details>
<summary>With 2020 data</summary>
<p>Hypothetically, this project is meant to be constructed without COVID-19 but the data available for 2020 includes the impact of COVID-19 on the airline industy. Both charts below, display the spread of total passenger boardings at LAX.</p>
<img src = https://user-images.githubusercontent.com/65270652/119819133-6691ca80-bf33-11eb-9005-b3f055dc2f77.png>
<img src = https://user-images.githubusercontent.com/65270652/119819684-fcc5f080-bf33-11eb-9289-f12d7359acfc.png>

<br>Running a linear regression, we predicted the total passenger boardings for LAX (year 2021 - 2024).</br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119820325-b02ee500-bf34-11eb-8619-0359d1c31db2.png></br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119820387-c5a40f00-bf34-11eb-86c3-e38fabb8f9c5.png></br>
- The green fitted line represents the predicted values (extrapolation)
</details>
<details>
  <summary>Without 2020 data</summary>
  <p>Obviously the airline industry took a massive hit due to COVID-19. The 2020 data displays this change. Here, we pretend that COVID never happened. Both charts below, display the spread of total passenger boardings at LAX.</p>
  <img src = https://user-images.githubusercontent.com/65270652/119821347-cd17e800-bf35-11eb-81ad-9b125b0452fe.png>
  <img src = https://user-images.githubusercontent.com/65270652/119821538-05b7c180-bf36-11eb-8866-8f84c77e9c8d.png>
  
  <br>Running a linear regression, we predicted the total passenger boardings for LAX (year 2020 - 2024).</br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119821942-74951a80-bf36-11eb-9343-c998f2be4787.png></br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119822045-9393ac80-bf36-11eb-861c-4bd7669b2d5e.png></br>
  - The green fitted line represents the predicted values (extrapolation)
</details>
  
<b>Determining Aircraft</b>
------
To help determine exactly which of the airplanes to select, multiple charts and graphs have been produced to assist, [<i>see main.ipynb</i>].

<details>
  <summary>Short Range Aircraft</summary>
  <br><i><b>See the following price chart:</b></i></br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119823261-f0dc2d80-bf37-11eb-9d92-f7637b4935c6.png></br>
  <ul>
  <li>We find that Boeing on average is $6.75 million more expensive than Airbus</li></ul>
  
  <br><i><b>See the following range and order numbers interactive graph:</i></b></br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119829990-29333a00-bf3f-11eb-88c5-c11317dab777.png></br>
  <ul>
  <li>[<i>[nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb)for the full interactive version</i>]</li>
  <li> <i>Each bubble will show the model, orders, range in nautical miles and price in $1,000,000</i></li>
  </ul>
  
  <br><i><b>See the following seating capacities:</i></b></br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119828090-2f281b80-bf3d-11eb-91be-659591d0a5db.png></br>
  <ul>
  <li>Blue represents Boeing aircraft, and silver for Airbus aircraft</li></ul>
  
  <br><b><i>See the following plot for Max Takeoff Weight and Takeoff Distance:</b></i></br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119828915-ffc5de80-bf3d-11eb-9927-ba6f795de5e5.png></br>
  <ul>
  <li>A large spread between takeoff performances</li></ul>
    
  <br><i><b>See the maximum cruising altitude:</i></b></br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119829300-72cf5500-bf3e-11eb-8c6b-8962a8efbc2d.png></br>
  <ul>
  <li>Boeing airplanes perform better in the air</li></ul>
  
  <br><b><i>Let's examine delivery rates:</b></i></br>
  
```python
#Delivery rate for short-range aircraft 
#
#Implemented through a linked list

class node:
    def __init__(self, data = None):
        self.data = data 
        self.next = None 

class sra:
    def __init__(self):
        self.head = None 

    def showdeliveryrate(self):
        if self.head == None:
            return None

        rates = [str(round(((1172/3857) * 100), 2)) + '%', str(round(((481/3437) * 100), 2)) + '%', str(round(((435/(2135 + 234)) * 100), 2)) + '%']

        traverse = self.head 
        while traverse != None:
            for i in range(3):
                print(traverse.data + rates[i])
                traverse = traverse.next

smallplanes = sra()

smallplanes.head = node('A320neo -> ')
smallplanes1 = node('A321neo -> ')
smallplanes2 = node('737 MAX -> ')

smallplanes.head.next = smallplanes1 
smallplanes1.next = smallplanes2 

smallplanes.showdeliveryrate()
```
<br>
<img src = https://user-images.githubusercontent.com/65270652/119829783-f7ba6e80-bf3e-11eb-8450-a157e32a44c0.png></br>

<br>__Final Decision__</br>

Based on the data we have collected and using the visualizations generated:

- We will recommend the <b>A320neo</b> and the <b>737 MAX 8</b>

The expectation is that for short-range aircraft, they will only be used for domestic flights within the United States. Flight range from LAX to the East coast is at most 2,500 nautical miles so we simply won't need the bigger, more expensive A321neo. Seating is very similar across the A320neo, 737 MAX 8 and 737 MAX 9 airplanes so that wouldn't have much impact. The A320neo is a very popular aircraft based on orders and delivery rate so that was also taken into account. Further, we noticed that Boeing airplanes can reach higher cruising altitudes (increases fuel efficiency) so we decided this would be beneficial. Also, we took into account that Boeing factories are located within the US and purchasing from a US company may have political, economical and goodwill benefits. Selecting the cheapest airplane from both Boeing and Airbus also addresses diversity within the fleet and the airline's needs. Hence, the decision to go with the MAX and the neo.

<br>
<img src = https://user-images.githubusercontent.com/65270652/119915211-5e727300-bfa5-11eb-8b32-8cb42586d911.png></br>

<br>
<img src = https://user-images.githubusercontent.com/65270652/119915321-98dc1000-bfa5-11eb-8150-48876d4cd831.png></br>

<br>
<sub>Credits: Airbus' website, Boeing's website</sub></br>

<br></br>

</details>

<details>
<summary>Long Range Aircraft</summary>
  <br><b><i>See the following price chart:</b></i></br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119824263-10278a80-bf39-11eb-851c-5c8208524cba.png></br>
<ul>
  <li>We find that Boeing on average is $88.35 million more expensive than Airbus</li></ul>

<br><b><i>See the following range and order numbers interactive graph:</b></i></br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119831205-62b87500-bf40-11eb-8899-7cf51c3938f4.png></br>
<ul>
  <li>[<i>[nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb)for the interactive version</i>]</li>
  <li><i>Each bubble will show the model, orders, range in nautical miles and price in $1,000,000</i></li></ul>

<br><b><i>See the following seating capacities:</b></i></br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119831591-c773cf80-bf40-11eb-9b1c-6e36bcc3ad88.png></br>
<ul>
  <li>Blue represents Boeing aircraft, and silver for Airbus aircraft</li></ul>

<br><b><i>See the following plot for Max Takeoff Weight and Takeoff Distance:</b></i></br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119832136-423cea80-bf41-11eb-9d58-f4f0ed89471b.png></br>
<ul>
  <li> A consistent spread between takeoff performances </li></ul>

<br><b><i>See the maximum cruising altitude:</b></i></br>
<br>
<img src = https://user-images.githubusercontent.com/65270652/119832416-803a0e80-bf41-11eb-84b1-c679d0a9da1a.png></br>
<ul>
  <li>Boeing airplanes perform a bit better in the air</li></ul>

<br><b><i>Let's examine delivery rates:</b></i></br>

```python
#Delivery rate for long-range aircraft 
#
#Implemented through a linked list

class node:
    def __init__(self, data = None):
        self.data = data 
        self.next = None 

class sra:
    def __init__(self):
        self.head = None 

    def showdeliveryrate(self):
        if self.head == None:
            return None

        rates = [str(round(((355/745) * 100), 2)) + '%', str(round(((53/168) * 100), 2)) + '%', str(round(((47/155) * 100), 2)) + '%', str(round(((0/312) * 100), 2)) + '%']

        traverse = self.head 
        while traverse != None:
            for i in range(4):
                print(traverse.data + rates[i])
                traverse = traverse.next

smallplanes = sra()

smallplanes.head = node('A350-900 -> ')
smallplanes1 = node('A350-1000 -> ')
smallplanes2 = node('747-8i -> ')
smallplanes3 = node('777-9X -> ')

smallplanes.head.next = smallplanes1 
smallplanes1.next = smallplanes2
smallplanes2.next = smallplanes3

smallplanes.showdeliveryrate()

```
<br>
<img src = https://user-images.githubusercontent.com/65270652/119832900-f8a0cf80-bf41-11eb-8f63-e6ad4b8b27f4.png></br>

<br>__Final Decision__</br>

Based on the data we have collected and using the visualizations generated:

- We will recommend the <b>A350-1000</b> and the <b>747-8i</b>

The expectation is that long-range aircraft only service international flights. From the price chart, we notice that Boeing is much more expensive on average than Airbus. We decide that the ranges and takeoff performance for all four airplanes are sufficient for potential international routes. Also, LAX's runway length is also sufficient to operate all four airplanes. Seating wise, the 747-8i's capacity is a very attractive and we will recommend to send the 747-8i for the most popular international destinations. Performance in the air with the 747-8i is excellent with its 43,000ft maximum cruising altitude (great of fuel efficiency). Further, we would like to continue the relationship with Boeing as mentioned before. We simply did not select the 777-9X based off no deliveries as the airplane is still in production. The reason we decided to go with the A350-1000 over the -900 is range and capability to hold more weight (or cargo). We would like the airline to keep the possibility of ultra-long haul routes and we believe this will mitigate the need to purchase entirely new aircraft because of the -1000's already extremely long range capability. Choosing from both Airbus and Boeing will allow pilots to easily transition from the A320neo to the A350-1000 and the 737 MAX 8 to the 747-8i when the time comes, reducing training costs. Hence, the decision to go with the 747 and the -1000.

<br>
<img src = https://user-images.githubusercontent.com/65270652/119916861-ab0b7d80-bfa8-11eb-91fc-9e7bf85c8a3c.png></br>

<br>
<img src = https://user-images.githubusercontent.com/65270652/119916889-bc548a00-bfa8-11eb-9984-1381cb6ad98f.png></br>

<br>
<sub>Credits: Airbus' website, Boeing's website</sub></br>

<br></br>

</details>


<b>Routes</b>
------
Now, for potential routes. All routes will depart from LAX and return to LAX. We examined the top destinations of flights from LAX for both domestic and international. We will use the visualisations and other information to determine potential routes. See [<i>main.ipynb</i>].

<details>
  <summary>Domestic Routes</summary>
  <br>
  <i>We highly recommend viewing [nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb) for the full interaction version of the following graphs and plots.</i></br>
  <br>The bubbles in the following map of the United States show the top destinations within the US from LAX</br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119919875-b19cf380-bfae-11eb-9edf-6e38f8920854.png></br>
  <ul>
  <li>We see that destinations are somewhat evenly distributed across the country</li>
  <li>Each bubble displays the city of arrival, time of flight in hours (TOF), latitude, longitude and passengers</li>
  <li>A bubble has been generated for LAX just for reference</li>
  <li>[<i>[nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb)for the full interactive version (recommended)</i>]</li></ul>
  <i><b>See the bar plot:</i></b>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119920584-eb222e80-bfaf-11eb-88fb-9194fc329f75.png></br>
  <ul>
  <li>As expected, major tourist destinations such as New York, Las Vegas and San Francisco are top destinations</li></ul>
  <b><i>Using this, we generate the following:</b></i>
  <br></br>
  
  Destination | Time of Flight | Frequency | Aircraft
  ------|------|------|------
  New York | 5.19 | 4 | A320neo
  San Francisco | 1.13 | 6 | 737 MAX 8 
  Las Vegas | 0.94 | 6 | 737 MAX 8 
  Chicago | 3.8 | 4 | A320neo
  Seattle | 2.3 | 3 | 737 MAX 8
  Dallas | 2.83 | 4 | 737 MAX 8 
  Denver | 2.12 | 3 | 737 MAX 8 
  Honolulu | 5.33 | 3 | A320neo
  Atlanta | 4.12 | 4 | A320neo
  Phoenix | 1.2 | 3 | 737 MAX 8 
  
  <ul>
  <li>NOTE: Time of Flight is in hours</li>
  <li>All destinations include return flights</li>
  <li>A320neo <i>numbers</i> = 15 + [3 (standby aircraft)]= 18</li>
  <li>737 MAX 8 <i>numbers</i> = 25 + [4 (standby aircraft)] = 29</li>
  
  <br>We recommend the airline operating the following flights every day of the week, but frequency should be slightly different each week to free-up aircraft for return flights, maintanence etc.</br>
  
</details>

<details>
  <summary>International Routes</summary>
  <br>
  <i>We highly recommend viewing [nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb) for the full interaction version of the following graphs and plots.</i></br>
  <br>The bubbles in the following map of the Earth show the top international destinations from LAX</br>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119922879-0abb5600-bfb4-11eb-95ed-02c4094f9785.png></br>
  <ul>
  <li>We see that destinations are primarily distributed across the Northern Hemisphere</li>
  <li>Each bubble displays the city of arrival, distance, latitude, longitude and passengers</li>
  <li>[<i>[nbviewer_airlineanalysis](https://nbviewer.jupyter.org/github/darrenlxu/airline-analysis/blob/main/main.ipynb) for the full interactive version (recommended)</i>]</li></ul>
  <i><b>See the bar plot:</i></b>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119922950-2a527e80-bfb4-11eb-8fc4-2a7f5648fa6c.png></br>
  <ul>
  <li>Majority of international destinations belong in North America and Asia</li></ul>
  <b><i>Using this, we generate the following:</b></i>
  <br></br>
  
  Destination | Time of Flight | Frequency | Aircraft
  ------|------|------|------
  London | 10.82 | 2 | 747-8i
  Seoul | 11.85 | 1 | 747-8i
  Sydney | 14.67 | 1 | A350-1000 
  Hong Kong | 3.8 | 1 | A350-1000
  Paris | 11.23 | 1 | 747-8i
  Toronto | 4.62 | 1 | A350-1000
  Mexico City | 3.52 | 3 | A320neo
  
  <ul>
  <li>NOTE: Time of Flight is in hours</li>
  <li>All destinations include return flights</li>
  <li>747-8i <i>numbers</i> = 4 + [0 (standby aircraft)]= 4</li>
  <li>A350-1000 <i>numbers</i> = 3 + [2 (standby aircraft)] = 5</li>
  <li>A320neo <i>numbers</i> = 3 + [0 (standby aircraft)] = 3</li>
  <li><i>We will use the A320neo for Mexico flights, because it will be too expensive to run frequent long-range aircraft on this route</i></li></ul>

<br>We recommend the airline operating the following flights 4-5-6 days of the week (depending on peak seasons), but frequency should be slightly different each week to free-up aircraft for return flights, maintanence etc.</br>

</details>

<b>Conclusion</b>
------

<details>
  <summary>Cost Report</summary>
  All prices or costs addressed in this project is in $USD (US dollars)
  <br></br>
  
  Model | Price | Quantity | Cost
  ------|------|------|------
  A320neo | $110.6 million | 21 | $2.32 billion
  737 MAX 8 | $124.6 million | 29 | $3.61 billion
  A350-1000 | $366.5 million | 5 | $1.83 billion
  747-8i | $419.4 million | 4 | $1.67 billion
  
  <ul>
    <li> Total cost = $9.43 billion </li></ul>
</details>

Throughout this project we have found the airline's short-range aircraft as well as long-range aircraft. We have also established a home base/hub for the airline. We also recommended potential routes for the airline to operate on a domestic and international level. We used data analysis, scraping and visualization techniques to reach this, along with addressing the airline's criteria and requirements. 

<br><b><i>See basic summary:</i></b></br>
[summary.pdf](https://github.com/darrenlxu/Airline-Analysis-Project/files/6558126/summary.pdf)

<b>Other</b>
------

<details>
  <summary>Potential Improvements</summary>
  <sub>To further improve this project, we can perform deeper analysis and create more extensive models. We can also address factors and criteria such as potential ticket prices, estimated performance and a full competition analysis. More of this may be added in the future to best improve the Airline Analysis Project.</sup>
</details>









