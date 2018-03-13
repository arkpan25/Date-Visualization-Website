# Date-Visualization-Website
Caffeine Consumption of the World
1. Data
1.1 Sources
Caffeinedrink.js, countrydata.js and map.js are the three data file we used for our
project. Caffeinedrink.js describes caffeine content of 60 kinds of drinks, all data in this
file comes from Caffeine Content of Drinks.1 The other file countrydata.js describes the
coffee, tea and soda consumption and corresponding caffeine consumption from the
three kinds of drinks around the world which comes from three sources, List of countries
by coffee consumption per capita,2 List of countries by tea consumption per capita 3 and
Americans Drink More Soda Than Anyone Else.4 Although we have coffee, tea and
consumption from three links above, we still calculate the average caffeine content in
those drinks from link1 and compute the caffeine content. Map.js used for mapping a
country to its country code and continent, we got this data from getCountries() 5 which is
a cool web provides a lot of data about countries. In the last part, how much caffeine is
okay to have, we use the data from Caffeine Safe Limits: Determine Your Safe Daily
Dose.6
1.2 Variables
In Caffeinedrink.js, one object represents the caffeine content for a specific kind of drink
and there are five variables in one object.
{
"Type": "Coffee",
"Drink": "Nescafe Ice Java",
"Volume_floz": 0.85,
"Caffeine_mg": 100,
"caffeinemg/floz": 117.6
}
Type is what kind of this drink, coffee, tea or soda. Drink is the name of this drink.
Volume_floz represents the common volume of this kind of drink using floz.
Caffeine_mg is the caffeine content in this kind of drink. Caffeinemg/floz represents the
caffeine content per floz in this drink which will be shown in the bar chart.
In countrydata.js, one object represents the caffeine consumption from different kind of
drinks in specific country and there are eight variables in an object.
{
"Country": "Albania",
"annualTea": 0.013,
"annualSoda": 0,
"annualCoffee": 1.6,
"caffeineTea": 0.52,
"caffeineSoda": 0,
"caffeineCoffee": 65.6,
"totalcaffeine": 66.12
}
Country represents the country name. AnnualTea, annualSoda and annualCoffee are
the annual tea, soda and coffee consumption of one person in this country by kg.CaffeineTea, caffeineSoda and caffeineCoffee represent the daily caffeine consumption
from tea, soda and coffee of one person in this country by mg. Totalcaffeine is the sum
of daily caffeine consumption from tea, soda and coffee which can be seen as the total
caffeine consumption from drinks.
In map.js, there are three variables in an object provides country code and continent
information for each country as following format.
{
"countryCode": "AD",
"countryName": "Andorra",
"continent": "EU"
}
1.3 Reformatting
A number of edits and reformatting changes had to be made for our purposes. Firstly,
we import all the data into two csv file. Secondly, we make some changes on the two
files through Microsoft Excel. For caffeinedrink, we only manually add variable “Type”
for every drink. For countrydata, we do more calculation on the data we get from the
resource. For instance, we only have the annual consumption of coffee, tea and soda
per person, we calculate the average caffeine content in these drinks and compute the
daily caffeine consumption and daily total caffeine consumption per person. Last, we
convert the csv file to js file through js converter.
2. Visualizations
2.1 Bubble chart
We tried world map in the initial design but we found it’s really difficult to see a large
amount of countries clearly, so we decided to use bubble charts instead. Thanks for the
inspiration from Fun with D3js: Data Visualization Eye Candy with Streaming JSON.7
This is the first visualization when user load this webpage, we want to represent an
overview about caffeine consumption among each country. We use bubble size to
represent the caffeine consumption and colored each bubble a color according to its
continent so that user can learn both caffeine consumption and continent information
from the bubble chart. We add seven buttons to provide seven filter methods to show
caffeine consumption in specific continent or all of the countries. Each bubble can be
clicked to create a tooltip which can display the country’s name and its consumption.
We also use basic transition() and duration() method to add animation to make the
bubble chart more lively.
2.2 Liquid Bubbles
This part of the project represents the total % of liquid consumed per type (coffee, tea
and soda) by a selected country. We wanted to show the story behind what people were
drinking in addition to the caffeine. We wanted to give an overview of what a country
was doing and what they drank at quick glance. This chart was created using the liquid
bubbles8 d3 code found on the d3 examples page. Joe modified this to use gradient fills
instead of solid fills to give a more interesting and liquid look. Coffee was given a
darker color of coffee, tea was given an orange to yellow opaque color to reflect tea and finally soda was given a more caramel to dark brown color so that it still looked like
soda, but didn’t conflict with the color of coffee.
2.3 Bar Chart
This part represents the caffeine content of top 20 drinks in 400mL for coffee, tea or
soda. User could learn the caffeine content for specific kind of drinks through the bar
chart and find out the drink suitable for him/her. When user load this html file and would
defaultly shown the information about coffee and would change when user click the
buttons. We also use transition() to add animation for bar chart and add click event to
show a tooltip describe the drink’s name and caffeine content represented by this bar.
2.4 Caffeine Consumption Quiz
We use four dropdown menu, four input components and two buttons to construct the
frame of this little quiz which helps user learn whether their caffeine consumption is
suitable for his/her condition. User can choose their basic upper limit of caffeine
consumption according to his/her age and health condition. The default attribute for
each user is a healthy adult and we could calculate a more suitable caffeine content if
user input his/her weight. The following dropdown menu contains 60 kinds of drinks (we
filter out the drinks which have too little caffeine), user can choose the drinks and
number as their daily consumption. The result and our advice will be shown when user
click the calculate button and the previous record will be deleted when user click clear
button. A modal was put in to present the findings, which made it easier on mobile
devices for users to see results quickly but also dismiss them quickly.
2.5 Media Query
Bootstrap (getbootstrap.com) was used for responsive DIVS and http://verge.airve.com/
was used to detect screen size and get new width for SVGs. We divide common
devices to six groups which have their own constraints. As a result, our project could be
accustomed to cell phone and tablet from width 320px to 1279px(e.g. iPhone 6 to
iPhone 7 Plus, iPad Mini, iPad, Galaxy and Nexus).
3. Story
The story this data tells is the caffeine and drink consumption around the world. It starts
by showing you the top consuming countries based on caffeine in the world, and invites
you to click on the circles to find out what country it is. Once you click it then shows you
in that country what people are actually consuming (coffee, tea, soda). One surprising
thing you see when clicking on the bubbles and seeing the consumption of drinks is
sometimes how one sided a drink is based on continent and country. Further
exploration was to show the caffeine content of popular drinks in the different
categories. The amount of caffeine in some of the coffee drinks are surprisingly much
larger than the others. Finally, we wanted to show people what the consumption limits
are. Often people have a preconceived notion of how much caffeine is bad for you (Joe
for instance drinks Red Bull and people always say one red bull is terrible for you it has
so much caffeine!) but through this little interactive section, you can put in your weight
and see if the amount of caffeine you are drinking in a day is okay or too much.Overall the story is telling about caffeine consumption and looking how people get it and
how to be healthy while drinking it.
Visually we made the flow of the page to take them through the story. First we used
bright, colorful circles that invited you visually to click on them. With it right next to the
labels of the colors of the continents, users can quickly understand what to do. Next, the
liquid circles were placed next to the circle chart in larger screens so that users could
click on circles and see direct change in the liquid circles. On a smaller screen the large
circle chart will be the first layer with the liquid circles below it. They are small enough
that a user could see both on screen at the same time.
Next a new layer is started in which you can see caffeine content in each of the different
categories. This is set onto a different colored background to give it separation from the
previous section., but uses similar colors in the buttons to tie it to the entire design. You
can tell that it is a part of the information, but it is a new level of information.
Finally the last part is setup with instructions on the left and input fields on the right
which is how users would read a site. Input fields are easy to tab through and followed
by a calculate button. The calculate button is a new color to draw attention to it.
1http://www.caffeineinformer.com/the-caffeine-database
2https://www.google.com/fusiontables/DataSource?docid=1Cfn6nSe21acP0xJIO1T1x0wohqfMYCQyJjbqdk#rows:id=1
3https://en.wikipedia.org/wiki/List_of_countries_by_tea_consumption_per_capita
4http://www.slate.com/articles/health_and_science/map_of_the_week/2012/07/ma
p_of_soda_consumption_americans_drink_more_than_anyone_else_.html
5http://peric.github.io/GetCountries
6http://www.caffeineinformer.com/caffeine-safe-limits
7https://www.pubnub.com/blog/2014-10-08-fun-with-d3js-data-visualization-eyecandy-with-streaming-json
8http://bl.ocks.org/brattonc/5e5ce9beee483220e2f6