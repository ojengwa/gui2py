<a href='https://github.com/reingart/gui2py'><img src='https://s3.amazonaws.com/github/ribbons/forkme_right_red_aa0000.png' alt='Fork me on GitHub' border='0' align='right' /></a>

InformacionGeneral - GuiaInstalacion (Español) 

gui2py is a GUI framework for building cross-platform "visual" desktop applications on Windows, Mac OS X, and Linux, using the Python language and the wxPython toolkit.
Its objetive is to evolve [PythonCard](http://pythoncard.sourceforge.net/) with [web2py's](http://www.web2py.com/) phylosophy and facilities with the following goals:

  * KISS compact structure: easy to learn, complete and powerful GUI Framework for Rapid Application Development
  * Visual Tools: designer, inspector and property editor, embeddables into IDEs (see [rad2py](http://code.google.com/p/rad2py)  [screenshot](https://gui2py.googlecode.com/hg/screenshots/win8/rad2py_ide2py_gui2py_integration.png))
  * HTML/Javascript-like capabilities (i.e. events, layout): reusing and/or adapting gluon (web2py framework) + automatic flow mechanism

## Features ##

Currently, gui2py supports the following components:
  * Window (wx.Frame) with Menues (wx.MenuBar, wx.Menu, wx.MenuItem, etc.) and StatusBar (wx.StatusBar), see the [minimal example](https://code.google.com/p/gui2py/source/browse/minimal.pyw)
  * Common dialogs: alert, prompt, confirm, select font/color, open/save file, choose directory, single / multiple choice, find
  * Controls: Button (wx.Button and wx.BitmapButton), CheckBox (wx.CheckBox), ComboBox (wx.ComboBox), Gauge (wx.Gauge, a.k.a. as a progress bar), GridView (wx.Grid) MVC, HtmlBox (wx.HtmlWindow), Image (wx.StaticBitmap), Label (wx.StaticText), Line (wx.StaticLine), ListBox (wx.ListBox), ListView (wx.ListCtrl), Notebook (wx.Notebook), Panel (wx.StaticBox & wx.Panel), RadioButton (wx.RadioButton), Slider (wx.Slider, similar to a "scroll bar"), TextBox (wx.TextCtrl, including masked and date picker support), TreeView (wx.Tree). See the [sample app code](https://code.google.com/p/gui2py/source/browse/sample.pyw) and [screenshot](https://gui2py.googlecode.com/hg/screenshots/win8/sample.png)
  * Basic Sizers support: automatic flow layout mechanism using wx.WrapSizer, see the [sizers example](https://code.google.com/p/gui2py/source/browse/sizers.pyw) and [sizers screenshot](https://gui2py.googlecode.com/hg/screenshots/win8/sizers.png)
  * Basic HTML "Rich internet Application" support: see some web2py forms in gui2py at the  [forms example](https://code.google.com/p/gui2py/source/browse/forms_example.py) ([login form screenshot](https://gui2py.googlecode.com/hg/screenshots/win8/form_login.png))

## Visual Tools ##

For quick Point-and-Click visual design of user interfaces, gui2py includes: a designer, a toolbox, an inspection tool and a property editor:

![https://gui2py.googlecode.com/hg/screenshots/win8/designer.png](https://gui2py.googlecode.com/hg/screenshots/win8/designer.png)

**Note:** You need wxPython 2.9.4 (3.0.0 or newer recommended) to use the development tools, as they depends on the latest widgets added to wx (mainly, [Wx Property Grid](http://wxpropgrid.sourceforge.net)

## Screenshots ##

  * SampleScreenshots: sample application running on Windows (7 & 8, works also on XP), Mac OS X (cocoa) and Ubuntu 12.04 (GTK)
  * ToolsScreenshots: designer + inspector + property editor + toolbox running on Windows, Mac OS X and Ubuntu 12.04 (GTK).

For more screenshots, browse the [screenshots](https://code.google.com/p/gui2py/source/browse/#hg%2Fscreenshots) folder in the repo.

## Compatibility ##

gui2py is designed to work with multiple versions of wxPython and Python (including py3k!). It is developed and tested at least in the following environments:
  * Python 2.5.4 - wxPython 2.8.11.0 (stable) - MS Windows XP (msw-unicode)
  * Python 2.6.1 - wxPython 2.9.4.0 (classic) - Mac OS X 10.6 (osx-carbon)
  * Python 2.7.2 - wxPython 2.9.4.1 (classic) - Ubuntu 12.04 LTS and 12.10 (gtk2 32/64 bits)
  * Python 2.7.2 - wxPython 2.9.4.0 (classic) - MS Windows 7 & 8 (msw 32/64 bits)
  * Python 2.7.3 - wxPython 2.9.4.0 (classic) - Mac OS X 10.6 (osx-cocoa)
  * Python 2.7.4 - wxPython 2.9.5.81 (phoenix) - Ubuntu 13.04 (gtk3 including broadway! 32/64 bits)
  * Python 2.7.4 - wxPython 3.0.0 (classic) - Ubuntu 13.04 (gtk2 3.0.0.0.b20131219 preview release)
  * Python 2.7.4 - wxPython 3.0.0 (phoenix) - Ubuntu 13.04 (gtk2 r 75400 build with some deprecation warnings)
  * Python 2.7.6 - wxPython 3.0.0 (classic) - MS Windows 8.1 (msw MSC v.1500 32 bits)  **_new!_**
  * Python 2.7.6 - wxPython 3.0.0 (classic) - Ubuntu 14.04 LTS (gtk2 3.0.0.0)  **_new!_** (using libwxgtk3.0 package)
  * Python 3.2.3 - wxPython 2.9.5.81 (phoenix) - Ubuntu 12.10 (gtk2 64 bits)
  * Python 3.3.1 - wxPython 2.9.5.81 (phoenix) - MS Windows 8 (msw 64 bits)

Notes:
  1. It should work in other combinations too (see installation section bellow)
  1. Visual designer requires propgrid, currently only available on classic (wx2.9.4 and up)
  1. some features are emulated ("degraded gracefully") in some versions where are not supported (like wx.WrapSizer prior wx2.9, using custom FlowSizer)
  1. To be used in py3k, you need to use 2to3 migration tool and download the latest sources from the repository

## Installation ##

See InstallationGuide or [readme.txt](https://code.google.com/p/gui2py/source/browse/readme.txt)

## News ##

  * 0.9.4 under development...
  * 0.9.3 third alpha released on 2013-08-27 (announce comming soon)
  * 0.9b second alpha released on 2013-05-08 [announcement](http://mail.python.org/pipermail/python-announce-list/2013-May/009895.html)
  * Ported to py3k + phoenix (future wxPython implementation) on 2013-04-24, [more info...](https://groups.google.com/d/msg/wxpython-users/Hquyccdid1s/dS-Q4JCt24sJ)
  * 0.9a first alpha released on 2013-03-31 [announcement...](http://mail.python.org/pipermail/python-announce-list/2013-April/009845.html)
  * Presented as a [lighting talk](http://www.web2py.com.ar/deck2py/slides/show/lt_gui) at [http://ar.pycon.org/2011 PyConAr2011](.md)
  * Initial working example in wiki page Web2pyExample and Web2pyExampleWithTable