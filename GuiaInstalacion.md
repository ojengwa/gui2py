# Guía de Instalación #

Indice:


## Inicio Rápido ##

Asegurese de haber instalado [Python 2.7](http://python.org/download/) y [wxPython 2.9.4](http://wxpython.org/download.php#unstable). Versiones anteriores podrían funcionar, pero no han sido completamente probadas y no son recomendadas. Ver abajo el paquete exacto y las instrucciones para cada OS.

Descargue & y descomprima el [acrchivo zip de código fuente](https://gui2py.googlecode.com/files/gui2py-0.9.3.zip), o haga un [check out](https://code.google.com/p/gui2py/source/checkout) del repositorio mercurial:

```
hg clone https://code.google.com/p/gui2py/ 
```

Leugo, pruebe la aplicación mínima en el directorio principal, haciendo doble click en el archivo `minimal.pyw` o ejecutando:
```
python minimal.pyw
```

O, pruebe la aplicación de ejemplo en el mismo directorio, haciendo doble click en el archivo `sample.pyw` o ejecutando:
```
python sample.pyw
```

También, puede iniciar el diseñador GUI con:
```
python -m gui.tools.designer
```
Eso debería levantar el diseñado (pidiéndole el nombre de un archivo para editar). Puede pasarle el archivo para editar como primer parámetro: `python -m gui.tools.designer sample.pyw`. Ver también los pantallazos en ToolsScreenshots.

Para instalar, copie la carpeta "gui" en su directorio de paquetes de python o cualquier otro directorio en el PYTHONPATH.
Por defecto, el instalador de windows lo pondrá en el directorio Python2x\Lib\site-packages;
la ruta real puede ser diferente dependiendo de su sistema operativo y versión de Python.

Puede instalar ejecutando:
```
python setup.py install
```

Necesitará iniciar una sesión de administrador (o usar `sudo` en Ubuntu) para instalarlo en un directorio del sistema.

## Windows ##

En windows, ejecute los siguientes instaladores de acuerdo a la arquitectura de su CPU:

### Windows 32 bit ###

  * http://python.org/ftp/python/2.7.3/python-2.7.3.msi
  * http://downloads.sourceforge.net/wxpython/wxPython2.9-win32-2.9.4.0-py27.exe
  * https://gui2py.googlecode.com/files/gui2py-0.9.3-py2x.win32.exe

### Windows 64 bit ###

  * http://python.org/ftp/python/2.7.3/python-2.7.3.amd64.msi
  * http://downloads.sourceforge.net/wxpython/wxPython2.9-win64-2.9.4.0-py27.exe
  * https://gui2py.googlecode.com/files/gui2py-0.9.3-py2x.win-amd64.exe


## Mac OSX ##

Se ha probado en Mac OS X 10.6 + Python 2.7 + wxPython 2.9 "cocoa":

  * http://python.org/ftp/python/2.7.3/python-2.7.3-macosx10.6.dmg
  * http://downloads.sourceforge.net/wxpython/wxPython2.9-osx-2.9.4.0-cocoa-py2.7.dmg
  * https://gui2py.googlecode.com/files/gui2py-0.9.3.zip


También funciona en versiones anteriores de Mac OS con carbon.

## GNU/Linux ##

Código Fuente:
  * https://gui2py.googlecode.com/files/gui2py-0.9.3.zip

En Ubuntu y otras distribuciones, necesitará construir los paquetes .deb/.rpm de  wx2.9, con checkinstall o similar.
Puede revisar la siguiente página para las instrucciones para el método de checkinstall (que automáticamente construye los paquetes):

http://wiki.wxpython.org/CheckInstall

También puede descargar algunos paquetes binarios pre-construidos de las siguientes secciones.

**DISCLAIMER**: Por supuesto, no son paquetes oficiales,  uselos bajo su propio riesgo ;-)

Estos paquetes pueden no cumplir con todas las recomendaciones de cada distribucipon, pero deben ser suficientes para que pueda instalarlos y desinstalarlos...

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


## Resolución de Problemas ##

Primero, verifique su versión de python (2.7) y wx (2.9.4), haciendo:

```
reingart@desktop:~/gui2py-hg$ python
Python 2.7.3 (default, Aug  1 2012, 05:14:39) 
[GCC 4.6.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import wx
>>> wx.version()
'2.9.4.1 gtk2 (classic)'
```

Luego, verifique las rutas: esta la carpeta `gui` (not gui2py one) en el  `PYTHONPATH`?
Pruebe:
```
python -c "import gui; print gui.__version__"
```

Si arroja una excepción o no imprime la versión (0.9.3), la manera fácil de solucionarlo es cambiandose a la carpeta correspondiente:
```
cd gui2py
```
donde gui2py está descomprimido, o la raíz del repositorio.

Para una solución más permanente, simplemente instale el paquete ejecutando `python setup.py install` o equivalente.

Por favor notar que 0.9 es una liberación alfa, por lo que puede aún hay algunos detalles que pulir.

## Python 3 & wxPython Phoenix ##

Para usar gui2py en la versión venidera de python y wx, debe descargar Phoenix snapshot build (probado con wxPython\_Phoenix-2.9.5.81 r. 73942 y superior):

http://wxpython.org/Phoenix/snapshot-builds/

Luego, debería descargar el código fuente de gui2py (para obtener los últimos cambios), y convertirlos con 2to3:

```
hg clone https://code.google.com/p/gui2py/
cd gui2py
2to3 -w gui
2to3 -w -x import sample.pyw
```

Para su comodidad, se proveen scripts de conversión:
  * En MS Windows, puede usar `py3k.bat`.
  * En GNU/Linux y Mac OS X, puede usar `py3k.sh`.

Para MS Windows, se proveen instaladores pre-generados:
  * https://gui2py.googlecode.com/files/gui2py-0.9b-py3k.win32.exe
  * https://gui2py.googlecode.com/files/gui2py-0.9b-py3k.win-amd64.exe

Finalmente, puede ejecutar la aplicación de ejemplo (GNU/Linux y Mac OS X):
```
python3 sample.pyw
```
En MS Windows:
```
C:\python33\python.exe sample.pyw
```