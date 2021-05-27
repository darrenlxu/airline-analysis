# Airline Analysis Project


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

First, we will examine and clean/tidy our data sets. Next with the now relevant/short-listed data, we began to collate our analysis, finalizing our results and final decisions whilst simultaneously meeting the airline's criteria.

<b>Cleaning & Short Listing Data</b>
------
Multiple data sets were loaded into MySQL and the process of cleaning and short listing data was done using Python's MySQL Connector library. We addressed multiple criteria to cut down to the final best remaining planes. From this, we produced finalists in aircraft choice and airport choice [<i>see sqlqueries.ipynb</i>]. Most airlines operate both short-range and long-range aircraft so we have decided to do the same. Only two aerospace manufacturers are in contention, Airbus and Boeing.

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
- The green line represents the predicted values (extrapolation)
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
  - The green line represents the predicted values (extrapolation)
</details>
  
<b>Determining Aircraft</b>
------
To help determine exactly which of the airplanes to select, multiple charts and graphs have been produced to assist, [<i>see main.ipynb</i>].

<details>
  <summary>Short Range Aircraft</summary>
  <p>See the following price chart:</p>
  <br>
  <img src = https://user-images.githubusercontent.com/65270652/119823261-f0dc2d80-bf37-11eb-9d92-f7637b4935c6.png></br>
  <p>
  - We find that Boeing on average is $6.75 million more expensive than Airbus </p>
  
  
  
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
</details>

<details>
  <summary>Long Range Aircraft</summary>
  <p>See the following price chart:</p>
  <img src = https://user-images.githubusercontent.com/65270652/119824263-10278a80-bf39-11eb-851c-5c8208524cba.png>
  - We find that Boeing on average is $88.35 million more expensive than Airbus
</details>



<b>Routes</b>
------

<details>
  <summary>Domestic Routes</summary>
</details>

<details>
  <summary>International Routes</summary>
</details>


<b>Conclusion</b>
------


<b>Other</b>
------








