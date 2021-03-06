GSKY interacts with ArcGIS suite
===============================================================

This tutorial demonstrate how ArcGIS pro, ArcGIS Earth and ArcMap interact with the GSKY Web Mapping Services (WMS). In this tutorial, you will learn to add layers by calling the GSKY WMS server. 


Introduction
~~~~~~~~~~~~~~~~~~~~~~~

ArcGIS 

https://learn.arcgis.com/en/projects/get-started-with-arcgis-online/
 
In this tutorial, we are going to demonstrate how to: 

* Create a map showing evacuation routes in Houston
* Use smart mapping and pop-ups to determine areas with low vehicle ownership.
* Configure a web app to share your findings with others.

0. Prerequisites 
~~~~~~~~~~~~~~~~

In this lesson, you'll create a map that shows hurricane evacuation routes in Houston, Texas. First, you'll create a new map and locate Houston, Texas. Then, you'll add a map layer that shows evacuation routes. Lastly, you'll change the way your map and layers look to better display the data.

If you don't have an ArcGIS account, you can sign up for a free `public account`_ or an `ArcGIS free trial`_.

.. _public account: https://www.arcgis.com/home/createaccount.html
.. _ArcGIS free trial: https://www.arcgis.com/features/free-trial.html

1. Sign in using google account 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Type this link in your web browser: https://www.arcgis.com/home/createaccount.html

.. image:: ../_static/images/GSKY_ArcGISweb1.png

Click "Using Google" to login.

.. image:: ../_static/images/GSKY_ArcGISweb2.png

You might need to click twice to login.

.. image:: ../_static/images/GSKY_ArcGISweb3.png

2. Choose a Basemap
~~~~~~~~~~~~~~~~~~~~~~~

Click "Map" on the top bar. You will see a map with the dafault location. 

.. image:: ../_static/images/GSKY_ArcGISweb4.png

Choose "Terrain with Labels" as the Basemap from the list. 

.. image:: ../_static/images/GSKY_ArcGISweb5.png

Type the location in the search window on the right-top corner and click enter. Dismiss the "Search result" box. 
We will just use the default view or search "Australia" if the default view is not Australia.

.. image:: ../_static/images/GSKY_ArcGISweb6.png

3. Load GSKY layer onto a map
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  
Click "Add | Add Layer from Web".

.. image:: ../_static/images/GSKY_ArcGISweb7.png

You will see a list of options from the drop down box below. Choose "A WMS OGC Web Service". 

.. image:: ../_static/images/GSKY_ArcGISweb8.png

Type "https://gsky.nci.org.au/ows/geoglam" in the URL box. Then click "ADD LAYER". You can tick the box beneath of URL box "Use as Basemap" if you like. 

.. image:: ../_static/images/GSKY_ArcGISweb9.png

All data layers published through GSKY production server should now be available for you to choose. Click the grey arrow to expend the dataset list. Note if you untick the top layer "GSKY Web Map Service", all the GSKY layers will be invisible. 

.. image:: ../_static/images/GSKY_ArcGISweb10.png

You can tick/untick the layer as you like. 

.. image:: ../_static/images/GSKY_ArcGISweb11.png

You can change the layer's appearance for each layer. Put mouse on top of the "..." under each layer, a list of options will pop up as below. For example, you can increase the Transparency by moving the percentage bar. You can use this layer as the Basemap by clicking "Move to Basemap". You can also remove the layer by choosing "Remove" option.

.. image:: ../_static/images/GSKY_ArcGISweb12.png


4. Add Oil and Gas pipeline data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click "Add | Browse Living Atlas Layers".

.. image:: ../_static/images/GSKY_ArcGISweb13.png

Search "Australia" to see what database is available in this Living Atlas. Two layers are found: Oil and Gas Infrastrcutre and DEM SREM 1 Second Hydro Enforced. 

.. image:: ../_static/images/GSKY_ArcGISweb14.png

Choose "Oil_Gas_Infrastructure" and click "Add layer".

.. image:: ../_static/images/GSKY_ArcGISweb15.png

Close the layer information (step 1 in red circle) and go back to the map view (step 2 in red circle)

.. image:: ../_static/images/GSKY_ArcGISweb16.png

Two layers are shown on the map.

.. image:: ../_static/images/GSKY_ArcGISweb17.png

Drag and move to re-arrange the order of different layers.

.. image:: ../_static/images/GSKY_ArcGISweb18.png

Click "Details | Contents | Layer name | Transparency" to see through this layer.

.. image:: ../_static/images/GSKY_ArcGISweb19.png


5. View attribute table
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click "Details | Content | Layer name (National Onshore Oil Pipelines) | Show Table" (click the table icon).

.. image:: ../_static/images/GSKY_ArcGISweb20.png

Move the bar up to expand the table view.

.. image:: ../_static/images/GSKY_ArcGISweb21.png

Select the records that you find interesting. Click "Show Selected Records".

.. image:: ../_static/images/GSKY_ArcGISweb22.png

The four selected records are highlighted on the map.

.. image:: ../_static/images/GSKY_ArcGISweb23.png


6. Style the layer with attribute
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click "Details | Contents | Layer name | Change style".

.. image:: ../_static/images/GSKY_ArcGISweb24.png

Choose an attribute to show - Operational status. Click "Option".

.. image:: ../_static/images/GSKY_ArcGISweb25.png

Click the colour line to change the styles.

.. image:: ../_static/images/GSKY_ArcGISweb26.png

Select thick black solid line for operational lines.

.. image:: ../_static/images/GSKY_ArcGISweb27.png

Select thick grey dash line for non-operational lines.

.. image:: ../_static/images/GSKY_ArcGISweb28.png

.. image:: ../_static/images/GSKY_ArcGISweb29.png


7. Enable and customise the Pop-up
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click "Details | Contents | Layer name (National Onshore Oil Pipelines) | More Options".

.. image:: ../_static/images/GSKY_ArcGISweb30.png

Click "Enable Pop-up".

.. image:: ../_static/images/GSKY_ArcGISweb31.png

Click on a tract to see the pop-up.

.. image:: ../_static/images/GSKY_ArcGISweb32.png

Click "Details | Contents | Layer name (National Onshore Oil Pipelines) | More Options | Configure Pop-up".

.. image:: ../_static/images/GSKY_ArcGISweb33.png

Choose "A description from one field" to display as pop-up content.

.. image:: ../_static/images/GSKY_ArcGISweb34.png

Click on a tract to see the pop-up.

.. image:: ../_static/images/GSKY_ArcGISweb35.png


8. Save the map and create a web app to share
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click "Save". 

.. image:: ../_static/images/GSKY_ArcGISweb36.png

Type the map name and tags. Click "Save maps".

.. image:: ../_static/images/GSKY_ArcGISweb37.png

Click "Share".

.. image:: ../_static/images/GSKY_ArcGISweb38.png

Click "Create a web app". The link to the map will automatically pop up.

.. image:: ../_static/images/GSKY_ArcGISweb39.png

Choose a template.

.. image:: ../_static/images/GSKY_ArcGISweb40.png

Click "Create web app".

.. image:: ../_static/images/GSKY_ArcGISweb41.png

Enter title, summary. Click "Done" and wait until map is generated.

.. image:: ../_static/images/GSKY_ArcGISweb42.png


Click "Save". Click "Launch". Copy the URL for sharing.

.. image:: ../_static/images/GSKY_ArcGISweb43.png

