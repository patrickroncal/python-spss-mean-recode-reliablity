# python-spss-mean-recode-reliablity
The purpose of this Python tool is to reduce the most routine programming aspects of SPSS.

INTRODUCTION

The purpose of this Python tool is to reduce the most routine programming aspects of SPSS. Using this tool depends on the codebook. It assumes that the numbers for the attributes go in increasing order (i.e. 1, 2, 3, 4, etc.).  And of course, check your work and edit the SPSS code if there are any problems. This instructions manual is intended for an audience without prior knowledge of using Python or SPSS. 

Key benefits of using this Python tool:

•	Easy to use (with a very small learning curve)

•	Eliminates repetitive tasks (such as copying and pasting)

•	Standardizes output, reducing human error

•	Generates source code in bulk, saving time

•	Elegant output


There are two main steps to this tool: (1) SET UP, and (2) INPUT.


(1)	SET UP
i.	Open Python.

•	You can access Python remotely by visiting this website online:

http://live.sympy.org/

•	You can check if Python is on your workstation by clicking “Start” on the bottom right hand corner and searching for “Python” in the program search. Apple products have Python by default.

ii.	Copy and paste the text from one of the attached1 text files into Python. Press Enter.

iii.	Repeat step 1-ii for each text file. There are five files.

1This file should be contained in a folder with the necessary text files. Appendix A also has the original Python source code. 

(2)	INPUT

To summarize, we have these functions to use:

(2.A) Function for mean (single attribute): M(title, number)

(2.B) Function for additional attributes in mean: AM(title,number) 

(2.C) Function for recoding: REC(list,number)

(2.D) Function for reliability (single attribute): REL(title,number)

(2.E) Function for additional attributes in reliabilities: AR(title,number)


(2.A)	M(title,number): If you would like to calculate the mean for one single variable, use the M(title,number) function. (M stands for Mean)

i.	Type M(title,number) into Python.

ii.	Replace title with the name of your measure attribute. Use apostrophes! 

iii.	Replace number with the number of this measure attribute.

iv.	Press Enter. 

v.	Check your work and then copy and paste the output from Python into SPSS. 


For example:
Input:

M(“Extroversion_”, 5)


Output:

* ** *** **** Mean of Extroversion_ *** ** * Compute Extroversion__Mean=Mean( Extroversion_1,  Extroversion_2,  Extroversion_3,  Extroversion_4,  Extroversion_5). Execute
*********

Input:

M(“Friendly”,4)

Output:

* ** *** **** Mean of Friendly *** ** * 
Compute Friendly_Mean=Mean( Friendly1,  Friendly2,  Friendly3,  Friendly4). Execute *********

(2.B)	AM(title, number): Sometimes, there are more than one attribute name in your mean. If you would like to calculate the mean for multiple attributes, use the M(title,number) function first and then use the AM(title, number) function. (AM stands for Additional attributes for mean)

AM(title,number) outputs the exact same thing as M(title,number), but without all of the extra text and just the variable names. You can copy and paste this into your SPSS code outputted from M(title,number).


For example:

Input:

AM(“Outgoing_”, 3)

Output:

Outgoing_1,  Outgoing_2,  Outgoing_3

Then you can copy and paste this into your Friendly SPSS source code:

* ** *** **** Mean of Friendly *** ** * 
Compute Friendly_Mean=Mean( Friendly1,  Friendly2,  Friendly3,  Friendly4, Outgoing_1,  Outgoing_2,  Outgoing_3). Execute *********


(2.C) REC(list,number): If you would like to recode a scale for a list of some attributes, use the recode function: REC(list,number)

i.	First, create a list of the names of the attributes you would like to recode. Type list = [“….R”,”….R”,”….R”] into Python where “….R” are the names of the attributes with the letter R at the very end. Remember to use apostrophes. Press Enter
For example, type in: list=[“Happiness2R”,”Happiness3R”,”Happiness7R”]

ii.	Type REC(list,number) into Python.

iii.	Replace number with the number of the scale you would like to invert.

iv.	Press Enter. 
v.	Check your work and then copy and paste the output from Python into SPSS.

For example:
Input:
list=[“Happiness2R”,”Happiness3R”,”Happiness7R”]
REC(list,8) 

Output:
RECODE  Happiness2R Happiness3R Happiness7R 1=5 2=4 3=3 4=2 5=1 INTO  Happiness2 Happiness3 Happiness7


(2.D) REL(title,number): If you would like to calculate the reliability for one single variable, use the REL(title,number) function. (REL stands for Reliability)
i.	Type REL(title,number) into Python.
ii.	Replace title with the name of your measure attribute. Use apostrophes! 
iii.	Replace number with the number of this measure attribute.
iv.	Press Enter. 
v.	Check your work and then copy and paste the output from Python into SPSS. 

For example:
Input:
REL(“Extroversion_”, 5)

Output:
* ** *** **** Reliability of Extroversion_ *** ** * RELIABILITY  /VARIABLES=  Extroversion_1 Extroversion_2 Extroversion_3 Extroversion_4 Extroversion_5  /SCALE('ALL VARIABLES') ALL  /MODEL=ALPHA. *********




(2.E)	AR(title, number): Sometimes, there are more than one attribute name in your reliability. If you would like to calculate the reliability for multiple attributes, use the REL(title,number) function first and then use the AR(title, number) function. (AR stands for Additional attributes for Reliability)

AR(title,number) outputs the exact same thing as REL(title,number), but without all of the extra text and just the variable names. You can copy and paste this into your SPSS code outputted from REL(title,number).

For example:
Input:
AR(“Outgoing_”, 3)

	Output:
	Outgoing_1 Outgoing_2 Outgoing_3

	Then you can copy and paste this into your Extroversion SPSS
source code:

* ** *** **** Reliability of Extroversion_ *** ** * RELIABILITY  /VARIABLES=  Extroversion_1 Extroversion_2 Extroversion_3 Extroversion_4 Extroversion_5 Outgoing_1 Outgoing_2 Outgoing_3  /SCALE('ALL VARIABLES') ALL  /MODEL=ALPHA. *********


