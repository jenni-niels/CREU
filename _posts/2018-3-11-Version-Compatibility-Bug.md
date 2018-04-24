I spent this week continuing to investigate the error I ran into last week.
Initially I attempted to examine the settings of the MATLAB Runtime library,
and go through the documentation relating to them, but I couldn't find anything
to resolve the error.

Eventually I went back to the figurative "drawing board", and decided to examine
my code in the MATLAB IDE so see if there was anything thing in my odd code that
looked like it could be causing the error.  In hindsight it feels obvious 
(although I spent hours before I figured it out), it turned out that since I
developed much of the code I was using previously over the summer, it had been
done in a previous version of MATLAB.  Unsurprisingly, when I attempted to run
the current in the more recent version on MATLAB (the same version as the
runtime) it crashed.  Okay that was a surprisingly simple explanation.
The next step was to find where in my code it was crashing (and why). 
I had been building of off the the [GLOAT toolbox](http://tcts.fpms.ac.be/~drugman/Toolbox/),
and the line in question was a built in MATLAB function, which appears to have
changed the expected types of its parameters between versions.