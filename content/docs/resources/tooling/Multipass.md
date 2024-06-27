---
title: Multipass
weight: 1
image: "/docs/resources/tooling/images/multipass.webp"
---

![Multipass](/docs/resources/tooling/images/multipass.webp)

# Using Multipass with Windows Terminal: A Quick Setup Guide

If you're looking to run Ubuntu virtual machines effortlessly on your Windows machine, Multipass is an excellent tool to consider. It provides a lightweight VM manager that allows you to launch and manage Ubuntu instances quickly. When combined with the sleek interface of Windows Terminal, you get a powerful environment for development and testing. In this blog post, we'll walk you through setting up and configuring Multipass with Windows Terminal.

## What You'll Need

Before we dive in, ensure you have the following:

1. **Windows 10 or later**: Multipass and Windows Terminal are compatible with recent versions of Windows.
2. **winget**: The Windows Package Manager, which you can use to install Multipass and Windows Terminal.

## Step 1: Install Multipass and Windows Terminal Using winget

First, open Command Prompt or PowerShell and use winget to install Multipass and Windows Terminal:

```sh
winget install --id Canonical.Multipass -e
winget install --id Microsoft.WindowsTerminal -e
```

## Step 2: Launch Your First Instance

Open Command Prompt or PowerShell and run the following command to launch your first Ubuntu instance:

```sh
multipass launch --name my-first-instance
```

This command downloads the latest Ubuntu LTS image and creates a VM named my-first-instance.


## Step 3: Configure Windows Terminal for Multipass
1. Open Windows Terminal: Launch Windows Terminal from your Start menu.

2. Add a New Profile: Click on the dropdown arrow in the title bar and select "Settings." This will open the settings file.

3. Create a Multipass Profile:

   * In the profiles section, add a new profile for Multipass:
  
    ```sh
    {
        "guid": "{YOUR-GUID-HERE}",
        "name": "Multipass",
        "commandline": "multipass shell my-first-instance",
        "icon": "https://multipass.run/favicon.ico",
        "startingDirectory": "//wsl$/Ubuntu/home/YOUR-USERNAME"
    }
    ```
    Replace {YOUR-GUID-HERE} with a unique GUID and YOUR-USERNAME with your actual username.

4. Save and Apply: Save the settings file and close it. You should now see "Multipass" in the dropdown list of available profiles in Windows Terminal.

## Step 4: Start Using Multipass with Windows Terminal
Select the Multipass profile from the dropdown in Windows Terminal. This will open a shell inside your `my-first-instance` Ubuntu VM. You can now interact with your Ubuntu instance directly from Windows Terminal, enjoying the benefits of both tools.

## Conclusion
By setting up Multipass with Windows Terminal, you create a seamless and efficient workflow for managing Ubuntu VMs on your Windows machine. Whether you're a developer, sysadmin, or hobbyist, this setup provides a powerful environment for your tasks. Happy coding!