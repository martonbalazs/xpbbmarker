# xpbbmarker
Scripts for an assignment marking workflow with Xournal++

Some help with marking homeworks and exams. Directory and file structure are compatible with our downloads from Blackboard; the scripts then help with the workflow of annotating pdf assignments and adding marks. Vim, Xournalpp and Libreoffice are assumed to be available. Explanation video: <https://youtu.be/4KaaEbDr_-k>

See the "test_course" folder for an example structure of assignments to mark. It is pretty much the way they come from Blackboard: assignments come in folders named after students' id's. The name of the pdf's inside is irrelevant. The assignments must be in folders called "hw[n]" or "exam". These must be subfolders of a common folder. No spaces in filenames please - I never use them and haven't tested. (In my "cli_file_util" repo I have a script to clean filenames.)

Go to either of the "hw[n]" or "exam" folders, create a template file called "templ[anything].txt" for marking (see examples in "test_course/") and run (perhaps from your path) "xpbbmarker". It will open the xls file (that is normally provided by Blackboard), then go through the assignments of that folder, opens them in Xournalpp with an auxiliary feedback txt file based on the template. Enter the marks in the line that starts with "Mark:". Once the text file is closed, the script does the additions and presents the file again for copy-pasting the sums into Xournalpp. Once done, save the Xournalpp file adding "d" to "annotate" in the filename and also export the annotated pdf under this same name. The script will keep the text file and the annotated pdf in "hw[n]" or "exam", while a copy of the .xopp file plus the pdf assignment will be moved into the student's subfolder. This can later be edited manually in Xournalpp if necessary.

After every completed assignment the script can be stopped by pressing "q" on the prompt, otherwise it continues to the next assignment. When re-run, assignments with already a text feedback file are not considered. Yes, we sometimes mark over multiple days. :-)

When all assignments are marked, the text feedback files are again presented to copy into or compare with the still open xls file.

The other script, "xphwexjoin", again needs to be run from one of the "hw[n]" or "exam" folders. It will look for all students with text feedback file and collect their marks across all available homeworks and exam in a .csv format. This script doesn't write or modify files, save its output by "xphwexjoin > [filename].csv" if needed.

I'm no programmer, so please don't blame me on the quality of the code. :-)
Licensed under GNU GPLv3.
