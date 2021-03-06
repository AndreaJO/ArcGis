# Grouping Values

The command <b> Summary Statistics </b> allows us not only to perform the basic exploratory analysis (such as Mean, Min, Max, Standard Deviation, etc) but is also a useful tool when our aim is to group fields from our attribute table depending of another variable.

We can find the command in Analysis <b>Tools->Statistics->Summary Statistics</b> or by typing <i>Summary Statistics</i> on the search bar

![Summary Statistics](https://raw.githubusercontent.com/biometry/ArcGis/master/Images/Summarize/Summary%20Statistics.JPG)

In this example, we wanted to group the field <b>Shape_Area </b> based on the field <b> RST_SIEGEL </b>, type of soil composition. That means that we have several rows with the same type of soil and in order to make an easier graphic representation, we will add the area of each type of soil. The result will be only one row per type of soil with the sum of the areas.

![Summary Statistics Command](https://raw.githubusercontent.com/biometry/ArcGis/master/Images/Summarize/Summary%20Statistics.JPCommand_G.JPG)

* <i>Input Table</i>: The Attribute table that contains the data we want to summarize

* <i>Output Table</i>: Table destination

* <i>Statistics Field</i>: The field (numeric) that we will calculate or, in this case, add. 
An error message will pop up when we select our variable. That is because we need to select the Statistic Type that we want to calculate (Mean, STD, etc). We select <b>SUM</b> for this example.

![Error](https://raw.githubusercontent.com/biometry/ArcGis/master/Images/Summarize/Error.JPG)

* <i>Case Field</i>: The field dependent on the Statistic field. The soil type, or <b>RST_SIEGEL</b> in our example.

<i>Note:</i> Another way to summarize the value would be on the attribute table. We just have to select the column we want to summarize and click on the command.


Once the table with the new group values is created, we can create a graphic representation of it.
In <b>View->Graphs->Create Graph</b> we just have to select the type of graph we want and to set up the Value Field (The sum of the areas in our case) and the X field/label (type of soil or RST_SIEGEL here)

![Graph Set Up](https://raw.githubusercontent.com/biometry/ArcGis/master/Images/Summarize/GraphsetUp.JPG)
![Graph](https://raw.githubusercontent.com/biometry/ArcGis/master/Images/Summarize/Graph.JPG)

##Grouping values with different names

The first step will be to create a new column where we will calculate the new names for the different groups we want to have.

Once with have it, we will have to use <b>Select By Attributes</b> to select the items that will conform one of our groups. In our example, the first group would consist in all the elements from the column <i>BST_BEZ</i> that contain the letter <i>a</i> (that is, a3, a2, a5, a2*1, etc).
The expression that we will write on the <b>Select By Attributes</b> window will be: <i>"BST_BEZ" LIKE 'a%'</i>
LIKE would mean <i>contains</i> and the <i>%</i> symbol indicates that we do not care what is written after the a.

![Select By Attribute](https://raw.githubusercontent.com/biometry/ArcGis/master/Images/Summarize/Graph.JPG)

