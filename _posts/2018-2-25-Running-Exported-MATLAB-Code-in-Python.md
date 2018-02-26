After over a month of struggling with the MATLAB framework and finding and
importing the correct, I've finally managed to be able to export MATLAB code
and imported it as a module that I can call from python.  This path allows for
MATLAB code to be exported to a collection of files that can be compiled into
a python module which can be used to call MATLAB functions and run them on the
MATLAB Runtime Engine.  I've only tested this on Ubuntu, however it appears
that the Runtime Engine can be installed royalty free on Mac, Windows, and
Linux systems. 


Consider the following simple MATLAB script "hello_world.m":

    function hello_world
        fprintf('Hello, World!\n')
    end

We will go through the steps required to be able to call this from python.

 ## Note: This process has the following dependencies:
 * [MATLAB Runtime](https://www.mathworks.com/products/compiler/matlab-runtime.html "MATLAB Runtime")
 * [Python](https://www.python.org "Python")

First launch the MATLAB application "libraryCompiler".  In the pop-up window
select Python Package and add the hello_world.m script to the exported
functions list. 

![Library Compiler Window](https://github.com/jenni-niels/CREU_blog/blob/master/_posts/images/libraryCompiler.png?raw=true)

Using a terminal navigate into the produced directory and into the 
for_redistribution_files_only directory.  In this case from my parent directory

    $ cd hello_world/for_redistribution_files_only

Now install the module with the command:

    $ python setup.py install

or, depending on your computer's permissions you will likely have to sudo it.

    $ sudo python setup.py install

Now we have to set the environment variable "LD_LIBRARY_PATH" on Linux (or
"PATH" on Windows and "DYLD_LIBRARY_PATH") on Mac.  If these are not set we
will get the following error:

    >>> import hello_world
    Exception caught during initialization of Python interface. Details: On Linux, you must set the environment variable "LD_LIBRARY_PATH" to a non-empty string. For more details, see the package documentation.
    Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
        File "hello_world/__init__.py", line 276, in <module>
            _pir.get_paths_from_os()
        File "hello_world/__init__.py", line 171, in get_paths_from_os
            friendly_os_name, self.path_var, 'For more details, see the package documentation.'))
    RuntimeError: On Linux, you must set the environment variable "LD_LIBRARY_PATH" to a non-empty string. For more details, see the package documentation.
    >>>

We want to set the "LD_LIBRARY_PATH" environment variable to the path in which
the MATLAB Runtime is installed.  For me this became:

    $ export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/local/MATLAB/MATLAB_Runtime/v93/runtime/glnxa64:/usr/local/MATLAB/MATLAB_Runtime/v93/bin/glnxa64:/usr/local/MATLAB/MATLAB_Runtime/v93/sys/os/glnxa64:/usr/local/MATLAB/MATLAB_Runtime/v93/sys/opengl/lib/glnxa64

Now we should be able to successfully import the module, without errors.

    >>> import hello_world
    >>> 

We are almost able run our function.  We simply need to initialize the MATLAB
Runtime, which is shown in lines 2 and 3 below.

    >>> import hello_world
    >>> hello_world.initialize_runtime(['-nojvm', '-nodisplay'])
    >>> ms = hello_world.initialize()
    >>> ms.hello_world(nargout=0) 
    Hello, World!
    >>> 

Yay! Success! We can export MATLAB code to python applications.  The next steps
for me will be to export mine and the labs MATLAB code so that I can integrate
them into the GUI I'm building.
