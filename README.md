# NextGen Connect Integration Engine (formerly Mirth Connect)
#  我们在原来的基础上，增加了对中文的支持：
# 包括： 通道名称支持中文，修改了显示字体，解决显示中文乱码处里。
# easy

1. [General Information](#general-information)
2. [Installation and Upgrade](#installation-and-upgrade)
3. [Starting Mirth Connect](#starting-mirth-connect)
4. [Running Mirth Connect in Java 9 or greater](#java9)
5. [License](#license)
6. [More Information](#more-information)

------------

<a name="general-information"></a>
## 1. General Information
##### The Mirth Solutions Mission
Mirth Solutions help many of the nation&apos;s largest, most respected healthcare entities streamline their care-management processes to satisfy the demands of a regulatory, competitive healthcare industry. With Mirth Solutions, NextGen Healthcare&apos;s goal is to provide the healthcare community with a secure, efficient, cost-effective means of sharing health information. The natural product of this aim is a family of applications &mdash; which includes Mirth Connect &mdash; flexible enough to manage patient information, from small practices to large HIEs, so our clients and users can work confidently and effectively within the healthcare-delivery system.
##### About Mirth Connect
Like an interpreter who translates foreign languages into the one you understand, Mirth Connect translates message standards into the one your system understands. Whenever a &quot;foreign&quot; system sends you a message, Mirth Connect&apos;s integration capabilities expedite the following:
- Filtering &mdash; Mirth Connect reads message parameters and passes the message to or stops it on its way to the transformation stage.
- Transformation &mdash; Mirth Connect converts the incoming message standard to another standard (e.g., HL7 to XML).
- Extraction &mdash; Mirth Connect can &quot;pull&quot; data from and &quot;push&quot; data to a database.
- Routing &mdash; Mirth Connect makes sure messages arrive at their assigned destinations.

Users manage and develop channels (message pathways) using the interface known as the Administrator:
![Administrator screenshot](https://i.imgur.com/tnoAENw.png)

------------

<a name="installation-and-upgrade"></a>
## 2. Installation and Upgrade
Mirth Connect installers are available for individual operating systems (.exe for Windows, .rpm and .sh for Linux, and .dmg for Mac OS X). Pre-packaged distributions are also available for individual operating systems (ZIP for Windows, tar.gz for Linux, and tar.gz for Mac OS X). The installer allows you to automatically upgrade previous Mirth Connect installations (starting with version 1.5).

Mirth Connect installers also come with the option to install and start a service which will run the background. You also have the option of installing and running the Mirth Connect Server Manager, which allows you to start and stop the service on some operating systems, change Mirth Connect properties and backend database settings, and view the server logs.

An optional Mirth Connect Command Line Interface can be installed, allowing you to connect to a running Mirth Connect Server using a command line. This tool is useful for performing or scripting server tasks without opening the Mirth Connect Administrator.

After the installation, the Mirth Connect directory layout will look as follows:

- /appdata/mirthdb: The embedded database (Do NOT delete if you specify Derby as your database). This will be created when the Mirth Connect Server is started. The path for appdata is defined by the dir.appdata property in mirth.properties.
- /cli-lib: Libraries for the Mirth Connect Command Line Interface (if installed)
- /client-lib: Libraries for the Mirth Connect Administrator
- /conf: Configuration files
- /custom-lib: Place your custom user libraries here. These libraries will be loaded on the Mirth Connect Server classpath when it is started, making them accessible to channel scripts.
- /docs: This document and a copy of the Mirth Connect license
- /docs/javadocs: Generated javadocs for the installed version of Mirth Connect. These documents are also available when the server is running at `http://[server address]:8080/javadocs/` (i.e. `http://localhost:8080/javadocs/`).
- /extensions: Libraries and meta data for Plug-ins and Connectors
- /logs: Default location for logs generated by Mirth Connect and its sub-components
- /manager-lib: Libraries for the Mirth Connect Server Manager (if installed)
- /public_html: Directory exposed by the embedded web server
- /server-lib: Mirth Connect server libraries
- /webapps: Directory exposed by the embedded web server to host webapps

------------

<a name="starting-mirth-connect"></a>
## 3. Starting Mirth Connect
Once Mirth Connect has been installed, there are several ways to connect to launch the Mirth Connect Administrator. On a Windows installation, there is a Mirth Connect Administrator item in the Start Menu which launches the application directly.

If the option is not available, you can connect to the Mirth Connect Administrator launch page which by default should be available at `http://[server address]:8080` (i.e. `http://localhost:8080`). Clicking the Launch Mirth Connect Administrator button will connect you to the server which will be listening on `https://[server address]:8443` (i.e. `https://localhost:8443`). If running a new installation, the default username and password for the login screen is admin and admin. This should be changed immediately for security purposes.

If you are launching the administrator for the first time, you will notice that the libraries for the Mirth Connect Administrator will be loaded. This feature allows you run the Administrator from any remote Mirth Connect server without having to download and install a separate client.

You may also notice a security warning when starting the administrator (dialog box depends on browser being used). This is because by default Mirth Connect creates a self-signed certificate for its web server. For now click Run to continue launching the administrator, but check out the User Guide for instructions on how to replace the certificate.

------------

<a name="java9"></a>
## 4. Running Mirth Connect in Java 9 or greater
In order to run Mirth Connect in Java 9 or greater, copy the options from `docs/mcservice-java9+.vmoptions` and append them to either mcserver.vmoptions or mcservice.vmoptions, depending on your deployment. Then restart Mirth Connect.

To run the Mirth Connect Command Line Interface, create a new file named mccommand.vmoptions in the Mirth Connect root directory. Copy all of the options from `docs/mcservice-java9+.vmoptions` into mccommand.vmoptions and save before launching the Command Line Interface.

------------

<a name="license"></a>
## 5. License
Mirth Connect is released under the [Mozilla Public License version 1.1](https://www.mozilla.org/en-US/MPL/1.1/ "Mozilla Public License version 1.1"). You can find a copy of the license in `server/docs/LICENSE.txt`.

All licensing information regarding third-party libraries is located in the `server/docs/thirdparty` folder.

------------

<a name="more-information"></a>
## 6. More Information
Download Mirth Connect and the official User Guide at: https://www.mirth.com

View the release notes, upgrade guide, FAQs, and examples at: https://www.mirthcorp.com/community/wiki/display/mirth/Home

Join the Mirth Community Forums at: https://www.mirthcorp.com/community/registration

Our public Slack group is located at: https://mirthconnect.slack.com/. You can join up here: https://mirthconnect.herokuapp.com
