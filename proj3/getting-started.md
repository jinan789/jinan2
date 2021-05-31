---
title: Getting Started
nav_order: 3
---


# Getting Started
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

There are two options to set up a virtual machine for the project. There
is no difference which option you choose. Option 2 is easier to set up,
but requires a stable Internet connection. If you run into any issues
with either option, please check the FAQ on Piazza first.

------------------------------------------------------------------------

## Option 1: Local Setup (VirtualBox)

This option is recommended if you do not have a stable Internet
connection.

To work with this option, you will need to install
[VirtualBox](https://www.virtualbox.org) and an SSH client (on Windows,
use
[Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
or [Git Bash](https://git-scm.com/download/win)). On Linux and Mac, you
can install these programs from your package manager (e.g., `apt` or
`brew`).

Open VirtualBox, and download and import the VM image
([pwnable-sp21.ova](https://drive.google.com/file/d/1eJgqKHICGIDvSgGy1C0E0oyyX0j4IBls))
via `File -> Import Applicance`.

You can now start the VM, in which you will run the vulnerable programs
and their exploits. You can SSH into the VM by running
`ssh -p 16121 USERNAME@127.0.0.1` on your local machine,
replacing `USERNAME` depending on the question.

To make sure the VM works, run `ssh -p 16121 customizer@127.0.0.1`. If
you see a prompt for `customizer@127.0.0.1’s password:`, you are ready
to start the project.

------------------------------------------------------------------------

## Option 2: Online Setup (the Hive)

To work with this option, you will need an EECS instructional account
(you should have set one up in HW1, Q2.2).

To start the VM, execute the following command in your terminal:

    $ ssh -t cs161-XXX@hiveYY.cs.berkeley.edu \~cs161/proj1/start

Replace `XXX` with the last three letters of your instructional account,
and `YY` with the number of a hive machine (1-20). For best experience,
use [Hivemind](https://hivemind.eecs.berkeley.edu/) to select a hive
machine with low load. (Machines 21-30 are reserved for CS61C, so please
only use machines 1-20.)

If everything works successfully, a lot of output will scroll by (from
the virtual machine booting up). If you see a `pwnable login:` prompt,
you are ready to start the project.

**Note**: Normally when you are done with the VM, you can simply close
the terminal window. Some events might cause the VM to become
inaccessible. In this case you can force close the VM by running the
following command on your local computer:

    $ ssh cs161-XXX@hiveYY.cs.berkeley.edu \~cs161/proj1/stop
