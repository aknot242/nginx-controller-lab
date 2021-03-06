=============================
Analytics of your app
=============================

+---------------------------------------------------------------------------------------------+
| Talk Track                                                                                  |
+=============================================================================================+
| In the previous scenario, we saw the expansion of the trading application. Now, let's take  |
| a look at the statistics Controller makes available for this app.                           |
+---------------------------------------------------------------------------------------------+


Viewing Analytics in the GUI
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    1. Select the Controller GUI tab in Chrome
    2. Using the navigation bar, select the `Analytics` menu
    3. Select the `retail-dev` Dashboard
    4. Note the traffic that you created during the previous steps
    
    |capture|

    In Controller 3.0 we have the ability to see all the statistics available to Samantha via a dashboard. You can edit and add additional statistics. You can see some of the traffic you have been generating while through the lab.

Viewing Metrics with the API
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    1. Using Postman
    2. Open the `Analytics` section
    3. Select `get metrics with filter`
    4. Review the query settings of resolution of 30 minutes for the aggregation of SUM of 500 errors with a filter to NGINX instance 4 or 6
    5. Select `Send`

     The return is time series data that are a summary of status 500 messages counted every 30 minutes.  The API offers flexibility to craft a number of different queries using filters, resolution over time periods, and aggregations.

  .. |capture|  image:: ../../_static/analytics.png
      :scale: 40%
