



==============================================
Protecting your app with rate limiting
==============================================


+---------------------------------------------------------------------------------------------+
| Talk Track                                                                                  |
+=============================================================================================+
| The mortgage team has been hearing reports that some users aren't able to log in. They tell |
| Olivia: "our service is seeing massive network spikes and CPU load!"                        |
| Olivia attempts to relieve this by changing the mortgate app config so that these issues    |
| go away.                                                                                    |
| The mortgate app is made up of a couple of different components, a web login and web API    |
| endpoints.                                                                                  |
+---------------------------------------------------------------------------------------------+


Create the configuration
^^^^^^^^^^^^^^^^^^^^^^^^

    1. Using Postman (in the JumpHost)
    2. Expand the `Lending-Prod Environment` section
    3. Expand `Application - mortgage.acmefinancial.net`
    4. Select `Create Component - login` and click Send
    
    |login|
    
    5. Note that both the INGRESS URIs and WORKLOAD URIs are configured to use encryption

Insert rate limiting
^^^^^^^^^^^^^^^^^^^^

    .. note:: 
        Ratelimiting is only available in the **API** in Controller 3.0; it will be available in the GUI later.


    1. Select `Create Component - login - with rate`
    2. Note the Security section and the rateLimit. The rate limit is set low ( 1 second ) to provide some relief.
    
    |ratelimitspec|
    
    3. Click `Send` to push the configuration change (PUT method)

Test the Rate Limit configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    1. Open a tab in the web browser (in the JumpHost)
    2. enter the URL: https://mortgage.acmefinancial.net/login
    3. Refresh the page quickly a few times
    4. Note the 429 that is returned if you refresh the page too quickly

|rate_limiting_test|

.. |rate_limiting_test| image:: ../../_static/rate_limiting_test.png
   :scale: 50 %

==========
END OF LAB
==========

 .. |login| image:: ../../_static/postman_loginforratelimit.png
 .. |ratelimitspec| image:: ../../_static/postman_ratelimitspec.png
