I've begun to work on exporting some of the existing code, starting with the
code that I wrote. The first steps were to go through it and modify it so that
the return values were simply the raw results (array of classification) as
opposed to manipulating those results to plot them in various ways.  The idea
being that the data presentation can be handled in Matplotlib, which integrates
with Tkinter more easily.

From the MATLAB side of things those modifications / refactoring for modularity
have been implemented.  However, when I attempt to follow the same process as
last week to export it, I run into the following error:


    >>> import detectVoice
    Exception caught during initialization of Python interface. Details: Could not find an appropriate directory for MATLAB or the MATLAB runtime in LD_LIBRARY_PATH. Details: libmwmclmcrrt.so.9.0
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
      File "detectVoice/__init__.py", line 275, in <module>
        _pir.get_paths_from_os()
      File "detectVoice/__init__.py", line 180, in get_paths_from_os
        self.path_var, file_to_find))
    RuntimeError: Could not find an appropriate directory for MATLAB or the MATLAB runtime in LD_LIBRARY_PATH. Details: libmwmclmcrrt.so.9.0
    >>> 

I'm not yet sure exactly what it refers to.  I have a suspicion it relates to
some setting of the MATLAB runtime, but am still working on figuring it out.