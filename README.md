# Data Alchemy - ADA Project

# A simple statistic

Let's start this story with a single very simple statistic : 
- "The number of climate-related disasters has **tripled in the last 30 years**", *Oxfam International, 2020*

This drastic increase in the frequency but also the severity of natural climate-related disasters (floods, typhoons, wildfires, etc.) arises at the same time as the reality that is climate change and its effects start to set in. 

These natural disasters are maybe the most concrete repercussions yet of climate change, and we believe that concrete consequences are far more likely to get discussions and change going.

## Question

Thus, we wonder whether an increase in the severity of natural disasters leads to a broader discussion about climate change and its dangers ? </br>
And if it does, is it the same everywhere, or are there geographical discrepencies in the effect natural disasters have on the talk about climate change ?


# Do natural disasters drive discussions about climate change ? 

Generally no, some effects are seen but they are very small (p-value ?)
But we need to dive deeper and we see that there are 3 conditions for a natural disaster to cause talk about climate change.
- Type
- Location
- Severity / intensity

# We pick specific storms and heat waves, why ?

- articles with sources linking those events to climate change

Selected events based on the apparent link in Quotebank between talk about the event and about climate change. Visual inspection of the plots + Google trends to ensure the talks are in fact due to the event and not other climate related activities (conference, strike, speech, etc.)

In the following sections, a comparison is made between discussion around the topic of climate change (climate data) and a general type of natural disaster (disaster data), either storms (e.g., hurricanes, typhoons, ...) or heat waves. One can be tempted to conclude that an observed increase in both would mean that the natural disaster caused an increase in discussion around climate change, however many factors can come into play. Real world factors could be climate summits and strikes or the release of a major climate report. On a more technical level though, the overall amount of quotes in the Quotebank dataset can fluctuate over time, meaning that an observed increase in the quotes related to climate change might be due to an increase in the overall number of quotes retrieved during that time window, rather than being due to a actual increase in quotes in the real world.

We attempt to account for the fluctuation in overall quotes retrieved over a time period by picking a common english word ('especially') which is broad enough to appear in many different contexts but not so broad that a subset of the Quotebank dataset which contains this token is too big to load into memory. The idea is that this subset of Quotebank (general data) is able to represent the general evolution of the number of quotes throughout a given time frame.

By including the general data, it can, for certain years, become blatantly obvious that spikes in the climate and disaster data happen simply because there is an increase in overall number of quotes because the evolution of all three quote occurrences follow an identical trend. The goal is to identify the parts of the climate and disaster data which increase for a reason other than there simply being a sudden increase in overall number quotes by leveraging the general data. 

In order to reach the aforementioned goal, we define a method for extracting so-called 'relevant spikes'. These are spikes in the climate and disaster related data which go against the trend of the general data, or surpass it by an adjustable parameter. For example, if the general data stays stable over the course of a few weeks, but the climate data experiences a sharp increase, we could decide to identify as a relevant spike. Whether or not the spike is due to a particular disaster is irrelevant at this stage, we simply want to identify spikes in the data which are likely caused by some effect from the real world.

The task of determining if a (supposedly) real world increase in climate data is related to a real world increase in disaster data is part of what the next sections try to tackle. Through a series of comparisons between events of a given disaster type occurring in different places, we try to determine the main factors that can create a causal relationship between the disaster (and discussion around it) and discussion around climate change. The hypotheses developed try to keep in mind that Quotebank was extracted from news articles in English, meaning that most quotes will originate from Western media and countries such as the United States, the United Kingdom, Canada and Australia. Of course, there are news English-speaking news outlets in many different countries, for example India, but the balance is uneven. 

