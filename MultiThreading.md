# Introduction #

In wxPython and other toolkits, a secondary thread cannot update GUI objects.

To prevent blocking the main thread, one solution is using `gui.call_after(function, *args, **kwargs)` to execute a function asynchonously.

Other approach is creating and using a custom event. This is not currently implemented in gui2py, but you could look at wxPython itself:

http://wiki.wxpython.org/LongRunningTasks

## Threads and Call After function ##

Minimal example:

```
import gui, thread, time

def hilo():
   "my custom function"
   # this functions is executed in a new secondary thread
   for i in range(100):
       time.sleep(1)    # do something
       gui.call_after(incrementar, i)

def incrementar(i):
    "increment the progress bar"
    # this function is exceuted in the main thread
    print("progress %s" % i)
    bar.value = i

# create a sample windows with a progress bar:
with gui.Window() as win:
    bar = gui.Gauge()
    win.show()

# create the new thread and run the app event loop:
thread.start_new(hilo, ())
gui.main_loop()

```