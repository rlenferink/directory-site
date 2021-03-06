---
title: Installing Apache Directory Studio in Eclipse
---

# Installing Apache Directory Studio in Eclipse

> **Note:**
>
> The Apache Directory Studio plugins require Java 8 or newer and a recent Eclipse version.

From workbench menu choose **Help > Install New Software...**.

<center>![Help -> Install New Software...](installation-in-eclipse.data/1-menu.png)</center>

In the opened wizard input `https://directory.apache.org/studio/update` into the **Work with:** text field and press **Enter**.


After a while the table below will show the available categories.

Choose **Apache Directory Studio**. You don't need to choose **Apache Directory Studio Dependencies**, the required dependencies will be automatically installed if required. Click **Next**.

<center>![Available Software](installation-in-eclipse.data/2-available-software.png)</center>

Review the installation details and click **Next**.

<center>![Install Details](installation-in-eclipse.data/3-install-details.png)</center>

Accept the license agreement, Apache Directory Studio is licensed under the Apache License, Version 2.0. Click **Finish**.

<center>![Review Licenses](installation-in-eclipse.data/4-review-licenses.png)</center>

Apache Directory Studio plugins are not signed yet, so you have to agree to the warning.

<center>![Warning](installation-in-eclipse.data/5-warning.png)</center>

You also have to trust the JCE Code Signing CA.

<center>![Certificates](installation-in-eclipse.data/6-certificates.png)</center>

After installation it is recommended to restart Eclipse.

<!--

<center>![Download](installation-in-eclipse.data/gettingstarted_install_1.png)</center>

Next, please specify the Apache Directory Studio update site. Click the **New Remote Site...** button. In the dialog input the following and press **OK**:

Name: **Apache Directory Studio Update Site**
URL: **[https://directory.apache.org/studio/update](https://directory.apache.org/studio/update)**

<center>![Download](installation-in-eclipse.data/gettingstarted_install_2.png)</center>

Make sure the new update site is checked an press **Finish**.

<center>![Download](installation-in-eclipse.data/gettingstarted_install_3.png)</center>

Now the install manager checks the update site and presents the search results. Select the feature you want to install and click **Next**.
In our example, we have selected the LDAP Browser.

<center>![Download](installation-in-eclipse.data/gettingstarted_install_4.png)</center>

Accept the license agreement, the Apache Directory Studio Browser is distributed under the Apache License, Version 2.0 and click **Next**.

<center>![Download](installation-in-eclipse.data/gettingstarted_install_5.png)</center>

In the next dialog ensure that the Apache Directory Studio features you have choosen are selected (here the LDAP Browser) and click to **Finish**.

<center>![Download](installation-in-eclipse.data/gettingstarted_install_6.png)</center>

Now the install manager loads the necessary files. When download is finished you have to verify the installation, please click to **Install**.

<center>![Download](installation-in-eclipse.data/gettingstarted_install_7.png)</center>

After installation it is recommended to restart the Eclipse workbench.

-->
