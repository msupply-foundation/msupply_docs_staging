+++
title = "Synchronisation"
description = "Configure the server sync settings"
date = 2022-05-17
updated = 2022-05-17
draft = false
weight = 6
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Synchronisation is the term we use to denote the process of transferring data between your server and the central server. This page covers viewing and managing the settings, viewing the current status and how to manually initiate synchronisation."
toc = true
top = false
+++

## Viewing the synchronisation settings

To view the synchronisation settings, go to `Settings` in the lower section of the navigation panel:

![admin: nav](../images/admin_nav.png)

You will see the synchronisation section below the display settings, click on this to view the options.

<div class="note">You will require the <code>Access server administration</code> permission, as noted in the <a href="../permissions/">Permissions</a> page</div>

![admin: page](images/administration.png)

## Updating settings

Be very careful updating these settings! They control how the server connects to the central server and do not usually need to be changed. If you make any changes without consulting the administrator of the central server, it is very likely that you will break the sync connection.
