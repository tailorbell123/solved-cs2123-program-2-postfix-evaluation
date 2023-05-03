Download Link: https://assignmentchef.com/product/solved-cs2123-program-2-postfix-evaluation
<br>
This is a continuation of Program #1 (Infix to Postfix).  In this assignment, we evaluate the postfix expressions.  I have provided a driver, include file, and data files.




This program is important in helping you understand

<ul>

 <li>Using a stack to evaluate postfix</li>

 <li>Integrating your code with someone else’s code (mine) Techniques for error handling</li>

 <li>The use of unions.</li>

</ul>




<strong>Input</strong>:

There are two input files:  course data and queries.  See cs2123p2Driver.c for more information.







<strong>Process</strong>: (green highlighting indicates work you previously did and yellow highlighting indicates your new work):

<ul>

 <li>Read the course data (as in Program #0) and print the course data (as in program #0).</li>

 <li>Read the infix expressions as was done in Program #1.  For each expression:

  <ol>

   <li>Convert the infix to postfix (as in Program #1).</li>

   <li>Evaluate the postfix expression, producing an array of booleans (one entry for each course).</li>

   <li>Print the infix expression, the postfix form of the expression, and evaluated result. The driver does this.</li>

  </ol></li>

</ul>




<table width="480">

 <tbody>

  <tr>

   <td colspan="4" width="480">Iterate over the list of courses and then evaluate the query for each course.  The</td>

  </tr>

  <tr>

   <td colspan="3" width="434">operator evaluation result is simply true or false (since only one course is</td>

   <td rowspan="3" width="46"> </td>

  </tr>

  <tr>

   <td width="73">considered).</td>

   <td colspan="2" width="361"> </td>

  </tr>

  <tr>

   <td colspan="2" width="402">•    For N courses, this approach evaluates the same query N times.</td>

   <td width="32"> </td>

  </tr>

  <tr>

   <td width="73"></td>

   <td width="328"></td>

   <td width="32"></td>

   <td width="46"></td>

  </tr>

 </tbody>

</table>

<strong>Approaches for Evaluating Operators  </strong>Approach #1:

<ul>

 <li>The operator result (i.e., a boolean) must be stacked.</li>

</ul>

Approach #2: When evaluating an operator, iterate over the courses to determine if each course satisfies the operator.    The operator evaluation result is an array corresponding to the course array with a boolean indicating whether the course satisfies the result.

<ul>

 <li>A query is evaluated once.</li>

 <li>Each operator will iterate over the list of N courses.</li>

 <li>The operator result (i.e., the array of booleans) must be stacked.</li>

</ul>

<strong>We will use approach #1. </strong>




<strong>Additional functions provided by Larry</strong>:

void printQueryResult(Course courseM[], int iNumCourse, QueryResult resultM[])  Prints the courses which have a corresponding element in the resultM array turned on.

int never(Course *pCourse, Attr attr)

Determines whether a course has a particular attribute (type and value).  If it doesn’t, never returns TRUE; otherwise, it returns FALSE.

int getCourseData(Course courseM[])

Gets course data and their corresponding attributes (type and values).

<strong> </strong>

<strong>Use of union </strong>

Since the evaluation needs two types of elements, we will use <strong>union</strong> as shown in the include file.




Some Files for your use:

p2Query.txt – data file containing infix expressions which are evaluated as queries p2Course.txt – course data file similar to program #0. cs2123p2.h – include file for Program #2

cs2123p2Driver.c – driver program that I provided.  It has several useful routines to help reduce your effort.  Please review this code




Your coding:

<ul>

 <li>Create your code in <strong>cs2123p2.c</strong> (not cs2123p2Driver.c). Based on what the driver calls, you need to create (at least) these functions:</li>

</ul>

int convertToPostFix(char *pszInfix, Out out)

// you did this in program #1

It returns 0 if it converted successfully.  Otherwise, it returns a value which indicates an error in

the infix data (e.g., missing left paren, missing right paren) It populates the out array using the addOut function (provided in the driver).

void printCourseData(Course courseM[], int iNumCourse)

This was done in program #0. void evaluatePostfix(PostfixOut out, Course courseM[], int iNumCourse

, QueryResult resultM[])

This evaluates a postfix expression (which is in out) using the courseM array.  For each course satisfying the posftfix query, it sets its corresponding position in resultM to TRUE.

int atLeastOne(Course *pCourse, Attr attr)

Determines whether a course has a particular attribute (type and value).  If it does, atLeastOne returns TRUE; otherwise, it returns

FALSE.

int only(Course *pCourse, Attr attr)

This looks at EACH attribute in the course’s attrM array for the specified course.  If the attribute’s szAttrType matches the specified szAttrType, then its corresponding szAttrValue must match the specfied attribute value.  If it doesn’t match the attribute value, FALSE is returned.  only examines each of the attributes for the specified course.

You will also have to provide code for AND and OR.

<ul>

 <li>Modify the Makefile from program #1 to reference p2 for each of the files.</li>

</ul>




Requirements:

<ol>

 <li>Your code must be written according to my programming standards.</li>

 <li>You should not have to modify cs2123p2Driver.c. If you want to modify it, please see me before you do that.</li>

 <li>Turn in your C code, include files, and output generated using the specified input file.</li>

 <li>Make certain you free up allocated memory (e.g., stack).</li>

 <li>Modularity matters.</li>

</ol>




<h1></h1>