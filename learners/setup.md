---
title: Setup
---

This lesson is designed to be run on a personal computer.
All of the software and data used in this lesson are freely available online,
and instructions on how to obtain them are provided below.

# <a name=#setup>Setup</a>

To participate in this lesson, we will use [Colab notebooks](https://colab.research.google.com/). Colab is a cloud-based environment where you can run scripting languages such as Python, create small segments of code, annotate them with notes and rich text, and return to your work later.

 will need to import our own resources into Colab, such as our simulated data. In order to do this, we will use Google drive. Because we will need to grant Colab access to our Google Drive data, **we strongly recommend creating an ad-hoc ("throwaway") Gmail account.** That way, we do not risk sharing or altering any sensitive data that we might have on our Broad Institute Google accounts.


## Testing Broad Login Server access

If you are on-site, connect to the **Broad-Internal** wireless network. If you are off-site, [connect](https://intranet.broadinstitute.org/bits/service-catalog/networking/vpn) to the Broad VPN.

::: tab

### Mac

1. Open Terminal from `/Applications/Utilities` or Spotlight Search.
1. Type <kbd>ssh \<username\>@login.broadinstitute.org</kbd> [Example: ssh jcase@login.broadinstitute.org ]
1. Enter your Broad password when prompted.

### Linux

1. Most Linux systems use Ctrl-Alt-T to start a Linux Terminal session.
1. On the command line, type <kbd>ssh \<username\>@login.broadinstitute.org</kbd> [Example: ssh jcase@login.broadinstitute.org ]
1. Enter your Broad password when prompted.

### Windows - WSL

1. Open WSL from the start menu item or by typing <kbd>wsl</kbd> from a command prompt or PowerShell.
1. Type <kbd>ssh \<username\>@login.broadinstitute.org</kbd> [Example: ssh jcase@login.broadinstitute.org ]
1. Enter your Broad password when prompted.

### Windows - SecureCRT

1. Launch [SecureCRT](https://broad.service-now.com/sp?sys_kb_id=072a3dc613eb0f80449fb86f3244b0e8&id=kb_article_view&sysparm_rank=1&sysparm_tsqueryId=f5b28afe47714e50a5d9a8ba216d43e9) from the Start menu
1. Go to the File menu and select "Connect". Select the "New Session"" button.
1. Within the New Session Wizard window, select SSH2 at the Protocol toggle and click Next.
1. Within the Hostname field, enter login.broadinstitute.org. Leave the Port and Firewall fields set to their defaults. Within the username field, enter your Broad username and click Next.
1. Leave the SecureFX protocol field as is (eg. SFTP), click Next.
1. Leave the session name field as it is, or rename it to something shorter. Click the Finish button.
1. X11 setup (for future reference, not needed for this workshop): Select the newly created connection entry and click the Properties icon button. The Session Options window will appear. Select Remote/X11 from the menu on the left, check Forward X11 packets. Click the OK button to close the window.
1. Finally, select your session and click the Connect button. Enter your password to log on.

:::

## Obtain lesson materials

1. Download [python-novice-inflammation-data.zip][zipfile1]
  and [python-novice-inflammation-code.zip][zipfile2].
2. Create a folder called `swc-python` in your computer's home directory.
3. Move downloaded files to `swc-python`.
4. Unzip the files.
5. Log into [Google Drive](https://drive.google.com/drive/my-drive) using the Gmail account you created for this course. You may want to use a private browsing window to do this, if you usually use your Broad account when logging in to Drive.
6. Upload the lesson content by clicking "+ New" followed by "Folder upload." Select and upload the `swc-python` folder you just created.

You should see a `swc-python` folder in "My Drive", with two subfolders called `data` and `code` in it.

#### Show your successful access

1. Type <kbd>touch /broad/hptmp/computing_basics_python/\<username\>_was_here</kbd>
2. Type <kbd>ls /broad/hptmp/computing_basics_python</kbd> Did you leave your mark?
3. Type <kbd>exit</kbd> to leave the server.

If you were unable to access the Broad login servers, please let the [workshop organizers](mailto:cb-admin@broadinstitute.org) know so we can help you troubleshoot before the start of the workshop.

:::::::::::::::::::::::::::::::::::::::::: spoiler

## to be updated by cb-admins

## Launch Python interface

To start working with Python, we need to launch a program that will interpret and execute our
Python commands. Below we list several options. If you don't have a preference, proceed with the
top option in the list that is available on your machine. Otherwise, you may use any interface
you like.

## Option A: Jupyter Notebook

A Jupyter Notebook provides a browser-based interface for working with Python.
If you installed Anaconda, you can launch a notebook in two ways:

::::::::::::::::: spoiler

## Anaconda Navigator

1. Launch Anaconda Navigator.
  It might ask you if you'd like to send anonymized usage information to Anaconda developers:
  ![](fig/anaconda-navigator-first-launch.png){alt='Anaconda Navigator first launch'}
  Make your choice and click "Ok, and don't show again" button.
2. Find the "Notebook" tab and click on the "Launch" button:
  ![](fig/anaconda-navigator-notebook-launch.png){alt='Anaconda Navigator Notebook launch'}
  Anaconda will open a new browser window or tab with a Notebook Dashboard showing you the
  contents of your Home (or User) folder.
3. Navigate to the `data` directory by clicking on the directory names leading to it:
  `Desktop`, `swc-python`, then `data`:
  ![](fig/jupyter-notebook-data-directory.png){alt='Anaconda Navigator Notebook directory'}
4. Launch the notebook by clicking on the "New" button and then selecting "Python 3":
  ![](fig/jupyter-notebook-launch-notebook.png){alt='Anaconda Navigator Notebook directory'}

:::::::::::::::::::::::::

::::::::::::::::: spoiler

## Command line (Terminal)

1\. Navigate to the `data` directory:

::::::::::::::::: spoiler

## Unix shell

If you're using a Unix shell application, such as Terminal app in macOS, Console or Terminal
in Linux, or [Git Bash][gitbash] on Windows, execute the following command:

```bash
cd ~/Desktop/swc-python/data
```

:::::::::::::::::::::::::

::::::::::::::::: spoiler

## Command Prompt (Windows)

On Windows, you can use its native Command Prompt program.  The easiest way to start it up is
pressing <kbd>Windows Logo Key</kbd>\+<kbd>R</kbd>, entering `cmd`, and hitting
<kbd>Return</kbd>. In the Command Prompt, use the following command to navigate to
the `data` folder:

```source
cd /D %userprofile%\Desktop\swc-python\data
```

:::::::::::::::::::::::::

2\. Start Jupyter server

::::::::::::::::: spoiler

## Unix shell

```bash
jupyter notebook
```

:::::::::::::::::::::::::

::::::::::::::::: spoiler

## Command Prompt (Windows)

```source
python -m notebook
```

:::::::::::::::::::::::::

3\. Launch the notebook by clicking on the "New" button on the right and selecting "Python 3"
from the drop-down menu:
![](fig/jupyter-notebook-launch-notebook2.png){alt='Anaconda Navigator Notebook directory'}

:::::::::::::::::::::::::

  <!-- vertical spacer -->

## Option B: IPython interpreter

IPython is an alternative solution situated somewhere in between the plain-vanilla Python
interpreter and Jupyter Notebook. It provides an interactive command-line based interpreter with
various convenience features and commands.  You should have IPython on your system if you installed
[Anaconda][anaconda-instructions].

To start using IPython, execute:

```source
ipython
```

  <!-- vertical spacer -->

## Option C: plain-vanilla Python interpreter

To launch a plain-vanilla Python interpreter, execute:

```source
python
```

If you are using [Git Bash on Windows][gitbash], you have to call Python *via* `winpty`:

```source
winpty python
```

::::::::::::::::::::::::::::::::::::::::::

[anaconda-instructions]: https://carpentries.github.io/workshop-template/install_instructions/#python
[zipfile1]: data/python-novice-inflammation-data.zip
[zipfile2]: ../episodes/files/code/python-novice-inflammation-code.zip
[gitbash]: https://gitforwindows.org
