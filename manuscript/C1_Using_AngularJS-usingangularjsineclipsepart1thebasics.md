##  Using AngularJS in Eclipse, Part 1) The Basics 

This is the first of four posts on how to run (inside Eclipse) the examples provided in [AngularJS](http://angularjs.org/http://angularjs.org/)'s home page:  

* Using AngularJS in Eclipse, Part 1) The Basics
* [Using AngularJS in Eclipse, Part 2) Add Some Control](/manuscript/C1_Using_AngularJS-usingangularjsineclipsepart2addsomecontrol.md)
* [Using AngularJS in Eclipse, Part 3) Wire up a Backend](/manuscript/C1_Using_AngularJS-usingangularjsineclipsepart3wireupabackend.md)
* [Using AngularJS in Eclipse, Part 4) Create Components](/manuscript/C1_Using_AngularJS-usingangularjsineclipsepart4createcomponents.md)

The example covered on this post is the _**The Basics.**_  

I'm doing this on an OSX laptop and the first step was to download and unzip ([eclipse-standard-kepler-SR1-macosx-cocoa.tar.gz](http://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/kepler/SR1/eclipse-standard-kepler-SR1-macosx-cocoa.tar.gz) (32bit version of Eclipse's Kerpler) into the **_~/_Dev/_AngularJS_** folder.

I fired up eclipse, chose the _~/_Dev/_AngularJS/workspace_ as the workspace root and installed the [Eclipse Grovy REPL Scripting Environment 1.6.0](https://marketplace.eclipse.org/content/eclipse-grovy-repl-scripting-environment) ([update site](http://eclipse-plugin-builder.azurewebsites.net/)) and [Angular-JS Eclipse Tooling](https://github.com/angelozerr/angularjs-eclipse) ([update site](http://oss.opensagres.fr/angularjs-eclipse/1.0.0-SNAPSHOT/)) plugins.

  
**1) Creating an Angular JS Project**  

After restarting eclipse, I right-clicked on the **_Project Explorer_** view and chose the **_New_** -> **_Static Web Project_** menu item

