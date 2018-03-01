With the ability to display the results, the next step in the GUI was to allow
the user to upload more types of files than just wav files.  While the audio
analysis functions require the audio in wav format, the original data files are
more commonly in video form.  (Our data set is specifically avi files, although
I intend to support at least both avi and m4v file types)  This would allow for
a more intuitive local functionality for the user, as previously we had to
manually extract the audio from the video files using a tool like audacity.

My research on this found that while there was no native tools for python to
accomplish this, there is a terminal program, [FFmpeg](www.ffmpeg.org), which
can convert between audio and video formats.  There are a few python wrappers
for ffmpeg.  However, instead of using those, I decided to call it as a
subprocess from python as that simplified both the decencies required for the
GUI tool and the event handler code.

Despite a large amount of time and effort put into continuing to try to figure
out how to exporting MATLAB code to an other form that does not require a
license to run and can ideally be trigged by a python event, I still have not
made any determinable process.  The documentation suggests that there is both a
way to compile a MATLAB script into a standalone executable and a way to export
it to a python module.  Using a simple proof-of-concept “hello world” script
I’ve been attempting to try both paths.  I did find some new information about
the MATLAB Runtime Engine yesterday, so hopefully that will lead to more
success next week.