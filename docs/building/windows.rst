.. _building_windows:

Building PySide on a Windows System
===================================

Installing prerequisites
------------------------

#. Install `Python
   <http://www.python.org/download/>`_.

#. Install `Qt 4.8 libraries for Windows VS 2008 edition
   <http://download.qt-project.org/official_releases/qt/4.8/4.8.7/qt-opensource-windows-x86-vs2008-4.8.7.exe>`_
   when building against Python 2.6, 2.7 or 3.2.

   Install `Qt 4.8 libraries for Windows VS 2010 edition
   <http://download.qt-project.org/official_releases/qt/4.8/4.8.7/qt-opensource-windows-x86-vs2010-4.8.7.exe>`_
   when building against Python 3.3 or 3.4.

#. Install `Cmake
   <http://www.cmake.org/cmake/resources/software.html>`_.

#. Install `Windows SDK v7.0
   <http://www.microsoft.com/en-us/download/details.aspx?id=3138>`_
   when building against Python 2.6, 2.7 or 3.2.

   Install `Windows SDK v7.1
   <http://www.microsoft.com/en-us/download/details.aspx?id=8279>`_
   when building against Python 3.3 or 3.4.

#. Install `Git
   <http://git-scm.com/download/win>`_.

#. (Optional) Install `OpenSSL
   <http://slproweb.com/products/Win32OpenSSL.html>`_.

#. Install latest ``pip`` distribution into the Python you
   installed in the first step: download `get-pip.py 
   <https://bootstrap.pypa.io/get-pip.py>`_ and run it using
   the ``python`` interpreter of your Python 2.7 installation using a
   command prompt:

   ::

      c:\> c:\Python27\python get-pip.py

#. Install latest `wheel` distribution:

   ::

      c:\> c:\Python27\Scripts\pip install wheel


.. note::
   
   * If you are using the Windows SDK versions linked above, make sure that you have .NET Framework 
     Version 4.0 installed on your system. Version 4.5 will not work.
   * To avoid problems with environment variables, execute all commands below in a "Windows SDK Comamnd 
     Prompt" that you will find in your Start Menu, instead of a standard cmd.exe command line.

Building PySide distribution
----------------------------

#. Download and extract `PySide source distribution
   <https://pypi.python.org/packages/source/P/PySide/PySide-1.2.4.tar.gz>`_

#. Switch to the distribution directory:

   ::

      c:\> cd PySide-1.2.4

#. Build the ``wheel`` binary distribution:

   ::

      c:\> c:\Python27\python.exe setup.py bdist_wheel --qmake=c:\Qt\4.8.7\bin\qmake.exe --openssl=c:\OpenSSL32bit\bin


Building PySide distribution from a Git repository
--------------------------------------------------

#. Clone ``PySide`` setup scripts from git repository:

   ::

      c:\> git clone https://github.com/PySide/pyside-setup.git pyside-setup

#. Switch to the ``pyside-setup`` directory:

   ::

      c:\> cd pyside-setup

#. Build the `wheel` binary distribution:

   ::

      c:\> c:\Python27\python.exe setup.py bdist_wheel --version=1.2.4 --qmake=c:\Qt\4.8.7\bin\qmake.exe --openssl=c:\OpenSSL32bit\bin

#. To build the development version of ``PySide`` distribution, ignore the --version parameter:

   ::

      c:\> c:\Python27\python.exe setup.py bdist_wheel --qmake=c:\Qt\4.8.7\bin\qmake.exe --openssl=c:\OpenSSL32bit\bin


Installing PySide distribution
------------------------------

#. After the successful build, install the distribution with ``pip``:

   ::

      c:\> c:\Python27\Scripts\pip install dist\PySide-1.2.4-cp27-none-win32.whl


Installing PySide distribution into ``virtual`` Python environment
------------------------------------------------------------------

#. Install latest ``virtualenv`` distribution:

   ::

      c:\> c:\Python27\Scripts\pip install virtualenv

#. Use ``virtualenv`` to make a workspace:

   ::

      c:\> c:\Python27\Scripts\virtualenv env

#. Switch to the ``env`` directory:

   ::

      c:\> cd env

#. Install the distribution with ``pip``:

   ::

      c:\> Scripts\pip install ..\dist\PySide-1.2.4-cp27-none-win32.whl
