# cs39003-assignment-6-target-code-generator-for-tinyc-solved
**TO GET THIS SOLUTION VISIT:** [CS39003 Assignment 6-Target Code Generator for tinyC Solved](https://www.ankitcodinghub.com/product/cs39003-assignment-6-target-code-generator-for-tinyc-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;92887&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS39003 Assignment 6-Target Code Generator for tinyC Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
6: Target Code Generator for tinyC

1 Preamble – tinyC

The Lexical Grammar (Assignment 3) and the Phase Structure Grammar (As- signment 4) for tinyC have already been defined as subsets of the C language specification from the International Standard ISO/IEC 9899:1999 (E). Finally, three address code (TAC) structure and a further subset of tinyC has been spec- ified (Assignment 5) for translating the input tinyC program to TAC quad array, a supporting symbol table, and other auxiliary data structures.

In this assignment you will write a target code translator from the TAC quad array (with the supporting symbol table, and other auxiliary data structures) to the assembly language of x86-64. The translation is now machine-specific and your generated assembly code would be translated with the gcc assembler to produce the final executable codes for the tinyC program.

</div>
</div>
<div class="layoutArea">
<div class="column">
2

•

•

</div>
<div class="column">
Scope of Target Translation

For simplicity restrict tinyC further:

<ol>
<li>Skip shift and bit operators.</li>
<li>Support only void, int, and char types. Skip double type.</li>
<li>Support only one–dimensional arrays.</li>
<li>Support only void, int, char, void*, int*, and char* types for returns types of functions.</li>
<li>No type conversion to be supported.</li>
</ol>
For I/O, provide a library (as created in Assignment 2) using in-line as-

sembly language program of x86-64 along with syscall for gcc assembler.:

– int printStr(char *) – prints a string of characters. The parame- ter is terminated by ‘\0’. The return value is the number of characters printed.

– int printInt(int n) – prints the integer value of n (no newline). It returns the number of characters printed.

– int readInt(int *eP) – reads an integer (signed) and returns it. The parameter is for error (ERR = 1, OK = 0).

The header file myl.h of the library will be as follows:

<pre>#ifndef _MYL_H
#define _MYL_H
#define ERR 1
#define OK 0
int printStr(char *);
int printInt(int);
int readInt(int *eP);  // *eP is for error, if the input is not an integer
#endif
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
1

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
Memory Binding

</div>
<div class="column">
This deals with the design of the allocation schema of variables (including parameters and constants) that associates each variable to the respective address expression or register. This needs to handle the following:

• Handle local variables, parameters, and return value for a function. These are automatic and reside in the Activation Record (AR) of the function. Various design schema for AR are possible based on the calling sequence protocol. A sample AR design could be as follows:

</div>
</div>
<div class="layoutArea">
<div class="column">
3 Design of the Translator

The steps for target code generation were outlined in Target Code Generation lecture presentations. In this assignment, however, you do not need to deal with any machine-independent or machine-specific optimization. Hence the transla- tion comprises the following major steps only:

</div>
</div>
<div class="layoutArea">
<div class="column">
Offset Stack Item

–ve Saved Registers –ve Callee Local Data

0 Base Pointer of Caller Return Address

+ve Return Value +ve Parameters

</div>
<div class="column">
Responsibility

Callee Saves &amp; Restores Callee defines and uses Callee Saves &amp; Restores Saved by call, used by ret Callee writes, Caller reads Caller writes, Callee reads

</div>
</div>
<div class="layoutArea">
<div class="column">
Code Translation

</div>
<div class="column">
Activation Record Structure with Management Protocol

<ul>
<li>– &nbsp;Offset’s in the AR are with respect to the Base Pointer of Callee.</li>
<li>– &nbsp;Return Value can alternatively be returned through a register
(like accumulator).
</li>
<li>– &nbsp;The AR will be populated from the Symbol Table of the function.</li>
<li>– &nbsp;Symbol Tables of nested blocks will be flattened and its variables
allocated within the Symbol Table (and hence the AR) of the function where there occur in. Necessary name mangling will be performed to to take care of same lexical name for different variables in different nested scopes.
</li>
</ul>
<ul>
<li>Handle global variables (note that local static variables are not al- lowed in tinyC) as static and generate allocations in static area. This will be populated from global symbol table (ST.gbl).</li>
<li>Generate Constants from Table of Constants – handle string con- stants as assembler symbols in DATA SEGMENT and integer con- stants as parts of target code (TEXT SEGMENT)</li>
<li>Register Allocations &amp; Assignment: Create memory binding for vari- ables in registers:
<ul>
<li>– &nbsp;After a load / store the variable on the activation record and the register have identical values</li>
<li>– &nbsp;Registers can be used to store temporary computed values</li>
<li>– &nbsp;Register allocations are often used to pass int or pointer param-
eters
</li>
<li>– &nbsp;Register allocations are often used to return int or pointer values
Note: Refer to Run-Time Environment lecture presentations for details and examples on memory binding.

This deals with the translation of 3–Address quad’s to x86-64 assembly code. This needs to handle:
</li>
</ul>
<ul>
<li>Generation of Function Prologue – few lines of code at the beginning of a function, which prepare the stack and registers for use within the function.</li>
<li>Generate Function Epilogue – appears at the end of the function, and restores the stack and registers to the state they were in before the function was called.</li>
</ul>
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
• Map 3–Address Code to Assembly – to translate the function body do:

<ul>
<li>– &nbsp;Choose optimized assembly instructions for every expression, as- signment and control quad.</li>
<li>– &nbsp;Use algebraic simplification &amp; reduction of strength for choice of assembly instructions from a quad.</li>
<li>– &nbsp;Use Machine Idioms (like inc for i++ or ++i in place of add reg, 1).
Note: Refer to Target Code Generation lecture presentations for details. Target Code Integrate all the above code into an Assembly File for gcc assembler.
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
4

1.

2. 3.

4.

</div>
<div class="column">
The Assignment

Write a target code (x86-64) translator from the 3-Address quad’s gen- erated from the flex and bison specifications of tinyC (with restrictions

as mentioned in Section 2). Assume that the input tinyC file is lexically, syntactically, and semantically correct. Hence no error handling and / or recovery is expected.

Prepare a Makefile to compile and test the project.

Prepare test input files ass6 roll test&lt;number&gt;.c to test the target code

translation and generate the translation output in ass6 roll &lt;number&gt;.asm.

</div>
</div>
<div class="layoutArea">
<div class="column">
Name your files as follows:

File

Flex Specification

Bison Specification

Data Structures (Class Definitions) and Global Function Prototypes

Data Structures, Function Implementa- tions and 3–Address Translator

Target Translator and x86-64 Transla- tor main()

Test Inputs

3–Address Test Outputs

Test Outputs

</div>
<div class="column">
Naming

ass6 roll.l

ass6 roll.y

ass6 roll translator.h

ass6 roll translator.cxx

ass6 roll target translator.cxx

ass6 roll test&lt;number&gt;.c ass6 roll quads&lt;number&gt;.out ass6 roll &lt;number&gt;.asm

</div>
</div>
<div class="layoutArea">
<div class="column">
5.

</div>
<div class="column">
Prepare a tar-archive with the name ass6 roll.tar containing all the files and upload to Moodle.

</div>
</div>
</div>