To select the individual disasters we select those that correspond to relevant spikes in the disaster data. We verify these spikes by looking for a similar pattern in Google Trends. In addition to verifying that the trends match, this tool will also often produce the specific natural disaster that occurred by checking the related queries. Additionally, the specific natural disasters and their properties can be verified using Wikipedia, notably, we made use of the [List of heat waves](https://en.wikipedia.org/wiki/List_of_heat_waves#2015) article. When selecting the disasters to compare, we look for the ones that cause an increase in climate discussion and those that don't. The goal of the analysis is to determine why two similar disasters could produce such different results in the climate data.

## Description of the events

The first events we will consider are both heat waves from the year 2015. 

INDIA : <br>
During the month of may 2015, a severe [heat wave](https://en.wikipedia.org/wiki/2015_Indian_heat_wave) struck India, with recorded temperatures nearing 50°C. Although the number of people affected is not well known, the heat wave caused at least 2500 casualties in multiple regions, making this heat wave the most deadly since 1979.

EUROPE : <br>
Unusual [heat](https://www.worldweatherattribution.org/european-heat-wave-july-2015/) [waves](https://www.washingtonpost.com/outlook/2019/07/26/europes-killer-heat-waves-are-new-norm-death-rates-shouldnt-be) occurred in Europe from late June to mid-September 2015, with over 40°C measured locally, the highest temperatures measured since the beginning of the weather records in certain parts of Europe. The Maghreb Mediterranean coast, south-west, central and south-east Europe were particularly hard hit. Statistically in France, around 3300 deaths were attributed to this series of heat waves.


## Inspection of the data

Regarding the heat wave in India, we can notice a relevant spike at the end of April due to a slight increase in heat wave quotes which is stronger than that of the general data. There is no corresponding relevant spike in the climate data, on the contrary, there is a sharp decrease. The spike in heat wave data towards the end of August corresponds mainly to heat waves that affected Europe. There is a corresponding relevant spike that can be observed in the climate data.

These results lead us to make the following hypotheses. Firstly, that a heat wave occurring in India doesn't attract the same level of attention (based on the spike magnitudes) as heat waves in Europe because Western media tends to have a stronger reaction to something when it happens geographically close to it. Secondly, the discussion around climate change might not increase as a result of a heat wave in India because they are more common there than in Europe. According to WHO: ["In India  Heat waves typically occur from March to June"](https://www.who.int/india/heat-waves). 

Combining these two together, we can conclude that, in regards to heat waves, when this type of disaster happens in a developing country, such as [India](https://www.worlddata.info/developing-countries.php), Western media's reaction is non negligible, but there is no apparent increase in climate discussion. When, on the other hand, a heat wave takes place in Europe, it can generate climate discussion because the event is happening where the Western media is based and so there is a stronger need to find solutions to mitigate future similar events. When a heat wave takes place in India, the effects are not directly experienced by the Western media.

![alt text](images/2015_heat_wave.png)
![alt text](images/2015_heat_wave_peaks.png)


## Description of the events

In the year 2016, being the warmest year on record, we will now compare the reactions to two heat waves in 2016, in the United States and India.

USA : <br>
This [heat wave](https://www.huffpost.com/entry/record-heat-wildfires-west-us_n_57678bb4e4b015db1bc9be59?section=) [in the United States](https://earthobservatory.nasa.gov/images/88547/extreme-heat-for-an-extreme-year) in July caused record temperatures in the Southwest, with "red flag warnings" for extreme fire conditions in effect across southern portions of California. <br>
During the peak of the heatwave, about 124 million people were under extreme heat warnings in the United States, according to the National Weather Service. 

INDIA : <br>
The 2016 [Indian heat wave](https://en.wikipedia.org/wiki/2016_Indian_heat_wave) was a major heat wave in April and May of that year. A national record high temperature of 51.0 °C was set in the town of Phalodi, in the state of Rajasthan. Over 160 people died with 330 million affected to some degree. There were also water shortages with drought worsening the impact of the heat wave.

These two heatwaves seem very comparable in their effects and consequences, with both affecting at least a hundred million people. However, these comparable real consequences did not lead to a comparable effect on the discussion around climate change.

## Inspection of the data

## Description of the events

INDIA : <br>
[Cyclone Titli](https://en.wikipedia.org/wiki/Cyclone_Titli) caused extensive damage to Eastern India and Bangladesh at the start of October 2018. Killing at least 85 people, it also caused nearly one billion dollars in damages during the single day it was on land.

USA : <br>
[Hurricane Florence](https://en.wikipedia.org/wiki/Hurricane_Florence) was a powerful hurricane that caused catastrophic damage in the Carolinas in September 2018. 
Overall, the storm caused $24.23 billion in damage and 54 deaths.

Although these events are not of the same scale, we did notice that the talk surrounding them was significant enough to warrant a study. 
Also, Cyclone Titli occured around the same time as an IPCC special report on the impacts of global warming came out, making this study particularly difficult and interesting.

## Inspection of the data

## Description of the events

2019 Dorian end of august in Bahamas, close to US but no contact – No increase in climate change talk
Typhoon Hagibis 10 October 2019 in Japan – Relatively important increase in talk about climate change (drop in baseline number of quotes)

BAHAMAS : <br>
In September of 2019 during hurricane season, [Hurricane Dorian](https://en.wikipedia.org/wiki/Hurricane_Dorian) became the worst natural disaster in The Bahamas' recorded history, with 74 deaths, 245 missing and over 3 billion dollars in damages.

JAPAN : <br>
At the start of October 2019, the [Typhoon Hagibis](https://en.wikipedia.org/wiki/Typhoon_Hagibis) caused widespread destruction in Japan. It was the strongest typhoon to strike mainland Japan in decades, and one of the largest typhoons ever recorded. Japan's Fire and Disaster Management Agency stated that at least 98 people have been confirmed dead, 7 people are missing, with 346 people injured by the storm. More than 270,000 households lost power across the country. The total damages were estimated at over 15 billion dollars.

Although the typhoon in Japan caused more monetary damages, that is to be expected considering the size of the country. 

## Inspection of the data



### General conclusions about data: just because a natural disaster gets a lot of attention does not necessarily mean that it will drive climate change discussion. There are several reasons for this. 
One is that a certain type of natural disaster might be common in parts of the world, meaning that quotes pertaining to governments advising the population to stay hydrated for example will occur frequently, but no discussion around climate change will be started because of how common the event is. 
Another is that a natural disaster might not be devastating enough to catch the attention of major public figures.



# Synthesis

Map of the world showing that disasters in developping countries cause less talk about climate change. (India, Bahamas)

Disasters in developped countries cause more talk about climate change.
(Europe, USA, Japan)





We should keep in mind that we only have access to english quotes from Quotebank. Therefore, when comparing the impact of an indian heat wave on the global talk about climate change, we really look at the impact that heatwave has on the english-speaking world. All these studies would be completed by taking into account the talk about climate change generated all over the world in different languages. 