[![](images/Screen_Shot_2014-02-19_at_16_38_43.png)](http://1.bp.blogspot.com/-B56lO0g6zwU/UwT3bmHMyGI/AAAAAAAAG5g/obPhZ5coWD0/s1600/Screen+Shot+2014-02-19+at+16.38.43.png)
  
... set **_AngularJS_Tests_** as the project name and clicked **_Finish_**

[![](images/Screen_Shot_2014-02-19_at_16_39_32.png)](http://2.bp.blogspot.com/-ZhxlaymwSS4/UwT3bntfzpI/AAAAAAAAG5c/kHEzhp8An3o/s1600/Screen+Shot+2014-02-19+at+16.39.32.png)

... switched to the **_Web Perspective_**

[![](images/Screen_Shot_2014-02-19_at_16_39_57.png)](http://3.bp.blogspot.com/-pRBNqa_-K70/UwT3btXOHtI/AAAAAAAAG5k/1OYo1Wheozg/s1600/Screen+Shot+2014-02-19+at+16.39.57.png)
  
... with the **_Project Explorer_** view now looking like this:

[![](images/Screen_Shot_2014-02-19_at_16_40_53.png)](http://2.bp.blogspot.com/-vUmO4KWEeCk/UwT3elCZ6KI/AAAAAAAAG6g/_aH6OZa9v5A/s1600/Screen+Shot+2014-02-19+at+16.40.53.png)
  
With the final setup being the conversion into an **_AngularJS Project_**

[![](images/Screen_Shot_2014-02-19_at_16_41_04.png)](http://1.bp.blogspot.com/-dzwplDIMxb0/UwT3cdjBDKI/AAAAAAAAG54/2byieoOAs9M/s1600/Screen+Shot+2014-02-19+at+16.41.04.png)

**2) Creating the The_Basics.html file**  

To create the first test file, I right-clicked on the _Web Content_ folder, and chose the _New _-> _Html File_ menu option:

[![](images/Screen_Shot_2014-02-19_at_16_41_54.png)](http://3.bp.blogspot.com/-UQwFx9Pcu7o/UwT3cp2EJoI/AAAAAAAAG5w/HOw6n4w5kAg/s1600/Screen+Shot+2014-02-19+at+16.41.54.png)
  
... set the file name to _The_Basics.html_ and click on **_Finish_**

[![](images/Screen_Shot_2014-02-19_at_16_47_16.png)](http://1.bp.blogspot.com/-DKxJ3nFj4m4/UwT3dixOjTI/AAAAAAAAG6I/SWnCUKowE_c/s1600/Screen+Shot+2014-02-19+at+16.47.16.png)

**NOTE: **The reason this first file is called _The_Basics.html_ is because I'm going to be using the examples from AngularJS' home page [http://angularjs.org/](http://angularjs.org/)

[![](images/Screen_Shot_2014-02-19_at_16_42_29.png)](http://4.bp.blogspot.com/-vXqvs93ufKA/UwT3dCrwLEI/AAAAAAAAG6A/WUsTnutGFsY/s1600/Screen+Shot+2014-02-19+at+16.42.29.png)
  
Once the _The_Basics.html _file opens up in eclipse

[![](images/Screen_Shot_2014-02-19_at_16_49_31.png)](http://2.bp.blogspot.com/-FclBKDoB6lo/UwT3dw43skI/AAAAAAAAG6Q/woQaq-hfQkc/s1600/Screen+Shot+2014-02-19+at+16.49.31.png)
  
... I change its contents to the code sample from [http://angularjs.org/](http://angularjs.org/)

[![](images/Screen_Shot_2014-02-19_at_16_50_25.png)](http://4.bp.blogspot.com/-fyWC3rSrsSo/UwT3eDJWJSI/AAAAAAAAG6Y/sjT7XrJw9VQ/s1600/Screen+Shot+2014-02-19+at+16.50.25.png)

Note how the AngularJS Eclipse plugin successfully detects the Angular attributes and showed relevant information about it.

Here is **_ng-app_**:

[![](images/Screen_Shot_2014-02-19_at_16_50_51.png)](http://3.bp.blogspot.com/-P7uYPDmj7Ok/UwT3g2zdphI/AAAAAAAAG7Q/uqM-oea5-l8/s1600/Screen+Shot+2014-02-19+at+16.50.51.png)
  
Here is **_ng-model_**:

[![](images/Screen_Shot_2014-02-19_at_16_51_08.png)](http://4.bp.blogspot.com/-KQiS1VKPVPM/UwT3e0Z11XI/AAAAAAAAG6o/C-4ykgVRmkM/s1600/Screen+Shot+2014-02-19+at+16.51.08.png)

**3) Fixing the undefined Attribute name issue**  

Since I chose to the Eclipse's **Static Web Project**, when we save the _The_Basics.html _file (and if the Eclipse's Html validation settings are the default ones), the following error will show:

[![](images/Screen_Shot_2014-02-19_at_16_51_22.png)](http://3.bp.blogspot.com/-jfY0Yk4SOYA/UwT3fDl7qBI/AAAAAAAAG60/EQN7MUJth8M/s1600/Screen+Shot+2014-02-19+at+16.51.22.png)

... which basically means that Eclipse is not recognising the AngularJS Html attributes:

[![](images/Screen_Shot_2014-02-19_at_16_51_27.png)](http://3.bp.blogspot.com/-AYADiOtSbMM/UwT3ft_lm-I/AAAAAAAAG64/JI0a-IVDPQ0/s1600/Screen+Shot+2014-02-19+at+16.51.27.png)

  
To fix this, I went to the **_AngularJS_Test _**project's Properties, opened the _HTML Syntax _page (from the **_Validation_** section) and set to false the **Undefined attribute name **setting (in the **_Attributes'_** options , not the **_Elements_**)  

[![](images/Screen_Shot_2014-02-19_at_17_08_36.png)](http://1.bp.blogspot.com/-MVLxW_PXxwo/UwT3hEVTSsI/AAAAAAAAG7Y/Q-XsYvC4s10/s1600/Screen+Shot+2014-02-19+at+17.08.36.png)
  
With that config change, there are no problems in this page, and hovering on top of one the AngularJS directives will show the correct tooltip:

[![](images/Screen_Shot_2014-02-19_at_17_09_28.png)](http://4.bp.blogspot.com/-H4MjXZg2SMc/UwT3hvbU0yI/AAAAAAAAG7g/P4mHFJIMvO0/s1600/Screen+Shot+2014-02-19+at+17.09.28.png)

**4) Viewing and previewing the **_The_Basics.html page_

Since at the moment we only have one page, we can view it directly without needing a Web Server.

To do that, I clicked on the html file and chose the **_Web Browser_** option from the **_Open With_** menu:

[![](images/Screen_Shot_2014-02-19_at_17_09_41.png)](http://2.bp.blogspot.com/-sWciFaQbqeQ/UwT3iOUtRrI/AAAAAAAAG7o/V8cwAq2N9h8/s1600/Screen+Shot+2014-02-19+at+17.09.41.png)
  
This will open the default Eclipse Browser

[![](images/Screen_Shot_2014-02-19_at_17_10_10.png)](http://1.bp.blogspot.com/-CbK66SqYCkc/UwT3iW6QfEI/AAAAAAAAG7w/dOj4I4-j8FQ/s1600/Screen+Shot+2014-02-19+at+17.10.10.png)
  
... with the AngularJS test working as expected (in this case any text typed in the **_Name_** TextBox will automatically be shown in the page:

[![](images/Screen_Shot_2014-02-19_at_17_10_21.png)](http://3.bp.blogspot.com/-RuhT5HnDH44/UwT3lGATGbI/AAAAAAAAG9E/JbSgRs1AgLI/s1600/Screen+Shot+2014-02-19+at+17.10.21.png)
  
We can also preview some of the changes in real time, by choosing the **_Web Page Editor:_**

[![](images/Screen_Shot_2014-02-19_at_17_10_46.png)](http://3.bp.blogspot.com/--Zk4Jhq1q10/UwT3i7ULY1I/AAAAAAAAG8A/hPCJY0Dhvp0/s1600/Screen+Shot+2014-02-19+at+17.10.46.png)
  
... which will look like this (note the non-processed HTML at the top and the HTML code at the bottom):

[![](images/Screen_Shot_2014-02-19_at_17_11_04.png)](http://1.bp.blogspot.com/-WoqWmXfqsDQ/UwT3jUK_V_I/AAAAAAAAG8M/c1dnxd3IKbA/s1600/Screen+Shot+2014-02-19+at+17.11.04.png)

Opening up the **_Preview_** tab (from the default **_Design_** tab) will allow us to test the page currently being edited (note how Angular JS is working):

[![](images/Screen_Shot_2014-02-19_at_17_11_23.png)](http://3.bp.blogspot.com/-2e7BA0FetAY/UwT3jjddTdI/AAAAAAAAG8Q/bxXOKRvChJE/s1600/Screen+Shot+2014-02-19+at+17.11.23.png)
  
This means that (when in the **_Design_** tab) we can edit the AngularJS HTML page and see the changes immediately:

[![](images/Screen_Shot_2014-02-19_at_17_12_13.png)](http://2.bp.blogspot.com/-N9TmY355300/UwT3kFqFOZI/AAAAAAAAG8Y/SeUGg_Tvn18/s1600/Screen+Shot+2014-02-19+at+17.12.13.png)
  
NOTE: This version of the **Web Page Editor **doesn't render the CSS while in that **_Design_** mode, which means that if we add bootstrap to this project:

[![](images/Screen_Shot_2014-02-19_at_17_23_58.png)](http://4.bp.blogspot.com/-Owx235gciTc/UwT3kc0-U3I/AAAAAAAAG8g/X95IRlvKGyQ/s1600/Screen+Shot+2014-02-19+at+17.23.58.png)
  
... the CSS will only be visible when in the **_Preview_** tab:  

[![](images/Screen_Shot_2014-02-19_at_17_24_12.png)](http://4.bp.blogspot.com/-vtCpjTUJ6HI/UwT3lFkk96I/AAAAAAAAG8o/3CJFCWUcHz0/s1600/Screen+Shot+2014-02-19+at+17.24.12.png)

**4) Creating a Git Repository for the files created**  

The best way for me to share these files is via a Git Repository, so the final step of this post is to create one on the files we have already created.

Since we are in eclipse I tried to create an Git Repo for the current project:

[![](images/Screen_Shot_2014-02-19_at_17_43_58.png)](http://2.bp.blogspot.com/-78lb7IDudvA/UwT3lfIyZhI/AAAAAAAAG9A/Pngz503zyp8/s1600/Screen+Shot+2014-02-19+at+17.43.58.png)
  
But the _Git Repository _wizard:  

[![](images/Screen_Shot_2014-02-19_at_17_44_24.png)](http://2.bp.blogspot.com/-zrzeIFi5avY/UwT3mU6UnMI/AAAAAAAAG9Y/piIfA7US_iY/s1600/Screen+Shot+2014-02-19+at+17.44.24.png)

... didn't work, because it expects the target folder to not exist:

[![](images/Screen_Shot_2014-02-19_at_17_48_31.png)](http://1.bp.blogspot.com/-2IGWLah2ODg/UwT3n0cIfhI/AAAAAAAAG9k/qk8VL68vsnA/s1600/Screen+Shot+2014-02-19+at+17.48.31.png)

This was easily solved via the command line (by executing _$ git init_ on the **_AngularJS_Tests _**folder)

[![](images/Screen_Shot_2014-02-19_at_18_22_10.png)](http://4.bp.blogspot.com/-9ilkH_K52hc/UwT3oWA1Z_I/AAAAAAAAG9w/N1B1DekFHaA/s1600/Screen+Shot+2014-02-19+at+18.22.10.png)
  
Now that we have a git repository, I was time to open it:

[![](images/Screen_Shot_2014-02-19_at_17_45_45.png)](http://1.bp.blogspot.com/-2P0K6E8UEZU/UwT3pKaG3GI/AAAAAAAAG-E/7Yw-3lIuMdM/s1600/Screen+Shot+2014-02-19+at+17.45.45.png)

... using the**_ Git Repositories_** view

[![](images/Screen_Shot_2014-02-19_at_17_46_03.png)](http://3.bp.blogspot.com/-Syxk6Em1Stg/UwT3ntsuakI/AAAAAAAAG9o/uE8XQJlK3hg/s1600/Screen+Shot+2014-02-19+at+17.46.03.png)

... where we can use the _Add an existing local Git repository_ link:

[![](images/Screen_Shot_2014-02-19_at_18_22_37.png)](http://3.bp.blogspot.com/-17VitQGxFEo/UwT3orgLBkI/AAAAAAAAG94/S8UEYWUIiMA/s1600/Screen+Shot+2014-02-19+at+18.22.37.png)

... to open the repository just created:

[![](images/Screen_Shot_2014-02-19_at_18_23_07.png)](http://4.bp.blogspot.com/-6aYeGTVpz_M/UwT3puS339I/AAAAAAAAG-I/6mTJfOI5h6c/s1600/Screen+Shot+2014-02-19+at+18.23.07.png)

In order to create a git commit, I also opened the **_Git Staging_** view:

[![](images/Screen_Shot_2014-02-19_at_18_24_16.png)](http://1.bp.blogspot.com/-QRSV4DLjj-w/UwT3qGkEHKI/AAAAAAAAG-Y/QOmiYR5Tq8g/s1600/Screen+Shot+2014-02-19+at+18.24.16.png)

This is what these two git views look like (note that there are not commits/references and the list of new files in the **Unstaged Changes **list)

[![](images/Screen_Shot_2014-02-19_at_18_25_20.png)](http://3.bp.blogspot.com/-ifymHiFLfgw/UwT3qc0ohEI/AAAAAAAAG-U/yy-EKFgBuxA/s1600/Screen+Shot+2014-02-19+at+18.25.20.png)
  
To commit the files drag-n-drop them from the **_Unstaged Changes_** to the _Staged Changes_, and write a commit message:

[![](images/Screen_Shot_2014-02-19_at_18_25_49.png)](http://3.bp.blogspot.com/-Zww7cJPHNKQ/UwT3q14aULI/AAAAAAAAG-g/my0wVqdKYXI/s1600/Screen+Shot+2014-02-19+at+18.25.49.png)

After clicking the **_Commit_** button the **_Git Repositories _**view will give a visual representation of the location current HEAD (which is the commit just done)

[![](images/Screen_Shot_2014-02-19_at_18_26_06.png)](http://2.bp.blogspot.com/-Hl9V7rKQK3w/UwT3rDepfOI/AAAAAAAAG-w/bJ0EGKxFrKo/s1600/Screen+Shot+2014-02-19+at+18.26.06.png)



- - - - 
[Table of Contents](../Table_of_contents.md) | [Code](../Code)