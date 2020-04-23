# SUSTAINABLE CAMPUS PROJECT: FINAL REPORT
## 94802-A: Geographic Information Systems, Spring 2019

### Introduction

*Background*

With the Trump Administration’s June 2017 announcement that it would withdraw from the Paris Climate Accord, the responsibility for achieving the necessary reductions in greenhouse gas (GHG) emissions to prevent a 2°C rise in average global temperatures is increasingly falling onto the shoulders of regular citizens. 

Collective action at this scale, however, is often limited in its impact due to the lack of appropriate institutional infrastructure. Many of the tools best tailored to this model of social organization (e.g., GitHub, version control software, etc.) require high levels of technical literacy and savvy to exploit at their full potential. 

More visual, user-friendly tools like ArcGIS and other mapping software provide a more viable entryway to leveraging the collective action potential of modern digital media technologies. A prime example of this is the SMS-based mapping app, Ushahidi. Since its development in 2008, this simple open source tool has been successfully adapted to address an exceedingly wide variety of purposes and contexts. 

*Problem Statement*

A joint study conducted in the Fall semester of 2017 by students from the Department of Engineering and Public Policy (EPP) and the Department of Social and Decision Sciences (SDS) at Carnegie Mellon University (CMU) sought to analyze options for a commitment by CMU to reduce its GHG emissions as if it were a party to the Paris Agreement. The main findings of this report were subsequently used by the Ad Hoc Committee on Sustainability, formed by the Senate Executive Committee in May 2018, “to provide advice to the Faculty Senate on the need for further university action related to sustainability at the university.” In the latest resolution on this subject, which was passed unanimously in the April 2 Faculty Senate Meeting, the Central Administration was committed to delivering a decision on the recommendations no later than December 31, 2019.

The gears of government, however, turn slowly. This project seeks to determine the extent to which equipping CMU students and other key stakeholders with accurate, up-to-date GHG emissions data for all CMU buildings and installations, along with a to be determined suite of analytical tools for rapid translation of data into actionable insights, might facilitate collective action in support of implementing the Sustainability Committee’s recommendations. If successful, the model could be reproduced in other settings in which the levers of power still lie in the hands of a privileged few and perhaps encourage greater accountability of officials to the will of their constituents. 

*Approach/Methodology*

The main goal of this project was to try to bridge some of the remaining gaps between the Sustainability Committee’s report and certain key desiderata of the Central Administration (cost savings potential of recommended actions, energy efficiency and utility cost comparisons to similarly specced buildings in Pittsburgh, etc.). Due to time constraints, I ultimately had to restrict the scope of the project to simply converting the report’s key data sets–namely greenhouse gas emissions from electricity use and heating per building for fiscal years 2014 to 2018–into a format that could be visualized geographically. Emissions data from prior to 2014 and emissions from transportation systems and non-energy sources (including fertilizers, refrigerants, etc.) were omitted for the sake of time. 

To represent each buildings’ energy use and emissions data geographically, I first obtained relevant data from Marty Altschul in CMU’s Facilities Management Services (FMS). Included in this data were the quantities of electricity (kWh), natural gas (Therms), and steam (MLbs) used by each CMU-owned or leased building during fiscal years 2014 to 2018. Each of these quantities was converted to its CO2 equivalent by using conversion factors either provided by Marty or published in the 2017 EPP-SDS report. The conversion factors used are provided in the table below.

*Table 1. CO2e conversion factor per unit energy use*
<p align="left">
<img width="70%" height="70%" src="https://user-images.githubusercontent.com/32546509/80046548-ecde1080-84d8-11ea-8040-f3d33779f126.JPG">
</p>

Once the energy use data had been converted to its CO2 equivalent values, it was joined to a shapefile of Allegheny County building footprints. This required first identifying which building IDs (BL_ID) from the energy use data set related to which building footprint ID (OBJECTID) in the Allegheny County building footprint data set (this was a many-to-one join in which multiple building IDs shared the same footprint ID). More detailed instructions on how these two data sets were matched is provided in the accompanying process log (see 4/24 entry). 

