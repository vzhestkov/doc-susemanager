---
title: Setup via YaST
keywords: setup, yast
last_updated: June 27, 2017
sidebar: sumadoc-31_sidebar
permalink: gs-setup-via-yast.html
folder: suse-mgr3.1/getting-started/mgr-setup
---

## SUSE Manager Setup via YaST {#suse-manager-setup-via-gui}

Procedure 1.1. SUSE Manager Setup

This section will guide you through SUSE Manager setup procedures.

- Log in to the SUSE Linux Enterprise 12 desktop and start the YaST SUSE Manager Setup module: Either click Applications+System Tools+YaST and enter SUSE Manager Setup, or open a terminal and as `root` type **yast2 susemanager_setup** to initiate the setup.

- On the initial screen select Setup SUSE Manager from scratch and select Next to continue.

- Enter an email address which will receive notifications about the server&#039;s status. The number of emails sent from SUSE Manager can be extensive, therefore notifications via email may be disabled from the Web UI after setup if desired. If wanted, enable advertising SUSE Manager via SLP; this can simplify client setup.

- Select Next to continue.

- Enter your certificate information and a password. The password should be stored in a secure location. Select Next to continue.
{% include warning.html content="Without this password it will be impossible to setup a SUSE Manager Proxy Server." %}

{% include image.html file="quickstart-mgr-setup4.png" alt="something different" caption="This is a sample caption" %}


- In Database Settings, enter a database user and password. This password should be stored in a secure location. Select Next to continue.

{% include image.html file="quickstart-mgr-setup5.png" alt="something different" caption="This is a sample caption" %}


- SUSE Manager requires that you connect to SUSE Customer Center for software, updates and patches. You will be unable to synchronize or provide channels to your clients without this information. Enter your SUSE Customer Center `Organization Credentials`. You may open [https://scc.suse.com/login](https://scc.suse.com/login) to register or access to your organization credentials. Select `Next` to continue.

{% include image.html file="quickstart-mgr-setup6.png" alt="something different" caption="This is a sample caption" %}


- Select Yes to run setup when prompted. When completed select `Next` to continue.

- You will be shown your new SUSE Manager Web UI address. Select Finish to complete SUSE Manager setup.

<span class="label label-info">MISSING LINK</span>
In [the section called “Creating the Organization with the Administrator&#039;s Account”](creating_the_organization_with_the_administrators_.md), you will create the administrator&#039;s account and synchronize with SUSE Customer Center.