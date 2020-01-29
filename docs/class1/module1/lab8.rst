=====================================================
Extending www.acmefinancial.net with a blog Component
=====================================================

Samantha is looking to expand on the marketing sites that are promoting the various technologies that the ACME Financial organization has been able to produce.
She wants to build a brand new application component within the marketing page www.acnefinancial.net and introduce the new blog capability so they can start blogging about the trading application.
So let's return to Controller as Samantha and take a look at some of the additional feature functionality with the ADC use cases of URI rewrite.

Log out as David
^^^^^^^^^^^^^^^^^^^

   1. Returing to the Controller GUI
   2. Select |admin| in the top right
   3. Select |logout|

Log in as Samantha
^^^^^^^^^^^^^^^^^^^^^

   1. Login as Samantha using the username: retain-dev@acmefinancial.net with the passord Admin123!@#

Review the Components added via the API
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   1. Select Services from the navigation menu
   2. Select Apps
   3. Select trading.acmefinancial.net
   4. Review the componnets added through the API, note the commonality between the API and GUI

Add blog page to the main ACME Financial site with a URI rewrite
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   1. Return to the list of all Apps
   2. Select www.acmefinancial.net
   3. Select View
   4. Select Create Component
   5. Name: blog
   6. Gateway: www.acmefinancial.net
   7. URI: /blog
   8. Add Workload Group: wordpress
   9. Add Backend Workload URIs:
      1. http://10.1.20.21:8003
      2. http://10.1.20.22:8003
   10. Add URI Rewrite:
       1. incoming pattern: ^/blog/(.*)$
       2. rewrite pattern: /blog/wordpress/wwwsite/$1?
   11. Publish

Test the URI rewrite
^^^^^^^^^^^^^^^^^^^^^^^

    1. In a new tab in the web browser enter: http://www.dev.acmefinancial.net/blog/biganouncement
    2. In the returned web page note that the path is being rewritten to: /blog/wordpress/wwwsite/biganouncement

.. |admin| image:: ../../_static/admin_istrator.png
    :scale: 50 %

.. |logout| image:: ../../_static/log_out.png
    :scale: 50 %