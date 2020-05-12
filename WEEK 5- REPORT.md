# Capstone Project - The Battle of the Neighborhoods
# Applied Data Science Capstone by IBM/Coursera

## PROJECT TITLE -  RUNNERS PARADISE

### Introduction: Business Problem ¶
In this project we will try to find an optimal location for a Running application. Specifically, this report will be targeted to runners interested in locating a optimal place to live for running in United Kingdom.

Since there are lots of parks in United Kingdom we will try to select few popular place locations in United Kingdon that are popular with runners. We are interested in a locality whether the runner is best close to the park for running. We  prefer staying in a locations as close to parks .

We will use our data science powers to generate a few most promising neighborhoods based on this criteria. Advantages of each area will then be clearly expressed so that best possible final location can be chosen by runners

## DATA SECTION
We will use the FourSquare API to collect data about locations of the parks in London. We are selecting 5 major location in United Kingdom, the locations are London, Oxford, Cambridge,Edinburgh and Windsor. These are the most prefered running location in the United Kingdom.

# Methodology
The main objective here is to asses which city in United Kingdom would have the closest park for the runner. I used the Four Square API . I used the near query to get park in the cities. Also, I use the CategoryID to set it to show only Park. 

An Example of my requests:

https://developer.foursquare.com/docs/build-with-foursquare/categories/

4bf58dd8d48988d163941735 is the Id of the Park Category. Also, Foursquare limits us to maximum of 100 venues per query.

Moreover, I repeated this request for the 5 studied cities and got their top 100 venues. 
The popular running location is saved in Runners_Paradise.csv

Next, to get an indicator of the density of all the identified parks in United Kingdom, I calculated a center coordinate of the venues to get the mean longitude and latitude values. Then I calculated the mean of the Euclidean distance from each venue to the mean coordinates. That was my indicator; mean distance to the mean coordinate.

## Results
For our initial visual inspection we see that all have locations have more then 10 plus parks . The following here are the pictures of the geoplot generated with folium:

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

Upon First inspection we see that London and Edinburg have more parks . In the next phase we Calculate the Mean coordinate and the mean distance to mean coordinate(MDMC). We represent the mean coordinate with a big green circle and distances with green lines

#### Mean Distance from Mean coordinates

London,UK Mean Distance from Mean coordinates - 0.10211696344549116
<br>
Oxford,UK Mean Distance from Mean coordinates - 0.023904481323610886
<br>
Cambridge,UK Mean Distance from Mean coordinates - 0.026315457669379753
<br>
Edinburgh,UK Mean Distance from Mean coordinates - 0.03923226547454313
<br>
Windsor,UK Mean Distance from Mean coordinates - 0.04309900140627803

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

#### RESULTS RANKED IN ORDER OF MEAN DISTANCE FROM MEAN COORDINATES:


Oxford,UK Mean Distance from Mean coordinates - 0.023904481323610886
<br>
Cambridge,UK Mean Distance from Mean coordinates - 0.026315457669379753
<br>
Edinburgh,UK Mean Distance from Mean coordinates - 0.03923226547454313
<br>
Windsor,UK Mean Distance from Mean coordinates - 0.04309900140627803
<br>
London,UK Mean Distance from Mean coordinates - 0.10211696344549116

### Discussion
Oxford and Cambridge is pretty close, what if we remove one outliners from Cambridge to see if Cambridge comes close to Oxford. 
The new MDMC for Cambridge was: 0.023113437334794786, and now Cambridge is on the first place.

As FourSquare is limited , more analysis could be done.

### Conclusion
Now there is no doubt that Oxford is the best place to run with many running parks close by closely followed by Cambridge. A running ethusisast opt for Oxford, Cambrisge, Edinburh, Wndsor and lastly London if he is passionate to run all these park.

Also, we would recommend that our runner book a place of stay closer to the mean coordinate.








