##  Creating an Eclipse UI to run AngularJS e2e tests using Karma 

This post shows how I created a nice set of views in Eclipse to quickly see the execution result of AngularJS e2e (end-to-end) tests, without leaving the Eclipse UI.

The image below shows this UI in action, where:  


  * The source code of the test is shown in the Eclipse Java editor
  * Just below is the **_console out_** of the Karma runner (which is detecting files changes)
  * On the top-right is the hooked browser (i.e. the one that will run the tests)
  * On the middle-right is the simple AngularJS **_Hello World_** page
  * On the bottom-right is the debug view of the hooked browser (which is what you get if you click on the **_Debug_** Button included on the top-right page)

[![](images/Screen_Shot_2014-02-24_at_12_46_54.png)](http://1.bp.blogspot.com/-XBiLq8A498k/Uws_Xn2LheI/AAAAAAAAHZk/yAr1W30Avl8/s1600/Screen+Shot+2014-02-24+at+12.46.54.png)
  
Here are the tools and Eclipse Plugins used to create this UI:  

* [Eclipse Kepler for Java EE Developers](https://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/keplersr1) with:

    * [Eclipse Grovy REPL Scripting Environment 1.6.0](http://marketplace.eclipse.org/content/eclipse-grovy-repl-scripting-environment) ([update site](http://eclipse-plugin-builder.azurewebsites.net/))
    * [AngularJS Eclipse Plugin](https://github.com/angelozerr/angularjs-eclipse)  ([update site](http://oss.opensagres.fr/angularjs-eclipse/1.0.0-SNAPSHOT/))
    * [Nodeclipse](http://www.nodeclipse.org/) ([update site](http://dl.bintray.com/nodeclipse/nodeclipse/0.10.0/))
    * [Ansi Console](http://mihai-nita.net/java/#ePluginAEC) ([update site](http://www.mihai-nita.net/eclipse))

* [NodeJs](http://nodejs.org/) with

    * [Karma](http://karma-runner.github.io/0.10/index.html)

The code used on this sample is based on my past attempts of using Karma (see [A small AngularJS Jasmine test executed by KarmaJS](http://blog.diniscruz.com/2013/06/a-small-angularjs-jasmine-test-executed.html) ,  [Running KarmaJS's AngularJS example test/e2e/angular-scenario (on Chrome)](http://blog.diniscruz.com/2013/06/running-karmas-angularjs-example.html) and [KarmaJS related posts](http://blog.diniscruz.com/search/label/KarmaJS))

Although the AngularJS and NodeJs Eclipse plugins provide nice helpers and views, they didn't provide (yet) the kind of UI that I was looking for. Namely they didn't support the use of KarmaJS to run AngularJS tests.

But since I now have the ability to quickly manipulate and create new Eclipse views without restarting Eclipse (using the [Groovy REPL script environment ](http://marketplace.eclipse.org/content/eclipse-grovy-repl-scripting-environment)) it was not very hard to create the UI that I wanted (see [Eclipse Plugin that allows the execution of REPL Groovy Scripts (in the current Eclipse Instance) and Fluent API for Eclipse+SWT](http://blog.diniscruz.com/2014/01/eclipse-plugin-that-allows-execution-of.html)).

Basically the brief was to:  


  * Create new (Eclipse) view with a browser showing _http://localhost:9879/__karma/ _(the KarmaJs browser runner/hook)
  * Create new view with _**a browser showing http://localhost:9879/index.html**_ (the AngularJS page)
  * Create new view with a browser showing _http://localhost:9879/__karma/debug.html _(debug view of Karma runner), with an toolbar button to refresh it.

Here is [the gist](https://gist.github.com/DinisCruz-Dev/9186835#file-eclipse_karma_views-groovy) with the code that creates this 3 Eclipse views:

Hopefully this [Groovy](http://groovy.codehaus.org/) script is easier to read (the idea of the Fluent API that I added to the Groovy REPL was allow the easy reading and understanding of scripts like this).

**1) Setting up the environment**

Now lets look at how this environment was setup:

We start with a simple AngularJS project test page that will just show the model-binding capabilities of AngularJS (yes I know that all those JS files should be in separate folders :) )  

[![](images/Screen_Shot_2014-02-24_at_11_44_12.png)](http://3.bp.blogspot.com/-nZm5S1oTx5Q/Uws9SBiPKtI/AAAAAAAAHWI/GbOHCToPjAE/s1600/Screen+Shot+2014-02-24+at+11.44.12.png)

Then I opened up [Groovy REPL script environment](http://marketplace.eclipse.org/content/eclipse-grovy-repl-scripting-environment)_ _and wrote [the script](https://gist.github.com/DinisCruz-Dev/9186835#file-eclipse_karma_views-groovy) (shown above) that creates the multiple views:

[![](images/Screen_Shot_2014-02-24_at_11_45_28.png)](http://3.bp.blogspot.com/-xHff1kwX4bI/Uws9SNCsQgI/AAAAAAAAHWQ/kdC5rZCP3zw/s1600/Screen+Shot+2014-02-24+at+11.45.28.png)

  
Clicking on _Execute _will create 3 views:

a) the **_Karma Runner_** view:

[![](images/Screen_Shot_2014-02-24_at_11_49_30.png)](http://1.bp.blogspot.com/-mwUWdXqS6mY/Uws9TAiebFI/AAAAAAAAHWo/C_i-7FTwllo/s1600/Screen+Shot+2014-02-24+at+11.49.30.png)

b) the **_Website _**view:

[![](images/Screen_Shot_2014-02-24_at_11_49_24.png)](http://1.bp.blogspot.com/-hzQ7Gvy_zgc/Uws9S02Il6I/AAAAAAAAHWY/GIr8TBFgJWY/s1600/Screen+Shot+2014-02-24+at+11.49.24.png)
  
c) the **_Karma Runner_** **_- debug_** view:

[![](images/Screen_Shot_2014-02-24_at_11_49_38.png)](http://3.bp.blogspot.com/--U_jt8hMCP0/Uws9UXesH0I/AAAAAAAAHXY/5s6GaBXtERg/s1600/Screen+Shot+2014-02-24+at+11.49.38.png)
  
... which (as seen in the first screenshot of this post) looks like this:

[![](images/Screen_Shot_2014-02-24_at_12_46_54.png)](http://1.bp.blogspot.com/-XBiLq8A498k/Uws_Xn2LheI/AAAAAAAAHZk/yAr1W30Avl8/s1600/Screen+Shot+2014-02-24+at+12.46.54.png)

Part of this UI (but not created using the Groovy script) is an Eclipse _Console _with the _'Karma Runner process'_ **_console_** **out **:

[![](images/Screen_Shot_2014-02-24_at_11_49_52.png)](http://4.bp.blogspot.com/-sbZ6pMlme-E/Uws9UbJOGGI/AAAAAAAAHW8/3rTNkCXe5_k/s1600/Screen+Shot+2014-02-24+at+11.49.52.png)

  
The AngularJS tests were executed when the **_Karma Runner_** view was opened, because the Karma process (configured via Karma.config.js) is set to wait for new browser's hooks/runners and (on connection or code changes) execute the configured tests.

**2) Making changes to existing tests**  

To see Karma in action, let's make a test fail :)

The current AngularJS page is basically just echoing/binding the contents of the **_Name_** TextBox into the **_H1_** tag:

[![](images/Screen_Shot_2014-02-24_at_12_03_39.png)](http://1.bp.blogspot.com/-HEcpOQNTTiA/Uws9UQqSZAI/AAAAAAAAHW4/39ybURAhEfg/s1600/Screen+Shot+2014-02-24+at+12.03.39.png)
  
Here is the test that is currently being executed, which is an e2e test that runs on the browser (just like Selenium or Watin).

[![](images/Screen_Shot_2014-02-24_at_12_03_53.png)](http://4.bp.blogspot.com/-lsvUjkbUxOI/Uws9U_eseSI/AAAAAAAAHXE/rtekBqlA8i8/s1600/Screen+Shot+2014-02-24+at+12.03.53.png)
  
Hopefully this type of Fluent API is easy to read:

  * browser navigates to **_/index.html_**
  * value is inserted into the **_yourName_** input field (the TextBox)
  * the value of the binded element (**_.ng-binding_**) is checked to see if it matches
  
To make this test fail, let's change just the **yourName **value:

[![](images/Screen_Shot_2014-02-24_at_13_28_02.png)](http://3.bp.blogspot.com/-EzE-pSCrNYU/UwtI9GWTHjI/AAAAAAAAHZ0/sMZqE4v5WP8/s1600/Screen+Shot+2014-02-24+at+13.28.02.png)
  
Immediately after saving the test with the changes shown above, Karma refreshes the hooked browsers in order to trigger the execution of the tests.

And as the image below will show, there is now one failed test:

[![](images/Screen_Shot_2014-02-24_at_12_04_10.png)](http://3.bp.blogspot.com/-hdl1Y8IQW-c/Uws9VIgz2jI/AAAAAAAAHXU/xZjDLUynC_A/s1600/Screen+Shot+2014-02-24+at+12.04.10.png)
  
In cases like this, the _**Karma Runner - debug** _is very useful since it will show more details on what happened, and where the test failed:

[![](images/Screen_Shot_2014-02-24_at_12_04_27.png)](http://4.bp.blogspot.com/-HSszFz4XYvg/Uws9VhFP7MI/AAAAAAAAHXQ/72LUUZJVsRg/s1600/Screen+Shot+2014-02-24+at+12.04.27.png)
  
Just to confirm that the page is actually being loaded and the tests are happening in a real browser instance, if we add an Javascript alert to the current test:

[![](images/Screen_Shot_2014-02-24_at_12_05_58.png)](http://2.bp.blogspot.com/-rewxh0k-WEI/Uws9WfwL_bI/AAAAAAAAHXo/IbKN8wLyisQ/s1600/Screen+Shot+2014-02-24+at+12.05.58.png)
  
... we will get an alert box in the  **Karma Runner - debug** (note that on the screenshot below we' are seeing the image of the final state of execution of the previous test (in this case the _'A small Angular Test'_)

[![](images/Screen_Shot_2014-02-24_at_12_05_41.png)](http://3.bp.blogspot.com/-zwhn5Ki1MUE/Uws9WYqb-8I/AAAAAAAAHXw/o9lcJNOtXEo/s1600/Screen+Shot+2014-02-24+at+12.05.41.png)
  
**3) Hooking multiple browsers and only failing on Firefox**  

In order to run the tests in multiple browsers all we need to do is to open the _http://localhost:9879/__karma/ _page (in the target browser), and a test execution will be triggered.

Note how on the image below:  

  * Eclipse is in the background (containing the views previously created and showing the **_console out_** of the Karma test runner process)
  * There are 3 stand lone browser windows (Chrome, Safari and Firefox)
  * Firefox (top most window) shows the tests being executed (in green the test executed, in yellow the test being executed)

[![](images/Screen_Shot_2014-02-24_at_12_10_11.png)](http://4.bp.blogspot.com/-LfE9SE8OByY/Uws9XZG7FbI/AAAAAAAAHYQ/wYFGASgwEIE/s1600/Screen+Shot+2014-02-24+at+12.10.11.png)
  
After execution, a quick look at the Karma runner shows that the modified test failed (as expected) on all browsers:

[![](images/Screen_Shot_2014-02-24_at_12_12_07.png)](http://3.bp.blogspot.com/-9MUkeoQjECw/Uws9XuW5s5I/AAAAAAAAHX4/kV8uiSk4-jk/s1600/Screen+Shot+2014-02-24+at+12.12.07.png)
  
Just to make sure all is working as expected, let's create a test that will fail only in one browser.

For example Firefox is the only one that has defined the **_navigator.userAgent.contains_** Javascript function (so we can use this to detect Firefox, and create a test that will only fail if executed inside it):

[![](images/Screen_Shot_2014-02-24_at_12_28_17.png)](http://4.bp.blogspot.com/-43cAX851e78/Uws9XsWy-7I/AAAAAAAAHYM/iLe_SVKQcdY/s1600/Screen+Shot+2014-02-24+at+12.28.17.png)
  
After saving the changes, the tests will be executed on all 4 browsers, with the one test that failed being the one executed in Firefox:

[![](images/Screen_Shot_2014-02-24_at_12_29_03.png)](http://3.bp.blogspot.com/-3UFj2UMcqM4/Uws9YmU4M5I/AAAAAAAAHYw/7nCtnOi7iXI/s1600/Screen+Shot+2014-02-24+at+12.29.03.png)

Refreshing the Firefox debug runner, shows the failed test and assert:

[![](images/Screen_Shot_2014-02-24_at_12_28_37.png)](http://2.bp.blogspot.com/-a2xV45BYzfk/Uws9YNgro3I/AAAAAAAAHYI/qH1H-kQT1fw/s1600/Screen+Shot+2014-02-24+at+12.28.37.png)

**4) Setup**  

In addition to creating the views programatically, I also setup an Eclipse**_ Run configurations_** for **_NodeJS_** and an _External Tools Configuration _for **_KarmaJS_**.

The NodeJS configuration was done here:

[![](images/Screen_Shot_2014-02-24_at_12_29_24.png)](http://3.bp.blogspot.com/-Q0OcbsI5HfE/Uws9Y1RIEuI/AAAAAAAAHYk/YPnhYAYce8c/s1600/Screen+Shot+2014-02-24+at+12.29.24.png)

... where I created a Node Application runner that was pointed to **_server.js_**

[![](images/Screen_Shot_2014-02-24_at_12_29_39.png)](http://4.bp.blogspot.com/-5r_O_qTnHVM/Uws9ZFcugfI/AAAAAAAAHYc/Xps7VhSzQwE/s1600/Screen+Shot+2014-02-24+at+12.29.39.png)

  
... which contains a simple NodeJS web server (we could also had used NodeJS Express, but that would had added a lot of other 'stuff' to this project)

[![](images/Screen_Shot_2014-02-24_at_12_30_18.png)](http://1.bp.blogspot.com/-hsi-QQQmQiM/Uws9ZV8H1UI/AAAAAAAAHYs/ZoAsyn-DsPA/s1600/Screen+Shot+2014-02-24+at+12.30.18.png)
  
The KarmaJS config was done as an **_External Tools Configuration_**

[![](images/Screen_Shot_2014-02-24_at_12_30_35.png)](http://2.bp.blogspot.com/-tL5uEOAAh20/Uws9Z8v9j0I/AAAAAAAAHZU/9neXImQY3h4/s1600/Screen+Shot+2014-02-24+at+12.30.35.png)

... where I simply run the **_start.sh_** bash file

[![](images/Screen_Shot_2014-02-24_at_12_31_57.png)](http://4.bp.blogspot.com/-nJ-oayXQ44s/Uws9aGSCH1I/AAAAAAAAHY4/QCwS12CqUUo/s1600/Screen+Shot+2014-02-24+at+12.31.57.png)
  
... which starts **_KarmaJS_**:

[![](images/Screen_Shot_2014-02-24_at_12_32_11.png)](http://3.bp.blogspot.com/-O_gJinPUnSw/Uws9abnJgXI/AAAAAAAAHZM/dQhy1Y2-z8M/s1600/Screen+Shot+2014-02-24+at+12.32.11.png)

... using this simple **_karma.conf.js c_**onfiguration

[![](images/Screen_Shot_2014-02-24_at_12_32_32.png)](http://1.bp.blogspot.com/-b1W-DKbvmnY/Uws9a57QbyI/AAAAAAAAHZE/ytPLVnt7fks/s1600/Screen+Shot+2014-02-24+at+12.32.32.png)
  
Note: I started the Karma process like this because there was an issue with **_KarmaJS_** finding the **NodeJS **executable from Eclipse (and at the time I didn't had time to debug why that was happening)  

**External References:**

  * [AngularJS docs on E2E Testing](http://docs.angularjs.org/guide/dev_guide.e2e-testing) 
  * [AngularJS Testing with Karma and Jasmine](http://www.tuesdaydeveloper.com/2013/06/angularjs-testing-with-karma-and-jasmine/) 
  * [Test runners for AngularJS - how to run the tests from eclipse IDE and CI server without too much complication?](http://stackoverflow.com/questions/21673376/test-runners-for-angularjs-how-to-run-the-tests-from-eclipse-ide-and-ci-server) 
  * [How to run KarmaJS from Eclipse](http://litebyte.net/blog/how-to-run-karmajs-from-eclipse/) 
  * [Setting-up AngularJS, Angular Seed, Node.js and Karma](http://bardevblog.wordpress.com/2013/07/28/setting-up-angularjs-angular-seed-node-js-and-karma/) 
  * [Can't run e2e tests with karma (for angular)](http://stackoverflow.com/questions/17408104/cant-run-e2e-tests-with-karma-for-angular) 





- - - - 
[Table of Contents](../Table_of_contents.md) | [Code](../Code)