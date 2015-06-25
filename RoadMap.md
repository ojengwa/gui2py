# Timeline #

## Milestones ##
  * ~~proof-of-concept (pre-alpha): done (mostly the wxHTML Form example)~~ DONE completed on September, 2011
  * ~~alpha:~~ (planned ~~December 2011~~ ~~February 2013~~) DONE completed on April 1st, 2013
  * beta: (planned to be released around July 2013)

# TODO (~~alpha~~ beta) #

  * Integrate PythonCard components, mainly:
    * Controls:
      * ~~Button (Button - wx.Button)~~ almost done
      * ~~Label (StaticText - wx.StaticText)~~ almost done and improved
      * ~~TextBox (pythoncard.components.textfield.TextField, pythoncard.components.textarea.TextArea, pythoncard.components.textfield.passwordfield.PasswordField - wx.TextCtrl)~~ almost done
      * ~~CheckBox (pythoncard.components.checkbox.CheckBox - wx.CheckBox)~~ almost done
      * ~~ListBox (pythoncard.components.choice.Choice - wx.Choice)~~ almost done
      * ~~ComboBox (pythoncard.components.combobox.ComboBox - wx.ComboBox)~~ almost done
      * ~~List (pythoncard.components.multicolumnlist.MultiColumnList - wx.ListCtrl)~~ almost done and improved
      * ~~Tree (pythoncard.components.tree.Tree - wx.Tree)~~ almost done and improved
      * ~~Grid (pythoncard.components.grid.Grid - wx.Grid)~~ almost done and improved
      * Canvas (BitmapCanvas - wx.Window or wx.FloatCanvas)
    * Containers & misc:
      * ~~Window (pythoncard.model.Background - wx.Frame)~~ almost done and improved
      * ~~Panel (pythoncard.model.Background - wx.Panel)~~ almost done and improved
      * ~~Notebook and TabPanel (wx.Notebook and wx.Panel)~~ almost done and improved
      * Dialog (pythoncard.model.CustomDialog - wx.Dialog)
      * ~~Application (pythoncard.model.Application - wx.App)~~ not needed
      * ~~MenuBar (pythoncard.menu - wx.MenuBar)~~ almost done and improved
      * ~~StatusBar (pythoncard.statusbar - wx.StatusBar)~~ almost done (needs improvements)
      * Sizers support (wx.WrapSizer): initiated, but needs work for more precise relative dimensions calulation
  * ~~Provide an easier abstraction to bind events (something like [HTML intrinsic events](http://www.w3.org/TR/html4/interact/scripts.html#h-18.2.3), or more formally: [DOM events](http://www.w3.org/TR/2000/REC-DOM-Level-2-Events-20001113/events.html#Events-eventgroupings-uievents))~~ DONE
  * Visual tools:
    * ~~inspector~~: DONE, need revision of some minor bugs (i.e. refresh when reindexing z-order / spec name changes)
    * ~~propeditor~~: DONE, need minor enhancements (i.e. edit of compound properties)
    * ~~toolbox~~: DONE, need revision of some minor bugs (specially on mac: drag&drop)
    * ~~designer~~: DONE, need revision of some minor bugs (specially on mac when rebuilding a Window)
  * web2py (gluon) HTML integration:
    * ~~Provide easier layout engine with wx.html.HtmlWindow~~ almost done (needs improvements)
    * Unify html forms (gui2py.form, gui2py.input) and gui2py.widgets
    * Sopport web2py helpers & tools: SQLFORM, auth, crud, grid, etc.
  * ~~Standard dialogs: alert, confirm, prompt~~ (TODO: fix minor usability & flexibility concerns)
  * Support more advanced controls
    * ~~wx.DatePickerCtrl~~ almost done
    * ~~wx.lib.masked.NumCtrl~~ almost done
    * ~~wx.lib.masked.TextCtrl~~ almost done
    * wx.lib.popupctl.PopupControl
  * Support wx.lib.agw.aui.
  * Documentation (on-line help, context-sensitive if possible)
  * Extract manual test from each file and make them unit test
  * Finish pep8-fication (remove all camel case names from pythoncard, use underscore only, fix long lines, etc.)
  * Complete IDE integration: started, see [rad2py](http://rad2py.googlecode.com/) ([screenshot](https://gui2py.googlecode.com/hg/screenshots/win8/rad2py_ide2py_gui2py_integration.png))
  * MVC execution framework (restful architecture - "Rich Internet Applications")
  * Migration Tools:
    * Pythoncard to gui2py conversion tool
    * Visual Basic (classic) to gui2py conversion tool? (maybe with [vb2py](http://vb2py.sourceforge.net/))
  * ~~Support for Python 3 + wxPython Phoenix~~ almost done (at least sample application runs on py3k + wx2.9.5.81)
