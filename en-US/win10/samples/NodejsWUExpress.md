---
layout: default
title: NodejsWU
permalink: /en-US/win10/samples/NodejsWUExpress.htm
lang: en-US
---

##Express Node.js (Windows Universal) Sample


###Set up your PC
* Follow the instructions [here]({{site.baseurl}}/{{page.lang}}/win10/SetupPC.htm) to install Visual Studio 2015 Preview.
* Install the latest NTVS (Node.js Tools for Visual Studio) Bundle VS 2015 from [here](https://github.com/ms-iot/ntvsiot/releases).
* Install Node.js on your machine from [here](https://nodejs.org/download/). Ensure that you select 'npm package manager' as one of the features to be installed.


###Create a new Express (Windows Universal) project
Start Visual Studio 2015 RC and create a new project (File \| New Project...). In the `New Project` dialog, navigate to `Node.js` as shown below (in the left pane in the dialog: Templates \| JavaScript \| Node.js).

Select the template `Basic Node.js Express 4 Application (Windows Universal)`

![Node.js Windows Universal New Express Project Dialog]({{site.baseurl}}/images/Nodejs/nodejswuexpress-newprojectdialog.PNG)

When the new project is created, you will see the dialog shown below asking if you want to use npm to install Express and its dependencies to the location of the project. Click Yes.

![npm Prompt]({{site.baseurl}}/images/Nodejs/npm-prompt.PNG)

After clicking yes, npm will run in the background and install the dependencies. Once that is complete, your project should look like the picture shown below.

![npm Express List]({{site.baseurl}}/images/Nodejs/npm-express.PNG)


###Deploy the server to your Windows IoT Core device
* Go to the Project menu and select '<Your project name> Properties.' You could also right-click on the project node in solution explorer to access Properties.
* Enter the IP Address in the Remote Machine text box as shown below (the `--debug` argument is required for debugging and is added automatically).
* You can also add `--use-logger` as an argument to redirect console output to a file in the local storage folder of the UWP application
  (C:\Users\DefaultAccount\AppData\Local\Packages\&lt;Your Project Name&gt;_&lt;Publisher Hash String&gt;\LocalState\nodeuwp.log).
* If you're building for Minnowboard Max, select `x86` in the dropdown.  If you're building for Raspberry Pi 2, select `ARM`.

    ![Node.js Windows Universal Project Properties]({{site.baseurl}}/images/Nodejs/nodejswu-properties.png)

* Now we're ready to deploy to the remote Windows IoT Core device. Simply press F5 (or select Debug \| Start Debugging) to start debugging the server.

* When the server is running, open up a browser and enter the address http://&lt;IP address of your device&gt;:3000. The result should look like the picture below.

    ![Hello World Result]({{site.baseurl}}/images/Nodejs/express-ie.PNG)


### GitHub
* NTVS IoT Extension source code: [https://github.com/ms-iot/ntvsiot](https://github.com/ms-iot/ntvsiot)
* Node.js UWP wrapper source code: [https://github.com/ms-iot/node-uwp-wrapper](https://github.com/ms-iot/node-uwp-wrapper)
