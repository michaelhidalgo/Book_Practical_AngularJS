##  First PoC of sending TeamMentor's server-side request URLS to Firebase (and seeing it in realtime in an AngularJS page) 

After getting my head around how Firebase works (see [Using Firebase to sync data with a webpage (via Javascript, REST and Firebase Admin panel)](http://blog.diniscruz.com/2014/02/using-firebase-to-sync-data-with.html) and [Trying our Firebase (Beta) hosting solution and good example of Firebase Security rules](http://blog.diniscruz.com/2014/02/trying-our-firebase-beta-hosting.html)), I really wanted to see how it could work on a key feature that I've been wanting to add to [TeamMentor](https://teammentor.net/) for ages: **Realtime ****viewing  of ****traffic and logs**  

And it worked :)

This is really exciting!!! (can you tell :)  ), specially since I can see so many great uses of this type of technique and technology in TeamMentor (for example it will allow for much better understanding on how the content is used, and for better collaboration between its readers (and authors))

I'm going to write a number of blog posts that explain how this works in detail, but the core of it is the C# code shown below ([gist here](https://gist.github.com/DinisCruz-Dev/9252195#file-1-hook-teammentor-beginrequest-and-send-url-to-firebase-c)) which is running on a test TeamMentor instance, and basically hooks into the ASP.net HTTP pipeline in order to send the current URL to Firebase (using [Firebase's REST API](https://www.firebase.com/docs/rest-api.html)):

Here is the AngularJS+Firebase Html app that I created in Eclipse which shows the data received from the TeamMentor website (i.e. all requests made by a client visiting its home page):

[![](images/Screen_Shot_2014-02-27_at_15_18_09.png)](http://1.bp.blogspot.com/-wIXiiNCcaec/Uw9Y6f2_cJI/AAAAAAAAH3w/zTpP5ONyiaQ/s1600/Screen+Shot+2014-02-27+at+15.18.09.png)

... here are the logs for a page that doesn't exist: 

[![](images/Screen_Shot_2014-02-27_at_15_19_33.png)](http://3.bp.blogspot.com/-9KDQQhElxjg/Uw9Y7KHULMI/AAAAAAAAH34/xFVnlNhbm8s/s1600/Screen+Shot+2014-02-27+at+15.19.33.png)
  
... here are the requests for the TeamMentor error page:

[![](images/Screen_Shot_2014-02-27_at_15_20_31.png)](http://3.bp.blogspot.com/-ijACPD8WUFo/Uw9Y7QHUcvI/AAAAAAAAH38/FMkLvuGZYAA/s1600/Screen+Shot+2014-02-27+at+15.20.31.png)
  
**Quick look at the C# code executed on the TeamMentor server **([gist here](https://gist.github.com/DinisCruz-Dev/9252195#file-1-hook-teammentor-beginrequest-and-send-url-to-firebase-c))**:**  

Here is how the HTTP pipeline is hooked (using the TMEvents helper object from TM)  
  
[![](images/Screen_Shot_2014-02-27_at_15_17_07.png)](http://3.bp.blogspot.com/-ve3Wa3EtP9s/Uw9Y4NQx-FI/AAAAAAAAH3Y/8TwzoUucUnI/s1600/Screen+Shot+2014-02-27+at+15.17.07.png)

... the **_logDebugMsg_** and **_logRequestURL_** lambda functions are used to set the Firebase object to store the received messages:

[![](images/Screen_Shot_2014-02-27_at_15_16_58.png)](http://1.bp.blogspot.com/-lNw1XrcLLeQ/Uw9Y30XkZCI/AAAAAAAAH3E/x-o7k8R14nE/s1600/Screen+Shot+2014-02-27+at+15.16.58.png)

... the _sendData_ lambda function is used to configure the Firebase target app and authorisation token:

[![](images/Screen_Shot_2014-02-27_at_15_16_47.png)](http://4.bp.blogspot.com/--7gD20mwTmU/Uw9Y3vCiCbI/AAAAAAAAH3I/xQcP7iXJZps/s1600/Screen+Shot+2014-02-27+at+15.16.47.png)

... the **sendData_Raw **lambda function is the one that sends the REST/POST request to the mapped Firebase app:

[![](images/Screen_Shot_2014-02-27_at_15_16_39.png)](http://2.bp.blogspot.com/-5c8zXtyEPq4/Uw9Y3K6icvI/AAAAAAAAH20/FaLgi9W-mfs/s1600/Screen+Shot+2014-02-27+at+15.16.39.png)
  
Let me know if you have any questions regarding this example.  

**Firebase recovers connection**  

In terms of being able to recover from going offline, Firebase seems to do a good job at reconnecting back to the server once the host box is back online (see image below which happened between me leaving my house and connecting into my current WIFI location)  

[![](images/Screen_Shot_2014-02-27_at_15_15_10.png)](http://1.bp.blogspot.com/-i5Srlj4Zs7k/Uw9Y2v3vuiI/AAAAAAAAH2s/O4w25H2FheU/s1600/Screen+Shot+2014-02-27+at+15.15.10.png)




- - - - 
[Table of Contents](../Table_of_contents.md) | [Code](../Code)