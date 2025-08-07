<!-- 220504.104939 -->

# Hosting custom myAvatar™ web services

>Last updated: May 3, 2022 by [Chris Banwarth](https://github.com/APrettyCoolProgram)

***

### CONTENTS

[Overview](#hosting-overview)<br>
[Using Microsoft IIS to host a custom web service](#using-microsoft-iis-to-host-a-custom-web-service)<br>

***

# Overview

In order to use any web service that interfaces with myAvatar™, that web service needs to be ***hosted*** at a location that myAvatar™ has access to

There are two options for hosting a custom web service:

1. **Have Netsmart host your custom web service**<br>
If your myAvatar™ environments are hosted by Netsmart, they can also host your custom web services. If you choose to have Netsmart host your custom web service, you can skip the rest of this document and contact them to set things up.

2. **Self-host your custom web service**<br>
If you self-host your myAvatar™ environments, or would rather have complete control over your custom web services, you can self-host them. This document will walk you through the process of doing that.

# Using Microsoft IIS to host a custom web service

You can probably host your custom web service using many web server/operating systems combinations, but these guidelines will focus on getting setup on Microsoft IIS.

These are the steps that I used - twice! - to host a custom web service in our environment, but they are more of a *guideline* than a perfect set of instructions. It's quite possible that I didn't follow best-practices, or maybe I have something setup incorrectly, so please use caution when following these steps. And since I (hopefully?) won't have to do this again, this section will probably not be updated.

### PLEASE NOTE

* This document assumes that you already have a IIS version 10 up and running.
* Keep in mind that myAvatar™ can only communicate with web services via the HTTPS:// protocol.

## Creating an Application Pool

I’m not sure this step is necessary, but it helps to make things a little more organized…maybe? I’m not an IIS expert, so I’m not sure.

From within IIS:
1. Right-click the **Application Pools** connection
2. Choose **Add Application Pool…**

The new application pool should be a **".NET 4.0 CLR (.NET 4.5)"** pool. I’ve chosen .NET 4.5, since it lines up with the Netsmart ScriptLink Objects that we will be using.

I’ve named the application pool *AvatoolWebService*.

<h6 align="center">

  <img src="resource/image/readme/iis-application-pool-633x187.png" width="633">
  <br>
  What my Application Pools setup looks like
  <br>

</h6>

## Creating a new site

From within IIS:
1. Right-click the **Sites** connection
2. Choose **Add Website**
3. The **Site name** should be: *AvatoolWebService*
4. The **Application pool** should be: *AvatoolWebService*
5. The **Physical path** should be: */path/to/your/files/*
6. Set the binding for port :80
6. Set the binding for port :443

<h6 align="center">

  <img src="resource/image/readme/iis-add-website-362x414.png" width="362">
  <br>
  Adding a new website
  <br>

</h6>

## Installing the ASP.NET role

ASP.NET is required by Web Services, so add the ASP.NET role to IIS.

Once that’s done, your IIS roles should look like this:

<h6 align="center">

  <img src="resource/image/readme/iis-roles-295x650.png" width="295">
  <br>
  Probably?
  <br>

</h6>

## Disabling the default site

Might as well do this? Probably?

From within IIS:
1. Right-click the Default Web Site
2. Choose **Manage Web Site**
3. Choose **Stop**

## Enabling directory browsing

From within IIS:
1. Double-click on the **Directory Browsing** icon
2. Choose **Enable**
3. Click **Apply**

<h6 align="center">

  <img src="resource/image/readme/iis-directory-browsing-633x204.png" width="633">
  <br>
  Enabling directory browsing
  <br>

</h6>

## Verifying the new site

Your AvatoolWebService site should look like this:

<h6 align="center">

  <img src="resource/image/readme/iis-site-home-633x206.png" width="633">
  <br>
  Maybe?
  <br>

</h6>

At this point, you should be able to point a browser to your website, and see the landing page.