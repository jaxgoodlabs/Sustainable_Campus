# SUSTAINABLE CAMPUS PROJECT: PROCESS LOG
## 94802-A: Geographic Information Systems, Spring 2019

*Thurs., 2/21/19* 

9-9:30 am – Meeting with Karen Clay, Heinz College 
- Discussed ideas for a Climate CoLab at CMU, or adaptations of the project to promoting sustainability at CMU

*Mon., 3/25/19*

4-5:15 pm – Meeting with Ed Rubin, EPP 
- Discussed subjects related to the development of a central Sustainability Office at CMU, opportunities to abet the process

*Tues., 4/2/19*

4:30-5:30 pm – Faculty Senate meeting
- Resolution passed committing CMU Central Administration to decision on recommendations by Ad Hoc Committee on Sustainability

*Wed., 4/3/19*

4:30-5 pm – Meeting with Karen Clay 
- Discussed discussions related to the development of a central Sustainability Office at CMU, opportunities to abet the process

*Sun., 4/14/19*

4-8 pm – Research, draft proposal

*Mon., 4/15/19*

9:30-11 am – Research, draft proposal

*Sat., 4/20/19*

2-2:30 pm – General Administrative
- Wrote Mikel for general guidance on using MapBox for visualizing data layers
- Solicited help with Github project management piece on Facebook
2:30-4:30 pm – Read and take notes on EPP-SDS report, identify data sets to be obtained and where to find them. Update proposal with new data sets. Send proposal to Ed Rubin (EPP) to ask for feedback, help obtaining data sets.
5:30-7:30 pm –Create documentation for data sets (File: “GISProposalDataPatrickCampbell”). Create file structure for downloaded data. 
9-10:30 pm – Track down and download other data sets. Explore University of New Hampshire Sustainability Institute’s Campus Carbon Calculator (CCC) https://sustainableunh.unh.edu/calculator. Supplement data ReadMe file.

**Notes**
- Could also use aggregate data from each focus area.
- Could use transformed data to compare GHG emissions only per sector. To do this, EPA data converts electricity usage in the CO2 equivalent (CO2e)
- Need to determine the standard practice for how these data sets were prepared. It looks like the final form of all data sets was a CO2e calculation by source, in order to provide a comprehensive assessment of CMU’s carbon footprint. Your project should probably take the same approach. The sections are always overview, data source, past and current, projected, GHG conversion

*Sun., 4/21/19*

