Much of my time was spent reading through the MATLAB documentation for the
function call in particular, that was causing the bug I was having. There was
some ambiguity as to which library the function was being invoked from as I 
found multiple libraries with that function name in the documentation, and 
even for the ones that seemed the most likely, the function was overloaded such
that it could take many different types of parameters.  In addition, to this I
was receiving build waring about typing, which I suspect were related.

I was at a point where I felt fairly confident that my bug was a version
compatibility issue, but in order to resolve it I would need to reverse engineer
the tool-box I was using and given that this could take weeks, I decided it was
likely better to stop chasing this rabbit hole, and continue my exportation
proof of concept with other code that was more integral to the project.  As such
I spoke with my team members and will continue my attempts to integrate with one
of their tools.