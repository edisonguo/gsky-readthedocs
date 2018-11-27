.. role:: red

.. role:: blue

.. role:: green


Web Coverage Services (WCS)
============================

NCI's GSKY Data Server supports the Open Geospatial Consortium (OGC) Web Coverage Service (WCS), which is a standard protocol for serving geospatial data in common formats such as NetCDF and GeoTIFF.


Constructing WCS requests
--------------------------

GSKY's Web Coverage Service (WCS) allows users to request data or subsets of data in either NetCDF3 or GeoTIFF format. The request is made by constructing a GetCoverage URL, which is then used within a web browser to communicate to the GSKY Data Server.

For example, the GetCoverage request takes the following form:


http://gsky.nci.org.au/ows?\ :red:`service`\ =WCS&\ :red:`version`\ =1.0.0&\ :red:`request`\ =GetCoverage&\ :red:`coverage`\ =\ :green:`value`\ &\ :red:`format`\ =\ :green:`value`
\
&\ :blue:`bbox`\ =\ :green:`value`\ &\ :blue:`crs`\ =\ :green:`value`\

where :red:`red` indicates required fields, :blue:`blue` are optional, and :green:`green` are where input values relevant to the dataset and user request need to be defined.

GetCoverage parameters
-----------------------

+------------------------+-----------------------+--------------------------------------+
| Parameter              | Required/Optional     | Input                                |
+========================+=======================+======================================+
| service                |  Required             | ``WCS``                              |
+------------------------+-----------------------+--------------------------------------+
| version                |  Required             | ``1.0.0``                            |
+------------------------+-----------------------+--------------------------------------+
| request                |  Required             | ``GetCoverage``                      |
+------------------------+-----------------------+--------------------------------------+
| coverage               |  Required             | ``<variable>``                       |
+------------------------+-----------------------+--------------------------------------+
| format                 |  Required             | ``GeoTIFF, GeoTIFF_Float, NetCDF3``  |
+------------------------+-----------------------+--------------------------------------+
| bbox ``*``             |  Required             | ``<xmin,ymin,xmax,ymax>``            |
+------------------------+-----------------------+--------------------------------------+
| time ``*``             |  Required/Optional    | ``<time_value>``                     |
+------------------------+-----------------------+--------------------------------------+
| srs, or crs            |  Required/Optional    | ``<srs_value>`` or ``<crs_value>``   |
+------------------------+-----------------------+--------------------------------------+

``*`` For large files and/or files with a time dimension, these might be necessary. If ``bbox`` is not defined, the entire spatial domain will be returned (if server limits allow)
and if ``time`` is not specified, either the first or sometimes the last timestep is returned.


WCS GetCapabilities and DescribeCoverage
-----------------------------------------

**Where do you find valid input values?**

In order to contruct the **GetCoverage** URL, a **GetCapabilities** request can be made to the server. This requests returns an xml describing the available
WCS parameters (metadata, services, and data) made available by NCI's GSKY server. Additional metadata information can also be requested about a specific
coverage layer by making a **DescribeCoverage** request.

**GetCapabilities example:**

http://gsky.nci.org.au/ows?service=WCS&version=1.0.0&request=GetCapabilities

.. image:: ../_static/images/gsky_wcs1.png


**DescribeCoverage example:**

http://gsky.nci.org.au/ows?service=WCS&version=1.0.0&coverage=LS5:NBAR:TRUE&request=DescribeCoverage

.. image:: ../_static/images/gsky_wcs2.png


GetCoverage request
--------------------

Using the information returned from the GetCapabilities and DescribeCoverage requests, a GetMap URL can be constructed and then entered into the address bar of any web browser.

**Example GetCoverage (NetCDF format)**


  | http://gsky.nci.org.au/ows?
  | :red:`service`\ =WCS&
  | :red:`coverage`\ =LS7:NBAR:TRUE&
  | :red:`crs`\ =EPSG:4326&
  | :red:`format`\ =NetCDF&
  | :red:`request`\ =GetCoverage&
  | :red:`height`\ =256&
  | :red:`width` =256&
  | :red:`version`\ =1.0.0&
  | :red:`bbox`\ =148,-37,151,-34&
  | :red:`time`\ =1999-08-05T00:00:00.000Z


 `http://gsky.nci.org.au/ows?SERVICE=WCS&service=WCS&crs=EPSG:4326&format=NetCDF&request=GetCoverage \ &height=256&width=256&version=1.0.0&bbox=148,-37,151,-34&coverage=LS7:NBAR:TRUE \ &time=1999-08-05T00:00:00.000Z <http://gsky.nci.org.au/ows?SERVICE=WCS&service=WCS&crs=EPSG:4326&format=NetCDF&request=GetCoverage&height=256&width=256&version=1.0.0&bbox=148,-37,151,-34&coverage=LS7:NBAR:TRUE&time=1999-08-05T00:00:00.000Z>`_.

 **Example GetCoverage (GeoTIFF format)**


   | http://gsky.nci.org.au/ows?
   | :red:`service`\ =WCS&
   | :red:`coverage`\ =LS7:NBAR:TRUE&
   | :red:`crs`\ =EPSG:4326&
   | :red:`format`\ =GeoTIFF&
   | :red:`request`\ =GetCoverage&
   | :red:`height`\ =256&
   | :red:`width` =256&
   | :red:`version`\ =1.0.0&
   | :red:`bbox`\ =148,-37,151,-34&
   | :red:`time`\ =1999-08-05T00:00:00.000Z


  `http://gsky.nci.org.au/ows?SERVICE=WCS&service=WCS&crs=EPSG:4326&format=GeoTIFF&request=GetCoverage \ &height=256&width=256&version=1.0.0&bbox=148,-37,151,-34&coverage=LS7:NBAR:TRUE \ &time=1999-08-05T00:00:00.000Z <http://gsky.nci.org.au/ows?SERVICE=WCS&service=WCS&crs=EPSG:4326&format=GeoTIFF&request=GetCoverage&height=256&width=256&version=1.0.0&bbox=148,-37,151,-34&coverage=LS7:NBAR:TRUE&time=1999-08-05T00:00:00.000Z>`_.