10-11:30 am – General administrative
- Email benchmarking@pittsburghpa.gov to request energy and water use data for all covered CMU buildings
- Email Neil Donahue (Director, Steinbrenner Institute for Environmental Education and Research and Barb Kviz (Environmental Coordinator, Green Practices) to request any data related to campus GHG emissions
- Explore Carnegie Mellon’s participation in outside sustainability initiatives
- International Sustainable Campus Network (https://www.international-sustainable-campus-network.org/membership-directory/231-carnegie-mellon-university)
  - Last report submitted 2013

- Explored Cornell’s GHG Inventory for guidance on data sets to make comparable (https://sustainablecampus.cornell.edu/our-leadership/cap/ghg-inventory)
  - Use the http://ghgprotocol.org/


12-12:30 pm – Download and set up Mapbox

*Mon., 4/22/19*

9-10:30 am – General administrative
- Write Jessica Benner (CMU Library, GIS) about CMU buildings and installations shapefile
- Explore applications for query-supporting GIS tools
  - GISPublisher
  - GISExplorer

*Tues., 4/23/19*

12:30 pm – General administrative
- Set up call with Mikel (MapBox)
1:30 pm – Explore GitHub Pages as possible hosting platform for project (https://pages.github.com/)

*Wed., 4/24/19*

9-10:30 am – Track down, download, and clean parcel and property tax assessment data.  
3:30-7:30 pm - Clean parcel and property tax assessment data. 
- Filter Allegheny County Parcel records by owner using the filter tool in the attribute table for the Parcels data layer in the Allegheny County ArcGIS Data Viewer. Manually add owner info from Allegheny County Parcels data to a new spreadsheet along with MapBlockLot number. Save the csv file as CMU Parcels MapBlockLot.csv. Import CMU Parcels MapBlockLot.csv to GDB as CMU_Parcels. Join CMU_Parcels table to Allegheny County Parcels shapefile. Name it CMU Parcels. 
- Create new data layers:
  - CMU Parcels – Pittsburgh Parcels filtered by owner (definition query owner = CARNEGIE MELLON UNIVERSITY)
  - CMU Campus – CMU Parcels dissolved by ObjectID
  - CMU Address Points – Pittsburgh Address points clipped to CMU Campus
  - CMU Buildings – Pittsburgh buildings clipped to CMU Campus
8:30-9:45 pm - Prepare for call with Mikel (MapBox). 
- Geocode table of addresses (instructions at http://desktop.arcgis.com/en/arcmap/10.3/guide-books/geocoding/geocoding-a-table-of-addresses-in-arcmap.htm)

*Thurs., 4/25/19*

9:30-10 am – Call with Mikel (MapBox). Talking points include:
- Visualization options for transportation and non-energy source emissions
- Project hosting on GitHub/GitHub Pages
- Purchase Real Estate Data CD for all parcels owned by Carnegie Mellon University. Call 412-350-6322 for more info.
1:15-1:45 pm – Meeting with Marty Atschul (FMS)
5:45-7:30, 8:30-10 pm – Clean CMU emissions data
- Join parcel (MapBlockLot) and building ID (OBECTID) fields to emissions data

*Fri., 4/26/19*

10:45 am -12:30 pm
- Clean CMU emissions data
- Join parcel (MapBlockLot) and building ID (OBECTID) fields to emissions data
2:30-11:30 pm
- Clean CMU emissions data
- Separate data by emissions category (electricity, steam, and natural gas) and year (2014-2018)
- Convert energy base units to CO2e (see  https://www.epa.gov/energy/greenhouse-gas-equivalencies-calculator; https://www.epa.gov/energy/greenhouse-gases-equivalencies-calculator-calculations-and-references). Email Marty for conversion factors.
- Format new emissions map layers in ArcGIS
- Convert data layers to geojson.files using Convert Feature to Json tool and import into Mapbox 
- Experiment with Mapbox visualization tools

*Mon., 4/29/19*

9-10:30 am – Fix problems with emissions table spreadsheet and update all feature layers in GDB project file. 
8-9:30 pm – Run through “add points to a map” tutorial (https://docs.mapbox.com/help/tutorials/add-points-pt-3/). Schedule appointment with Chris for Tuesday morning to debug emissions data. Schedule appointment with Mikel for Tuesday afternoon to finish visualization and set up Github Pages.
10-11:30 pm – Update data documentation. Upload updated project folder to L drive. 

*Tues., 4/30/19*

10-10:30 am – Meeting with Chris to debug emissions spreadsheet
12:30-2:30 pm – Fix emissions source data and update map layers. Export revised map layers as geojson files. Load datasets to Mapbox account and incorporate into Style. Email update to Mikel.
10:30 pm–12 am – Make final updates to Style. Email updates to Mikel. 

*Wed., 5/1/19*

9-10:30 am –Draft final report. Clean up aesthetics in Mapbox.
12:30-1:30, 3:30-4:30 pm – Add pitch to map (see https://docs.mapbox.com/mapbox-gl-js/example/set-perspective/). Convert electricity, steam, and natural gas units to CO2e for proportional display. [Not completed]
- Use aggregate spreadsheet to calculate proportion. Set proportions on Mapbox while maintaining original units.
- Open CMU energy use and GHG emissions_Final.csv
- Filter records by FY=2018
- Sort records by OBJECTID
- Calculate proportion of each energy type by dividing each use total (in original unit) by CO2e total (in metric tons).
In Mapbox, set height of each energy layer by multiplying use by proportion. [Not completed]
4:30-5:30 pm – Call with Mikel
Troubleshoot stacking visualization
Troubleshoot pop ups for buildings
Publish map source code (index.html) on GitHub
Move Mapbox project onto GitHub Pages. Publish Style with following interactivity:
Zoom / navigate
Pop ups for buildings (for all 4 2018 layers)
Building name [Not completed]
Address [Not completed]
Energy use [Not completed] / emissions stats
3D extrusions and color coding visualization for 4 2018 layers
Electricity use
Steam
Natural gas
Aggregate CO2e
[Proportional representation not completed]
5:30 pm -12 am – Finish final report and PowerPoint presentation. Make finishing touches on Mapbox Style. Clean up Data Documentation and Process Log files. Upload final project to L Drive.

Wed., 7/10/19
11 am – 4:30 pm – Add GHG emissions map layers for previous years (2014-2017)
Calculate change in GHG emissions per building from first year (2014) to most recent year (2018)
Open spreadsheet “CMU energy use and GHG emissions_Final” in Excel.
Save file as “CMU energy use and GHG emissions_Extension1”
Save 2014-2018 CO2e worksheet as a .csv file. Save as “2014_2018_SummarizeWithinTest”.
Import file “2014_2018_SummarizeWithinTest.csv” into ArcGIS project database.
Use Summary Statistics tool to calculate sum of CO2e per building (across all services) per year (see figure 1). Export new table as “SummarizeWithinTest_BuildingYear.”
Copy/paste “SummarizeWithinTest_BuildingYear” table into Excel. Sum Frequency field to verify that the number of records matches the source data (1224 records).
Create 4 duplicate copies of “SummarizeWithinTest_BuildingYear” as separate tabs and rename them as follows:
1-Yr Change in CO2e (2017-2018)
2-Yr Change in CO2e (2016-2018)
3-Yr Change in CO2e (2015-2018)
4-Yr Change in CO2e (2014-2018)
In each tab, eliminate all records except those corresponding to the first and last years in the range listed (e.g., first tab will contain all the records for FY 2017 and FY 2018, second tab all records for FY 2016 and FY 2018, etc.). 
For each tab, use conditional formatting to highlight duplicate records (use BL_ID field). Eliminate any building record that doesn’t have a pair in FY 2018 (not highlighted). Remove conditional formatting on BL_ID field. 
For each tab, sort records smallest to largest by BL_ID and smallest to largest FY. Create new field after SUM_CO2E field and name it “DIFFERENCE_CO2E.” In the new field, enter the formula =[2018 SUM_CO2E]-[first year SUM_CO2E] to calculate the difference in CO2e between the first and last years of the range. Drag down to autofill.
Optional: Use conditional formatting to highlight in red values larger than 0 and highlight in green values smaller than 0.
Save full workbook as .xls file. Save as “CMU energy use and GHG emissions_Extension1” (overwrite existing file). Move file “2014_2018_SummarizeWithinTest” to archive.
Save each tab as separate .csv files using the tab names as file names.
Import the .csv files for each year pair into ArcGIS project database.
In the DIFFERENCE_CO2E field for each new data table, change all null values to zeros using these instructions: https://support.esri.com/en/technical-article/000016100.
Use Summary Statistics tool to calculate the difference in CO2e between the first and last years for each building (see figure 2). (Notice that several records have null values in the OBJECTID and PARCEL fields. These will not be included in the subsequent join.)
Save project.

Thurs., 7/11/19
8 am – 4:30 pm – Prep map layers for import to Mapbox.
Create a new field ABS_DIFF (type: long, numeric) containing the absolute value of the change in CO2e. Calculate field using the following formula:
= abs(!SUM_DIFFERENCE_CO2E!)
Create a new field CHANGE_TYPE_NUM (type: long, numeric) containing a 1 for SUM_DIFFERENCE_CO2E > 0 and 0 for SUM_DIFFERENCE_CO2E <= 0. Calculate field using the following formula:
= 1 if !SUM_DIFFERENCE_CO2E! > 0 else 0
Create a new field CHANGE_TYPE (type: text) containing the text “decrease” for SUM_DIFFERENCE_CO2E <= 0 and “increase” for SUM_DIFFERENCE_CO2E > 0. Calculate field using the following formula:
= “decrease” if !SUM_DIFFERENCE_CO2E! <= 0 else “increase”

Fri., 7/12/19
8 am – 2 pm – Continue prepping map layers for import to Mapbox.
Join each table to the CMU_Buildings map layer. 
21 records in table “CO2eChange4YR_Difference” contain null values for OBJECTID. Also, number of records in CMU_Buildings layer is 135 while number of records in table “CO2eChange4YR_Difference” is 117. 
Conditional formatting in Excel reveals 61 unmatched records for CMU_Buildings layer and 5 unmatched records for “CO2eChange4YR_Difference.” 17 records in source data table contain duplicate OBJECTIDs but unique BL_IDs (see figure 3).
Default join in ArcGIS yields incorrect number of records and lots of null values for emissions fields. Solution below:

Mon., 7/15/19
1-4 pm – Troubleshoot join

Join Troubleshooting Guide
In Excel, fill in missing OBJECTIDs and PARCEL IDs for the “CO2e by Building and Year” worksheet using Google maps and Allegheny County GIS viewer. Update “4-Yr Change in CO2e (2014-2018)” worksheet accordingly. Save updated worksheet as .csv file with the name “CO2eChange_2014-2018b.”
Import the .csv file for the 4YR change (2014-2018 pair) into ArcGIS project database.
In table “CO2eChange4YR2,” run summary statistics tool to calculate the total change in CO2e emissions from 2014-2018 per OBJECTID. Save resultant table as “CO2eChange4YR_Difference”
In “CO2eChange4YR_Difference,” run summary statistics tool to eliminate duplicate OBJECTIDs. Sum Difference in CO2 field. Name resultant table “CO2eChange4YR_Difference_test1.”   
Create a new field ABS_DIFF (type: long, numeric) containing the absolute value of the change in CO2e. Calculate field using the following formula:
= abs(!SUM_DIFFERENCE_CO2E!)
Create a new field CHANGE_TYPE_NUM (type: long, numeric) containing a 1 for SUM_DIFFERENCE_CO2E > 0 and 0 for SUM_DIFFERENCE_CO2E <= 0. Calculate field using the following formula:
= 1 if !SUM_DIFFERENCE_CO2E! > 0 else 0
Create a new field CHANGE_TYPE (type: text) containing the text “decrease” for SUM_DIFFERENCE_CO2E <= 0 and “increase” for SUM_DIFFERENCE_CO2E > 0. Calculate field using the following formula:
= “decrease” if !SUM_DIFFERENCE_CO2E! <= 0 else “increase”
Optional: Delete any records containing null values for OBJECTID.
<End troubleshooting guide>
Copy and paste all records from table “CO2eChange4YR_Difference” and CMU_Buildings map layer into Excel. Use conditional formatting to identify duplicates. Eliminate any record without a pair in the corresponding table. Resolve any discrepancies in Parcel or other fields. Sum the values in the SUM_DIFFERENCE_CO2E field for any records sharing the same OBJECTID (applies to 6 records in “CO2eChange4YR_Difference” table). Save worksheet as a .csv file with the name “CO2eChange4YR_Difference_test.”
Import table “CO2eChange4YR_Difference_test” into ArcGIS project. 
Join table “CO2eChange4YR_Difference_test” to a copy of CMU_Buildings map layer. Rename map layer “Join_CO2eChange4YR_Difference.”
Export each new map layer into the project geodatabase using the naming convention “CMU_[#YR]CO2eDifference” (e.g., “CMU_4YRCO2eDifference,” etc.). 
Use the Feature to JSON tool to convert each new map layer to GeoJSON files.
7:30 - 10:30 pm – Visualize GHG emission changes in Mapbox
Use 3D extrude function to visualize changes in CO2e over time
Import GeoJSON file into Mapbox data library. 
Export data source as a tile set. 
Load tile set into Style. 
Select Extrude option
Set extrude height using ABS_DIFF field in tile set



Tues., 7/16/19
8:30 am - 12:15 pm – Add choropleth effect to highlight lowest and highest-achieving buildings
Create two copies of the CO2eChange4YRtest map layer
In the ‘select data’ window under the ‘Filter’ tab, Filter the two layers by CHANGE_TYPE_NUM field (0 for decrease in energy use, 1 for increase in energy use)
In the ‘Select data’ window under the ‘Type’ tab, choose the 3d extrusion option. 
In the ‘Style’ window under the ‘Height’ tab, choose the formula option, choose the ABS_DIFF_NUM field together with the formula / 100 
For the map layer for buildings with decreased energy use, select a green color scheme. For the map layer for buildings with increased energy use, select a red color scheme.
Under the color tab, use the ‘Style across data range’ option to create a choropleth effect (e.g., low-range numbers symbolized in yellow, mid-range numbers symbolized in orange, and high-range numbers symbolized in red)
1:30 - 4:30 pm – Parse building footprint map layer by BL_ID
In Excel, identify OBJECTIDs with multiple associated BL_IDs
Use Google maps to identify where the building separations are located
In ArcGIS, select the building footprint you wish to edit using the select tool. Right click the selected polygon and choose the vector option. Drag the vectors to eliminate the connections between distinct buildings (the isolated portion should appear as red). After you’ve isolated the portion of the polygon you wish to eliminate, choose the select tool again. The red portion of the polygon should disappear. 
Repeat for all building footprints until each building footprint is associated with one BL_ID. 
In the data tab, save all edits. 
Update “CO2eChange4YR” tab in CMU energy use and GHG emissions_Extension1.xls workbook to include recent edits. 
Save “CO2eChange4YR” tab as a .csv file under the name “CO2eChange4YR_BL_ID.”

Wed., 7/17/19
4:30-6 pm – Perform join on updated building footprint map layer
Import table “CO2eChange4YR_BL_ID” into ArcGIS geodatabase.
Join table “CO2eChange4YR_BL_ID” to CMU_Buildings_BL_ID map layer.
Repeat steps above to calculate the difference in CO2 between 2018 and 2014, change type (increase, decrease, 0, 1), etc.
Export edited map layer into project geodatabase with the name “CMU_Buildings_BL_ID_JOIN”

Thurs., 7/18/19
9 am - 2 pm – Perform join on updated building footprint map layer (cont.)
Use Multipart to Singlepart tool on CMU_Buildings_BL_ID_JOIN map layer to divide new (separated) building footprint polygons into distinct records. 
Action resulted in the creation of 39 new records. Duplicates indicate distinct buildings (common OBJECTID assigned to every BL_ID and every polygon in previous group). 
Export new map layer to project geodatabase as CMU_Buildings_BL_ID_FINAL
Use Google maps to identify which polygon belongs with which BL_ID and eliminate the remaining records in map layer attribute table. 
Elimination of records will result in same number of records as original map layer (CMU_Buildings_BL_ID_JOIN), which is what we’d expect (number of records in original table is equal to the number of unique BL_IDs).  
Copy/paste the edited data table into Excel. For all BL-IDs that belong to a single building, combine the relevant layers into a single aggregate layer by manually calculating the sum of the 4-yr change in CO2e for the two component BL_IDs.
Save resultant worksheet as a .csv file with the name “”
Import the table “” into ArcGIS project database.
Join “” with CMU_Buildings_BL_ID_FINAL map layer.
Export edited map layer into project geodatabase with the name CMU_Buildings_BL_ID_FINAL.
Use Feature to JSON tool to convert to a GeoJSON file. 
4 pm - 5 pm – Visualize GHG emission changes in Mapbox
Repeat steps above to visualize GHG emission changes at the BL_ID level.

Thurs., 7/25/19
8:30 am – 12:15 pm – Add 2D/3D toggle


