=  Creating a network from a table of entities and their attributes
Clément Levallois <clementlevallois@gmail.com>
2017-02-22

last modified: {docdate}

:icons: font
:iconsfont:   font-awesome
:revnumber: 1.0
:example-caption!:

:title-logo-image: gephi-logo-2010-transparent.png[width="450" align="center"]

image::gephi-logo-2010-transparent.png[width="450" align="center"]
{nbsp} +

//ST: 'Escape' or 'o' to see all sides, F11 for full screen, 's' for speaker notes


== Presentation of the plugin
//ST: Presentation of the plugin

//ST: !

This plugin is created by https://www.clementlevallois.net[Clement Levallois].

It converts a spreadsheet or a csv file into a network.

//ST: !

This plugin enables you to:

*   Start from a data table in Excel or csv format
*   In the data table, nodes are the entities listed in column A
*   Nodes' attributes must be listed in columns B, C, D, etc.
*   Connections will be created between nodes, when they have identical attributes.
*   Attributes can have values, stored in columns right next to the attribute.

//ST: !
==== 1. The input
//ST: !

image::An-Excel-file.png[align="center", title="An Excel file"]
{nbsp} +


//ST: !
==== 2. The output
//ST: !

image::en/similarity-computer/result.png[align="center", title="Resulting network"]
{nbsp} +

== Installing the plugin
//ST: Installing the plugin
//ST: !

image::Choose-the-menu-Tools-then-Plugins.png[align="center", title="Choose the menu Tools then Plugins"]
{nbsp} +

//ST: !

image::Click-on-the-tab-Available-Plugins.png[align="center", title="Click on the tab Available Plugins"]
{nbsp} +

//ST: !

image::Install-the-plugin-then-restart-Gephi.png[align="center", title="Install the plugin then restart Gephi"]
{nbsp} +

== Opening the plugin
//ST: Opening the plugin
//ST: !

image::Open-the-plugin-via-the-menu-File---Import.png[align="center", title="Open the plugin via the menu File - Import"]
{nbsp} +

== Using the plugin
//ST: Using the plugin

//ST: !
==== First panel
//ST: !

image::Select-a-file.png[align="center", title="Select a file"]
{nbsp} +

//ST: Is your file with a header?

//ST: !

image::en/similarity-computer/file-without-header-en.png[align="center", title="A file without headers"]
{nbsp} +

//ST: !

image::en/similarity-computer/file-with-header-en.png[align="center", title="A file with headers"]
{nbsp} +

//ST: !
==== Second panel
//ST: !

image::en/similarity-computer/plugin-4-en.png[align="center", title="Parameter for weight"]
{nbsp} +

//ST: !
==== Third panel
//ST: !

image::en/similarity-computer/plugin-5-en.png[align="center", title="Confirmation panel"]
{nbsp} +

== How is the similarity computed, exactly?
//ST: How is the similarity computed, exactly?
//ST: !

We use the cosine similarity. Sounds complicated, but it is not. http://stackoverflow.com/questions/1746501/can-someone-give-an-example-of-cosine-similarity-in-a-very-simple-graphical-wa[Check here].

The source code for the cosine calculation is in this https://github.com/gephi/gephi-plugins/blob/master-forge/modules/SimilarityComputer/src/main/java/net/clementlevallois/computer/CosineCalculation.java[file], at https://github.com/gephi/gephi-plugins/blob/master-forge/modules/SimilarityComputer/src/main/java/net/clementlevallois/computer/CosineCalculation.java#L110[this place].

== FAQ / special notes on the plugin
//ST: FAQ / special notes on the plugin
//ST: !

==== 1. Excel files should be .xlsx, not .xls

Because they represent two slightly different files formats, and the plugin supports only .xlsx

//ST: !

==== 2. csv files are ok.

If you select a http://www.computerhope.com/issues/ch001356.htm[csv file], you will be asked to indicate the field delimiter and optionally the text delimiter.

image::en/similarity-computer/plugin-6-en.png[align="center", title="When a csv file is selected"]
{nbsp} +

//ST: !

==== 3. You can't use numerical values in the attributes

image::en/similarity-computer/numerical-attributes-en.png[align="center", title="Age is a numerical attribute"]
{nbsp} +

This is too bad. If there is enough demand for it I'll add this feature, which is not trivial.

//ST: !

==== 4. Each entity should appear only on one line

image::en/similarity-computer/plugin-7-en.png[align="center", title="An entity appearing twice"]
{nbsp} +

David appears on lines 2 and 5 (because he made two purchases). Only the latest line where David appears (line 5) will be taken into account.

== The end
//ST: The end!

Visit https://www.facebook.com/groups/gephi/[the Gephi group on Facebook] to get help,

or visit https://seinecle.github.io/gephi-tutorials/[the website for more tutorials]
