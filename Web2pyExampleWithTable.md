# Example window with auto updated table

Remember to change the paths in sys.path to the proper gui2py and web2py clone folders in your system


---


```
#!/usr/bin/python
# -*- coding: latin-1 -*-

__author__ = "Mariano Reingart (reingart@gmail.com)"
__copyright__ = "Copyright (C) 2011 Mariano Reingart"
__license__ = "LGPL 3.0"

import sys

# import wxPython:
import wx

# import gui2py support -wxHTML FORM handling- (change the path!)
sys.path.append(r"/home/m/gui2py-hg")
from gui2py.form import EVT_FORM_SUBMIT

# import web2py (change the path!)
sys.path.append(r"/home/mariano/web2py-hg")
from gluon.dal import DAL, Field
from gluon.sqlhtml import SQLFORM

from gluon.sqlhtml import SQLTABLE
from gluon.html import INPUT, FORM, TABLE, TR, TD, DIV

from gluon.validators import IS_NOT_EMPTY, IS_EXPR, IS_NOT_IN_DB, IS_IN_SET
from gluon.storage import Storage

# create DAL connection (and create DB if not exists)
db=DAL('sqlite://guitest.sqlite', folder=None)

# define a table 'person' (create/aster as necessary)
person = db.define_table('person',
    Field('name','string', length=100),
    Field('sex','string', length=1),
    Field('active','boolean', comment="check!"),
    Field('bio','text', comment="resume (CV)"),
    )

# set sample validator (do not allow empty nor duplicate names)
db.person.name.requires = [IS_NOT_EMPTY(),
                           IS_NOT_IN_DB(db, 'person.name')]

db.person.sex.requires = IS_IN_SET({'M': 'Male', 'F': 'Female'})

# create the wxPython GUI application instance:
app = wx.App(False)

# create a testing frame (wx "window"):
f = wx.Frame(None, title="web2py/gui2py sample app")

# create the web2py FORM based on person table
form = SQLFORM(db.person)

# create the HTML "browser" window:
html = wx.html.HtmlWindow(f, style= wx.html.HW_DEFAULT_STYLE | wx.TAB_TRAVERSAL)

# automated web2py all records table
table = SQLTABLE(db(db.person).select())

# create the container DIV for the form and the table
div = DIV(form, table)

# convert the web2py DIV to XML and display it
html.SetPage(div.xml())

def on_form_submit(evt):
    "Handle submit button user action"
    global form
    print "Submitting to %s via %s with args %s"% (evt.form.action, evt.form.method, evt.args)
    if form.accepts(evt.args, formname=None, keepvalues=False, dbio=False):
        print "accepted!"
        # insert the record in the table (if dbio=True this is done by web2py):
        db.person.insert(name=form.vars.name,
                         sex=form.vars.sex,
                         active=form.vars.active,
                         bio=form.vars.bio,
                        )
        # don't forget to commit, we aren't inside a web2py controller!
        db.commit()
    elif form.errors:
        print "errors", form.errors
        
    # refresh the form and table (show web2py errors)
    table = SQLTABLE(db(db.person).select())
    div = DIV(form, table)

    # display the updated div
    html.SetPage(div.xml())

# connect the FORM event with the HTML browser
html.Bind(EVT_FORM_SUBMIT, on_form_submit)

# show the main window
f.Show()
# start the wx main-loop to interact with the user
app.MainLoop()

```