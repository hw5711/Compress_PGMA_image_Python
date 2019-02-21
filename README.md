# compress PGMA image(Python)

Submission Instructions:
Multimedia Assignment 1 January 30, 2019 Due February 12, 2019
 1. Please submit your work directly in TRACS (using the TRACS editor) or as a text/MS-word/PDF attachment by the due date/time. Please use only zip for compression.
2. It must be your own work – a penalty of at least one grade in your final grade and a report to the Dean of Students will result from sharing work or using other people work.
3. Please submit only the source code of your program in C/C++/Java/Python or Matlab. If I have doubts or concerns about your program. I might request that you submit the entire files required to produce a working program under Linux so that I can test your submission.
4. Please write your name in the assignment header and as a part of the file name of the attachment.
5. Please do not submit your assignment via email. If you miss the deadline, then please submit it on TRACS and
send me an email notification.
6. A penalty of 10% per day will be assessed for late submission and it will be graded at the end of the semester.
7. The code should include remarks that explain any non-trivial part of the program.
8. A question or two related to this assignment are very likely to be in the midterm and / or final examination
Note that you do not have to generate the tree only the resultant image.
Assignment Instructions:
Enclosed is a PGM (or PGMA for PGM ASCII) image – baboon.pgma as well as the Wikipedia description of the format. You can use GIMP or ImageMagick to display pgma images. Additionally you can use Photoshop / Linux. Additional information can be found in: http://people.sc.fsu.edu/~jburkardt/data/pgma/pgma.html
Your tasks are:
1. Develop a program to create a quad tree based image of an input pgma image with up to 256-gray levels.
The program should have a parameter “variance threshold” that can get values between 0 and 1024.
a. First, the program treats the entire image as a quad
b. Next, for each quad
i. If the quad contains only one pixel the program stops
ii. If the variance of the quad is equal to or below the threshold, the program replaces the
entire pixels of the quad with the average value of the pixels in the quad and stops. Note: You should actually create a new pgma image and when you write the new value of a quad you should write it into the new pgma image.
iii. If the variance of the quad is above the threshold the program divides the quad into four even quads and works on each of these quad recursively.
Note: the definition is recursive. Yet, recursive implementation is very inefficient and can result in a very slow execution or stack overflow. Nevertheless, it is easier to develop the recursive version of the program. So, you are allowed to use recursion
2. Test your program with the original baboon image using variance the thresholds 0, 16, 64, and 256.
3. You can use other images from TRACS for further testing.
4. Run an LZ based compression program such as zip, pkzip, rar, and UNIX compress on the original image and
on the quad based generated image and report the sizes before and after compression. Analyze the result
of these values.
Notes:
1) You do not have to write the LZ based program. Use any available program.
2) To estimate 𝑝̅ the average of pixels in a quadrant use: 𝑝̅ = 􏰀 ∑􏰁 𝑃 where 𝑃 is a pixel in the quadrant.
    􏰀 􏰁􏰂􏰃􏰀􏰂 􏰂
 3) To estimate the quadrant variance (𝜎 ) use 𝜎 = ∑ (𝑃 −𝑃) 􏰁􏰅􏰀 􏰂􏰃􏰀 􏰂 􏰆
􏰄􏰄􏰁􏰇􏰄
 
PGMA Files Portable Gray Map (ASCII)
PGMA is the ASCII portable gray map format. It is a simple grayscale image description. The definition is as follows:
􏰈 The typical file extension is ".pgm", but an extension of ".pnm" is also occasionally used.
􏰈 A "magic number" for identifying the file type. An ASCII PGM file's magic number is the two
characters "P2".
􏰈 Whitespace (blanks, TABs, CRs, LFs).
􏰈 A width, formatted as ASCII characters in decimal.
􏰈 Whitespace.
􏰈 A height, again in ASCII decimal.
􏰈 Whitespace.
􏰈 The maximum gray value, again in ASCII decimal.
􏰈 Whitespace.
􏰈 Width * height gray values, each in ASCII decimal, between 0 and the specified maximum value,
separated by whitespace, starting at the top-left corner of the gray map, proceeding in normal
English reading order. A value of 0 denotes black and the maximum value denotes white.
􏰈 Characters from the “#" to the next end-of-line are ignored (comments). No line should be longer than 70 characters.
PGMA example
The PGM and PPM formats (both ASCII and binary versions) have an additional parameter for the maximum value in a line between the X and Y dimensions and the actual pixel data.
P2
# Shows the word "FEEP" (example from Netpbm man page on PGM) 24 7
15
000000000000000000000000
0 3 3 3 3 0 0 7 7 7 7 0 0 11 11 11 11 0 0 15 15 15 15 0
0 3 0 0 0 0 0 7 0 0 0 0 0 11 0 0 0 0 0 15 0 0 15 0
0 3 3 3 0 0 0 7 7 7 0 0 0 11 11 11 0 0 0 15 15 15 15 0
0 3 0 0 0 0 0 7 0 0 0 0 0 11 0 0 0 0 0 15 0 0 0 0
0 3 0 0 0 0 0 7 7 7 7 0 0 11 11 11 11 0 0 15 0 0 0 0 000000000000000000000000
Example:
          
