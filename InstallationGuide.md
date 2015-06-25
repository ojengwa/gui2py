# Installation Guide #

Table of contents:


## Quick Start ##

First, be sure that you have installed [Python 2.7](http://python.org/download/) and [wxPython 2.9.4 development release](http://wxpython.org/download.php#unstable). Older versions could work, but they are untested and not recommended. See bellow for exact package and installation instructions on each OS.

Download & uncompress the [source code zip archive](https://gui2py.googlecode.com/files/gui2py-0.9.3.zip), or [check out](https://code.google.com/p/gui2py/source/checkout) the mercurial repository:

```
hg clone https://code.google.com/p/gui2py/ 
```

Then, try the minimal application the main directory, double clicking the `minimal.pyw` file or running:
```
python minimal.pyw
```

Or, try the sample application in the same directory, double clicking the `sample.pyw` file or running:
```
python sample.pyw
```

Also, you can start the GUI designer with:
```
python -m gui.tools.designer
```
That should bring up the designer (asking first for a filename to edit). You can pass the file to edit as a parameter: `python -m gui.tools.designer sample.pyw`. See also the ToolsScreenshots.

To install, place the "gui" directory in your python directory or another directory on your PYTHONPATH.
By default, the Windows installer and distutils installer will place PythonCard in your Python2x\Lib\site-packages directory;
the actual path will be different depending on your OS and version of Python.

You can install it running:
```
python setup.py install
```

You will need to start an administration session (or use `sudo` on Ubuntu) to install it in a system wide folder.

## Windows Users ##

In windows, please run the following installers according your CPU architecture:

### Windows 32 bit ###

  * http://python.org/ftp/python/2.7.3/python-2.7.3.msi
  * http://downloads.sourceforge.net/wxpython/wxPython2.9-win32-2.9.4.0-py27.exe
  * https://gui2py.googlecode.com/files/gui2py-0.9.3-py2x.win32.exe

### Windows 64 bit ###

  * http://python.org/ftp/python/2.7.3/python-2.7.3.amd64.msi
  * http://downloads.sourceforge.net/wxpython/wxPython2.9-win64-2.9.4.0-py27.exe
  * https://gui2py.googlecode.com/files/gui2py-0.9.3-py2x.win-amd64.exe


## Mac OSX Users ##

The tested combination is Mac OS X 10.6 + Python 2.7 + wxPython 2.9 "cocoa":

  * http://python.org/ftp/python/2.7.3/python-2.7.3-macosx10.6.dmg
  * http://downloads.sourceforge.net/wxpython/wxPython2.9-osx-2.9.4.0-cocoa-py2.7.dmg
  * https://gui2py.googlecode.com/files/gui2py-0.9.3.zip


It also runs on earlier Mac OS versions with carbon.

## GNU/Linux Users ##

Source code:
  * https://gui2py.googlecode.com/files/gui2py-0.9.3.zip

In ubuntu and other distros, you will need to build wx2.9 .deb/.rpm packages from the sources, with checkinstall or similar.
You can check this page with the instructions for the checkinstall approach (that automatically builds the packages):

http://wiki.wxpython.org/CheckInstall

You can download some prebuild binary packages from the following sections.

**DISCLAIMER**: Of course these aren't official packages, use at your own risk ;-)

The packages may not comply with all of the packaging guidelines of
each distro, but they should do the trick... (at least as far I tested
it)
I don't have knowledge to build the packages on Fedora, but if anyone
send me the step-by-step instruction, I think the .rpm could be made
too.

### Debian 6.0 32bits ###

  * http://www.sistemasagiles.com.ar/soft/dists/squeeze/wxwidgets_2.9.4-1_i386.deb
  * http://www.sistemasagiles.com.ar/soft/dists/squeeze/wxpython_2.9.4-1_i386.deb

### Ubuntu 12.04 32bits ###

  * http://www.sistemasagiles.com.ar/soft/dists/precise/wxwidgets_2.9.4-1_i386.deb
  * http://www.sistemasagiles.com.ar/soft/dists/precise/wxpython_2.9.4-1_i386.deb

### Ubuntu 12.04 64bits ###

  * http://www.sistemasagiles.com.ar/soft/dists/precise/wxwidgets_2.9.4-1_amd64.deb
  * http://www.sistemasagiles.com.ar/soft/dists/precise/wxpython_2.9.4-1_amd64.deb

### Ubuntu 12.10 64 bits ###

  * http://www.sistemasagiles.com.ar/soft/dists/quantal/wxwidgets_2.9.4-1_amd64.deb
  * http://www.sistemasagiles.com.ar/soft/dists/quantal/wxpython_2.9.4-1_amd64.deb


## Troubleshotting ##

First, check your version of python (2.7) and wx (2.9.4), doing:

```
reingart@desktop:~/gui2py-hg$ python
Python 2.7.3 (default, Aug  1 2012, 05:14:39) 
[GCC 4.6.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import wx
>>> wx.version()
'2.9.4.1 gtk2 (classic)'
```

Then, check your paths: is the `gui` folder (not gui2py one) in the `PYTHONPATH`?
Try:
```
python -c "import gui; print gui.__version__"
```

If it throws an exception or don't print the version (0.9), the easy way to fix that is just do:
```
cd gui2py
```
where gui2py is the uncompressed folder or the root of the mercurial repo.

For a more permantent solution, just install the package running `python setup.py install` or equivalent.

Please note that 0.9 is an alpha release, so there are some rough edges to polish right now.

## Python 3 & wxPython Phoenix ##

To use gui2py on the upcoming python and wx versions, you should download Phoenix snapshot build (tested wxPython\_Phoenix-2.9.5.81 r. 73942 and up):

http://wxpython.org/Phoenix/snapshot-builds/

Then, you should download the gui2py source code (to get the latest changes), convert it with 2to3:

```
hg clone https://code.google.com/p/gui2py/
cd gui2py
2to3 -w gui
2to3 -w -x import sample.pyw
```

For your convenience, there are conversion scripts provided:
  * On MS Windows, you can use `py3k.bat`.
  * On GNU/Linux and Mac OS X, you can use `py3k.sh`.

For MS Windows prebuild installers are provided too:
  * https://gui2py.googlecode.com/files/gui2py-0.9b-py3k.win32.exe
  * https://gui2py.googlecode.com/files/gui2py-0.9b-py3k.win-amd64.exe

Finally, you can run the sample app (GNU/Linux and Mac OS X):
```
python3 sample.pyw
```
On MS Windows:
```
C:\python33\python.exe sample.pyw
```