Next, I used definition queries to separate the 2018 fiscal year emissions data for each of the three energy types (electricity, natural gas, and steam). I then exported each of the resultant map layers as GeoJson files and uploaded them as data sets into [Mapbox](https://www.mapbox.com/). Once imported to Mapbox, I created a Style in which each CMU building was displayed as a 3D extrusion with a height proportional to its CO2e emissions. 

 
*Fig. 1. All map layers displayed (Mapbox Style editor view, in process)*
<p align="center">
<img width="100%" height="100%" src="https://user-images.githubusercontent.com/32546509/80047637-f2892580-84db-11ea-8607-6a6c9605daee.JPG">
</p>

I wanted to use a “stacking” method to present the proportion of total CO2e emissions represented by each of the three energy types, but I couldn’t pull it off in the allotted time frame. I believe I could eventually accomplish this effect by setting the base height of each component layer equal to the height of the layer underneath it (e.g., base height of electricity layer = height of natural gas layer, and base height of natural gas layer = height of steam layer). The figure below illustrates how the base layer function could be used to achieve a stacking effect. 

*Fig. 2. Illustration of using base layer setting to achieve “stacking” effect*
<p align="center">
<img width="100%" height="100%" src="https://user-images.githubusercontent.com/32546509/80047642-f4eb7f80-84db-11ea-87c9-c737eaaf5255.JPG">
</p>

Finally, I uploaded the [final map source code](https://github.com/jaxgoodlabs/Sustainable_Campus) onto GitHub. Using a series of Mapbox tutorials, I adjusted the map’s source code to incorporate some basic interactivity, including pop-ups to display information about each building. Though I had planned to have these pop ups include the building name, address, and proportional breakdown of CO2e emissions per energy type, time constraints only allowed me to configure the pop ups with a single value, aggregate CO2e emissions (see Fig. 3). 

*Fig. 3. Interactive map in GitHub Pages, illustrating pop-up feature*
<p align="center">
<img width="100%" height="100%" src="https://user-images.githubusercontent.com/32546509/80047644-f7e67000-84db-11ea-9250-9e6a57e93f0e.JPG">
</p>

### Results

*Solution/Findings*

Details related to troubleshooting are presented in the Approach/Methodology section above. More details on problems encountered during this project and how they were resolved can be found in the accompanying process log (see file: “GISProcessLogPatrickCampbell”). Results and findings are provided in the Conclusion section below. 

### Conclusion

Due to time constraints, I was unable to draw any final conclusions with respect to the central question of this study. That question was, “To what extent would equipping CMU students and other key stakeholders with accurate, up-to-date GHG emissions data for all CMU buildings and installations–along with the relevant set of analytical tools for rapid translation of data into actionable insights–facilitate collective action in support of implementing the Sustainability Committee’s recommendations?” By publishing the project on GitHub and GitHub Pages and sharing my work with those CMU students and faculty that are most active in promoting sustainability initiatives on campus, I hope to have laid the groundwork for eventually having that question answered. In the meantime, I was able to draw several provisional conclusions related to energy use and CO2e emissions of a large proportion of CMU-owned buildings and installations during the 2018 fiscal year. The most significant of these conclusions are presented below.

The average amount of CO2e emissions for CMU buildings in 2018 was 47,331 metric tons, with a standard deviation of 125,383 metric tons. The five buildings with the highest CO2e emissions values were:

1.	Pittsburgh Technology Center (OBJECTID #30998) – 1,033,795 metric tons
2.	ASTM International Test Monitoring Center (OBJECTID #481673) – 284,229 metric tons
3.	Cohon University Center (OBJECTID #142418) – 262,727 metric tons
4.	Morewood Gardens A-E (OBJECTID #150665) – 209,549 metric tons
5.	Doherty Apartments (OBJECTID #158025) – 152,705 metric tons

The five buildings with the lowest (non-zero) CO2e emissions values were:

1.	Bramer House & Garage (OBJECTID #149805) - 22 metric tons
2.	Highlands Apartments (OBJECTID #116460) - 46 metric tons
3.	Alumni House (OBJECTID #148899) - 648 metric tons
4.	Smith Hall (OBJECTID #143904) - 711 metric tons
5.	Margaret Morrison Apartments B (OBJECTID #169488) – 1,384 metric tons

Some of these findings are surprising and may reflect anomalies or inaccuracies in the data. One possible explanation for why this might happen is that the building footprint layer, which serves as the focal point of my analysis (identified by OBJECTID), sometimes encompasses more than one distinct building (identified by BL_ID). In such cases, the energy use and emissions values would be much higher than they should be, e.g., in the case that each building was represented individually. This is likely the case, for instance, for the OBJECTID associated with Morewood Gardens A-E above. 

### Future Work

Due to time constraints, there were several things I had hoped to accomplish that I wasn’t able to. Below I’ve provided a short list of suggestions for future work.

1.	Add emissions data for transportation systems and non-energy sources to more closely conform to the report that this analysis is intended to complement.
2.	Clean up the source data to make pop up info more readable/informative
3.	Provide a more granular breakdown of energy use and emissions per building by using building id (provided by FMS’s energy use and emissions data) instead of OBJECTID (the county’s building footprint data)
4.	Add missing buildings and related emissions data, especially Tepper
5.	Normalize energy use and emissions data by incorporating building size/area and other relevant attributes
6.	Separate energy use and emissions data according to building type (residential, industrial, etc.)
7.	Compare my findings and conclusions with those published in the 2017 EPP-SDS joint study for QA/QC purposes
8.	Add additional analytical tools and improve interactivity of published map (top priorities are relating emissions data to key desiderata of CMU’s Central Administration, including cost savings potential of recommended actions, energy efficiency and utility cost comparisons to similarly specced buildings in Pittsburgh, etc.)
9.	Include additional years to identify time trends (energy use and emissions data available for as far back as 2003)
10.	Clean up Process Log and convert to a concise protocol that others can follow to reproduce this study for their campus, and upload to Sustainable_Campus repository on GitHub

### Data Source(s)

A complete list of data sources used for this project along with descriptions of each can be found in the accompanying data documentation file (see file: “GISDataSourcesPatrickCampbell”). 

### References

Clay, Karen, Neil Donahue, Dave Dzombak, Vivian Loftness, Nick Muller, Illah Nourbakhsh, Illah, Ed Rubin, and Joel Tarr, eds. “The    Future of Sustainability Education, Research and Practice at CMU: Report of the Faculty Senate Ad Hoc Committee on Sustainability.” Carnegie Mellon University. February 2019.

Department of Engineering and Public Policy and Department of Social and Decision Sciences “Pittsburgh to Paris: Reducing the Carbon Footprint of Carnegie Mellon University.” Carnegie Mellon University. December 2017.

Maron, Mikel. “Mapbox Education – CMU Presentation.” PowerPoint Presentation. [https://docs.google.com/presentation/d/1sE0KsPb9ICbG7Ne1TucivOEmWDcTQuVjBH2cNRIytcU/edit?usp=sharing](https://docs.google.com/presentation/d/1sE0KsPb9ICbG7Ne1TucivOEmWDcTQuVjBH2cNRIytcU/edit?usp=sharing). Accessed April 25, 2019.

### Project Updates
On XX/XX/XXXX, this project was featured on Mapbox's student work. See the post [here]().
