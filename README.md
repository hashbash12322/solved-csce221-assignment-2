Download Link: https://assignmentchef.com/product/solved-csce221-assignment-2
<br>
<ol>

 <li>In this assignment, the sort program reads a sequence of integers either from the screen (standard input) or from a file, and outputs the sorted sequence to the screen (standard output) or to a file. The program can be configured to show total running time and/or total number of comparisons done in the sort.</li>

 <li>This program does not have a menu but takes arguments from the command line. The code for interface is completed in the template programs, so you only have to know how to execute the program using the command line.</li>

</ol>

The program usage is as follows.<em> Note that options do not need to be specified in a fixed order. </em>Usage:

./sort [-a ALGORITHM] [-f INPUTFILE] [-o OUTPUTFILE] [-h] [-d] [-p] [-t] [-c] Example:

./sort -h

./sort -a S -f input.txt -o output.txt -d -t -c -p

./sort -a I -t -c

./sort Options:

<ul>

 <li>ALGORITHM: Use ALGORITHM to sort.</li>

</ul>

ALGORITHM is a single character representing an algorithm:

S for selection sort

B for bubble sort

I for insertion sort

H for shell sort

R for radix sort

-f INPUTFILE: Obtain integers from INPUTFILE instead of STDIN

-o OUTPUTFILE: Place output data into OUTPUTFILE instead of STDOUT

-h: Display this help and exit

-d: Display input: unsorted integer sequence

-p: Display output: sorted integer sequence

-t: Display running time of the chosen algorithm in milliseconds

-c: Display number of comparisons (excluding radix sort)

<ol start="3">

 <li>Format of the input data. The first line of the input contains a number<em> n</em> which is the number of integers to sort. Subsequent<em> n</em> numbers are written one per line which are the numbers to sort. Here is an example of input data:</li>

</ol>

5 // this is the number of lines below = number of integers to sort

7

-8

4

0

-2

<ol start="4">

 <li>Format of the output data. The sorted integers are printed one per line in increasing order. Here is the output corresponding to the above input:</li>

</ol>

-8

-2

0

4

7

<ol start="5">

 <li>(<em>50 points</em>) Your tasks include implementing the following five sorting algorithms in corresponding cpp files.

  <ul>

   <li>selection sort in selection-sort.cpp</li>

   <li>insertion sort in insertion-sort.cpp</li>

   <li>bubble sort in bubble-sort.cpp</li>

   <li>shell sort in shell-sort.cpp</li>

   <li>radix sort in radix-sort.cpp

    <ol>

     <li>Implement the radix sort algorithm that can sort 0 to(2<sup>16</sup><em>−</em>1) but takes input <em>−</em>2<sup>15 </sup>to (2<sup>15</sup><em>−</em>1) .</li>

     <li>About radix sort of negative numbers: “You can shift input to all positive numbers by adding a number which makes the smallest negative number zero. Apply radix sort and next make a reverse shift to get the initial input.”</li>

    </ol></li>

  </ul></li>

</ol>

<ol start="6">

 <li>Generate the sets of the sizes 10<sup>2</sup>, 10<sup>3</sup>, 10<sup>4</sup>, and 10<sup>5 </sup>integers in three different orders.

  <ul>

   <li>random order</li>

   <li>increasing order</li>

   <li>decreasing order</li>

  </ul></li>

</ol>

HINT: The standard library &lt;cstdlib&gt;provides functions srand() and rand() to generate random numbers.

<ol start="7">

 <li>Measure the average number of comparisons (excluding radix sort) and average running times of each algorithms on the 12 integer sequences.

  <ul>

   <li>(<em>20 points</em>) Insert additional code into each sort (excluding radix sort) to count the number of<em> comparisons performed on input integers</em>. The following tips should help you with determining how many comparisons are performed.

    <ol>

     <li>You will measure 3 times for each algorithm on each sequence and take average</li>

     <li>Insert the code that increases number of comparison num_cmps++typically in an if or a loop statement</li>

    </ol></li>

  </ul></li>

</ol>

<ul>

 <li>Remember that C++ uses the shortcut rule for evaluating boolean expressions. A way to count comparisons accurately is to use comma expressions. For instance while (i &lt; n &amp;&amp; (num_cmps++, a[i] &lt; b))</li>

</ul>

HINT: If you modify sort.cpp and run several sorting algorithms subsequently, you have to call resetNumCmps() to reset number of comparisons between every two calls tos-&gt;sort() .

<ul>

 <li>Modify the code in sort.cpp so that it repeatedly measures the running time ofs-&gt;sort() .

  <ol>

   <li>You will measure roughly 10<sup>7 </sup>times for each algorithm on each sequence and take the average. You have to run for the same number of rounds for each algorithm on each sequence, and make sure that each result is not 0.</li>

   <li>When you measure the running time of sorting algorithms, please reuse the input array but fill with different numbers. Do not allocate a new array every time, that will dramatically slower the program.</li>

  </ol></li>

</ul>

<ul>

 <li>To time a certain part of the program, you may use functions clock() defined in header file &lt;ctime&gt;, or gettimeofday()defined in &lt;sys/time.h&gt;. Here are the examples of how to use these functions. The timing part is also completed in the template programs. However, you will apply these function to future assignments.</li>

</ul>

The example using clock() in &lt;ctime&gt;:

#include &lt;ctime&gt;

…

clock_t t1, t2; t1 = clock(); //<em> start timing</em>

…

/*<em> operations you want to measure the running time </em>*/

…

t2 = clock(); //<em> end of timing </em>double diff = (double)(t2 – t1)/CLOCKS_PER_SEC; cout &lt; &lt; “The timing is ” &lt; &lt; diff &lt; &lt; “ ms” &lt; &lt; endl; The example using gettimeofday()in &lt;sys/time.h&gt;:

#include &lt;sys/time.h&gt;

…

struct timeval start, end;

…

gettimeofday(&amp;start,0); //<em> start timing</em>

…

/*<em> operations you want to measure the running time</em> */

…

<ul>

 <li>Report)</li>

</ul>

Write a report that includes all following elements in your report.

<ol>

 <li>A brief description of assignment purpose, assignment description, how to run your programs, what to input and output.</li>

</ol>

The purpose of this assignment was to gain a better understanding of the relative efficiency of different sorting algorithms on a variety of input types, both in terms of number of comparisons and time taken. We are assigned to implement various sorting algorithms and experimentally observe their running times.We are supposed to implement 5 sorting algorithms: selection sort, insertion sort, bubble sort, shell sort, and radix sort. The program is run by the command ./sort [-a] [-f] [-o] [-h] [-d] [-p] [-t] [-c]. The command line arguments correspond to the desired algorithm, input file, output file, whether or not the user wants to display the help, display input, display output, display running time in milliseconds, and display number of comparisons, excluding radix sort because radix sort is a non-comparison-based sorting algorithm. The user should have the data in an input file,              specified in the command line arguments passed to the main function in the program. Further, we learned the basic use of git and GitHub, as well as some experience in programming as part of a group.

<ol start="2">

 <li>Explanation of splitting the program into classes and<em> a description of C++ object oriented features or generic programming used in this assignment</em>.</li>

</ol>

We split the program into classes so that we could have a general virtual ’sort’ class which could later be cast to one of a number of child classes. This allowed us to handle each preference of sorting type

separately while allowing a common interface for the user. Generic programming features are the general algorithms executed by the various classes, as these are implementable in a similar fashion regardless of language. Object-oriented features include the use of a virtual class which is later cast to a child based upon command line inputs.

<ol start="3">

 <li>Briefly describe the features of each of the five sorting algorithms.</li>

</ol>

Radix Sort- Radix sort uses a series of counting sorts from the least significant to the most significant places on a value, necessitating a stable counting sort algorithm, and taking in values up signed integers between (<em>−</em>2<sup>15</sup>)and (2<sup>15 </sup><em>−</em>1)<em>. </em>It is capable of sorting negative numbers by supplying an offset to make all values positive, and then returning them to their original values with a commensurate negative offset at the end of the process. This particular implementation of radix sort utilizes a byte-level counting sort, which then conducts itself in the usual manner of counting sorts by using three arrays, scanning for indices, cascading addition in the vocabulary array, and then using inverted index referencing to determining the value and number of array cells to be filled. It can sort in linear time with the given constraints of data.

Shell Sort- Shell sort uses a technique of segmenting normally distributed data across an interval into equal sub-intervals. The allocated into the correct sub-interval, and is sorted using insertion sort. Afterwards, the sub-intervals are stitched together, resulting in a sorted list. Because the sub-intervals allocation allows an insertion sort operation to be nearly sorted already, it can approach constant time given normally distributed data, and the other operations are linear.

Bubble Sort- Bubble combs linearly from the first element in the array to the last element of interest, taking up the largest element that it finds and comparing it to its upper neighbor.        After each iteration, it becomes uninterested in the next highest element of interest in the array, thereafter restricting its search to those elements that it considers unsorted. In this way it will always handle data in at least<em> O</em>(<em>n</em><sup>2</sup>) time.

Insertion Sort- Insertion sort, similarly to Bubble sort, combs linearly through the array. However, instead of carrying the largest element to the top, it instead will compare each element to its neighbors and carry small elements to the bottom.   An element<em> x</em> at [a] will be compared to its neighbor<em> y</em> at [a+1]:           if it is larger, then it will switch their indices. Then,<em> y</em> at [a] will be compared to the element at [a – 1] . This will continue until all elements are sorted, and it runs also in<em> O</em>(<em>n</em><sup>2</sup>) time.

Selection Sort- Selection sort will go through the element from smallest element to largest, and on each iteration compare the first element to every other in the list. If it finds that another element is smaller, then it will place that one at the front of the list. This algorithm has both a best and worst case of<em> n</em><sup>2</sup>time, and is horribly inefficient.

<ol start="4">

 <li>Theoretical Analysis. Theoretically analyze the time complexity of the sorting algorithms with input integers in decreasing, random and increasing orders and fill the second table.   Fill in the first table with the time complexity of the sorting algorithms when inputting the best case,     average case and worst case. Some of the input orders are exactly the best case, average case and worst case of the sorting algorithms. State what input orders correspond to which cases. You should use big-O asymptotic notation when writing the time complexity (running time).</li>

</ol>

<table width="339">

 <tbody>

  <tr>

   <td width="91">Complexity</td>

   <td width="70">best</td>

   <td width="89">average</td>

   <td width="89">worst</td>

  </tr>

  <tr>

   <td width="91">Selection Sort</td>

   <td width="70"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Insertion Sort</td>

   <td width="70"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Bubble Sort</td>

   <td width="70"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Shell Sort</td>

   <td width="70"><em>O</em>(<em>n</em> log<em> n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em>(log<em> n</em>))<sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em>(log<em> n</em>))<sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Radix Sort</td>

   <td width="70"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em>) or<em> O</em>(<em>k</em>)</td>

  </tr>

  <tr>

   <td width="91">Complexity</td>

   <td width="70">inc</td>

   <td width="89">ran</td>

   <td width="89">dec</td>

  </tr>

  <tr>

   <td width="91">Selection Sort</td>

   <td width="70"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Insertion Sort</td>

   <td width="70"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Bubble Sort</td>

   <td width="70"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em><sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Shell Sort</td>

   <td width="70"><em>O</em>(<em>n</em> log<em> n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em>(log<em> n</em>))<sup>2</sup>)</td>

   <td width="89"><em>O</em>(<em>n</em>(log<em> n</em>))<sup>2</sup>)</td>

  </tr>

  <tr>

   <td width="91">Radix Sort</td>

   <td width="70"><em>O</em>(<em>n</em>)</td>

   <td width="89"><em>O</em>(<em>n</em>) or<em> O</em>(<em>k</em>)</td>

   <td width="89"><em>O</em>(<em>n</em>) or<em> O</em>(<em>k</em>)</td>

  </tr>

 </tbody>

</table>

<u>inc:</u> increasing order; <u>dec:</u> decreasing order; <u>ran:</u> random order

<ol start="5">

 <li></li>

</ol>

(a) Briefly describe the experiments. Present the experimental running times (RT) and number of comparisons (#COMP) performed on input data using the following tables.

For the experiments, we created lists of incrementing, random and decrementing values.      We extensively tested each algorithm and took an average of the run times. This rigorous testing led us to the following results:

<table width="486">

 <tbody>

  <tr>

   <td width="38">RT</td>

   <td colspan="7" width="152">Selection Sort (ms)</td>

   <td colspan="10" width="149">Insertion Sort (ms)</td>

   <td colspan="8" width="147">Bubble Sort (ms)</td>

   <td width="48"></td>

  </tr>

  <tr>

   <td width="38"><em>n</em></td>

   <td colspan="2" width="51">inc</td>

   <td colspan="2" width="50">ran</td>

   <td colspan="3" width="51">dec</td>

   <td colspan="4" width="48">inc</td>

   <td colspan="3" width="50">ran</td>

   <td colspan="3" width="51">dec</td>

   <td colspan="2" width="48">inc</td>

   <td colspan="3" width="50">ran</td>

   <td colspan="3" width="50">dec</td>

   <td width="48"></td>

  </tr>

  <tr>

   <td width="38">100</td>

   <td colspan="2" width="51">0.043</td>

   <td colspan="2" width="50">0.052</td>

   <td colspan="3" width="51">0.046</td>

   <td colspan="4" width="48">0.003</td>

   <td colspan="3" width="50">0.031</td>

   <td colspan="3" width="51">0.05</td>

   <td colspan="2" width="48">0.003</td>

   <td colspan="3" width="50">0.098</td>

   <td colspan="3" width="50">0.078</td>

   <td width="48"></td>

  </tr>

  <tr>

   <td width="38">10<sup>3</sup></td>

   <td colspan="2" width="51">3.34</td>

   <td colspan="2" width="50">3.51</td>

   <td colspan="3" width="51">3.44</td>

   <td colspan="4" width="48">0.012</td>

   <td colspan="3" width="50">2.23</td>

   <td colspan="3" width="51">4.47</td>

   <td colspan="2" width="48">0.011</td>

   <td colspan="3" width="50">7.21</td>

   <td colspan="3" width="50">7.67</td>

   <td width="48"></td>

  </tr>

  <tr>

   <td width="38">10<sup>4</sup></td>

   <td colspan="2" width="51">175</td>

   <td colspan="2" width="50">196</td>

   <td colspan="3" width="51">279</td>

   <td colspan="4" width="48">0.134</td>

   <td colspan="3" width="50">143</td>

   <td colspan="3" width="51">235</td>

   <td colspan="2" width="48">0.092</td>

   <td colspan="3" width="50">375</td>

   <td colspan="3" width="50">329</td>

   <td width="48"></td>

  </tr>

  <tr>

   <td width="38">10<sup>5</sup></td>

   <td colspan="2" width="51">19332</td>

   <td colspan="2" width="50">21780</td>

   <td colspan="3" width="51">32388</td>

   <td colspan="4" width="48">0.713</td>

   <td colspan="3" width="50">11359</td>

   <td colspan="3" width="51">23823</td>

   <td colspan="2" width="48">0.598</td>

   <td colspan="3" width="50">44540</td>

   <td colspan="3" width="50">49056</td>

   <td width="48"></td>

  </tr>

  <tr>

   <td width="38">RT</td>

   <td colspan="6" width="149">Shell Sort (ms)</td>

   <td colspan="10" width="141">Radix Sort (ms)</td>

   <td colspan="10" width="207"></td>

  </tr>

  <tr>

   <td width="38"><em>n</em></td>

   <td colspan="3" width="55">inc</td>

   <td width="46">ran</td>

   <td colspan="2" width="48">dec</td>

   <td colspan="4" width="48">inc</td>

   <td colspan="2" width="46">ran</td>

   <td colspan="4" width="46">dec</td>

   <td colspan="10" width="207"></td>

  </tr>

  <tr>

   <td width="38">100</td>

   <td colspan="3" width="55">0.007</td>

   <td width="46">0.028</td>

   <td colspan="2" width="48">0.12</td>

   <td colspan="4" width="48">0.062</td>

   <td colspan="2" width="46">0.056</td>

   <td colspan="4" width="46">0.049</td>

   <td colspan="10" width="207"></td>

  </tr>

  <tr>

   <td width="38">10<sup>3</sup></td>

   <td colspan="3" width="55">0.107</td>

   <td width="46">0.428</td>

   <td colspan="2" width="48">0.185</td>

   <td colspan="4" width="48">0.33</td>

   <td colspan="2" width="46">0.328</td>

   <td colspan="4" width="46">0.404</td>

   <td colspan="10" width="207"></td>

  </tr>

  <tr>

   <td width="38">10<sup>4</sup></td>

   <td colspan="3" width="55">1.143</td>

   <td width="46">4.88</td>

   <td colspan="2" width="48">2.16</td>

   <td colspan="4" width="48">2.28</td>

   <td colspan="2" width="46">1.09</td>

   <td colspan="4" width="46">1.91</td>

   <td colspan="10" width="207"></td>

  </tr>

  <tr>

   <td width="38">10<sup>5</sup></td>

   <td colspan="3" width="55">10.205</td>

   <td width="46">55.9</td>

   <td colspan="2" width="48">19</td>

   <td colspan="4" width="48">20.43</td>

   <td colspan="2" width="46">20.56</td>

   <td colspan="4" width="46">20</td>

   <td colspan="10" width="207"></td>

  </tr>

  <tr>

   <td colspan="2" width="65">#COMP</td>

   <td colspan="14" width="252">Selection Sort</td>

   <td colspan="11" width="217">Insertion Sort</td>

  </tr>

  <tr>

   <td colspan="2" width="65"><em>n</em></td>

   <td colspan="4" width="84">inc</td>

   <td colspan="4" width="83">ran</td>

   <td colspan="6" width="85">dec</td>

   <td colspan="5" width="84">ran</td>

   <td colspan="3" width="50">inc</td>

   <td colspan="3" width="83">dec</td>

  </tr>

  <tr>

   <td colspan="2" width="65">100</td>

   <td colspan="4" width="84">4950</td>

   <td colspan="4" width="83">4950</td>

   <td colspan="6" width="85">4950</td>

   <td colspan="5" width="84">2608</td>

   <td colspan="3" width="50">99</td>

   <td colspan="3" width="83">5049</td>

  </tr>

  <tr>

   <td colspan="2" width="65">10<sup>3</sup></td>

   <td colspan="4" width="84">499500</td>

   <td colspan="4" width="83">499500</td>

   <td colspan="6" width="85">499500</td>

   <td colspan="5" width="84">250035</td>

   <td colspan="3" width="50">999</td>

   <td colspan="3" width="83">500499</td>

  </tr>

  <tr>

   <td colspan="2" width="65">10<sup>4</sup></td>

   <td colspan="4" width="84">49995000</td>

   <td colspan="4" width="83">49995000</td>

   <td colspan="6" width="85">49995000</td>

   <td colspan="5" width="84">25222691</td>

   <td colspan="3" width="50">9999</td>

   <td colspan="3" width="83">49994956</td>

  </tr>

  <tr>

   <td colspan="2" width="65">10<sup>5</sup></td>

   <td colspan="4" width="84">4999950000</td>

   <td colspan="4" width="83">4999950000</td>

   <td colspan="6" width="85">4999950000</td>

   <td colspan="5" width="84">2506169125</td>

   <td colspan="3" width="50">99999</td>

   <td colspan="3" width="83">4999950203</td>

  </tr>

  <tr>

   <td colspan="2" width="65">#COMP</td>

   <td colspan="12" width="219">Bubble Sort</td>

   <td colspan="11" width="190">Shell Sort</td>

   <td colspan="2" width="60"></td>

  </tr>

  <tr>

   <td colspan="2" width="65"><em>n</em></td>

   <td colspan="4" width="84">ran</td>

   <td colspan="3" width="50">inc</td>

   <td colspan="5" width="85">dec</td>

   <td colspan="5" width="65">ran</td>

   <td colspan="3" width="63">inc</td>

   <td colspan="3" width="63">dec</td>

   <td colspan="2" width="60"></td>

  </tr>

  <tr>

   <td colspan="2" width="65">100</td>

   <td colspan="4" width="84">4929</td>

   <td colspan="3" width="50">99</td>

   <td colspan="5" width="85">4950</td>

   <td colspan="5" width="65">902</td>

   <td colspan="3" width="63">503</td>

   <td colspan="3" width="63">668</td>

   <td colspan="2" width="60"></td>

  </tr>

  <tr>

   <td colspan="2" width="65">10<sup>3</sup></td>

   <td colspan="4" width="84">499490</td>

   <td colspan="3" width="50">999</td>

   <td colspan="5" width="85">499500</td>

   <td colspan="5" width="65">15683</td>

   <td colspan="3" width="63">8006</td>

   <td colspan="3" width="63">11716</td>

   <td colspan="2" width="60"></td>

  </tr>

  <tr>

   <td colspan="2" width="65">10<sup>4</sup></td>

   <td colspan="4" width="84">49991084</td>

   <td colspan="3" width="50">9999</td>

   <td colspan="5" width="85">49994999</td>

   <td colspan="5" width="65">258010</td>

   <td colspan="3" width="63">120005</td>

   <td colspan="3" width="63">169245</td>

   <td colspan="2" width="60"></td>

  </tr>

  <tr>

   <td colspan="2" width="65">10<sup>5</sup></td>

   <td colspan="4" width="84">4999508670</td>

   <td colspan="3" width="50">99999</td>

   <td colspan="5" width="85">4999950000</td>

   <td colspan="5" width="65">4259397</td>

   <td colspan="3" width="63">1500006</td>

   <td colspan="3" width="63">2196626</td>

   <td colspan="2" width="60"></td>

  </tr>

  <tr>

   <td width="36"></td>

   <td width="27"></td>

   <td width="24"></td>

   <td width="3"></td>

   <td width="47"></td>

   <td width="11"></td>

   <td width="37"></td>

   <td width="3"></td>

   <td width="9"></td>

   <td width="34"></td>

   <td width="2"></td>

   <td width="3"></td>

   <td width="43"></td>

   <td width="3"></td>

   <td width="4"></td>

   <td width="29"></td>

   <td width="11"></td>

   <td width="11"></td>

   <td width="10"></td>

   <td width="39"></td>

   <td width="15"></td>

   <td width="10"></td>

   <td width="25"></td>

   <td width="15"></td>

   <td width="25"></td>

   <td width="13"></td>

   <td width="45"></td>

  </tr>

 </tbody>

</table>

<u>inc:</u> increasing order; <u>dec:</u> decreasing order; <u>ran:</u> random order

As we can see, the run time and number of comparisons do increase with number of elements on the list.

The values for the number of comparison match the intended Big O notation.

(a) For each of the five sort algorithms, graph the running times over the three input cases (inc, ran, dec) versus the input sizes (<em>n</em>); and for each of the first four algorithms graph the numbers of comparisons versus the input sizes, totaling in 9 graphs.

<ol>

 <li>All of these graphs have been plotted in Log base 10 on both values.</li>

</ol>

HINT: To get a better view of the plots,<em> use logarithmic scales</em> for both x and y axes. Just to clarify, the last graph (Shell Sort) should be (Comparisons) on the y-axis.

(a) To compare performance of the sorting algorithms you need to have another 3 graphs to plot the results of all sorts for the running times for<em> each</em> of the input cases (inc, ran, dec) separately.

HINT: To get a better view of the plots,<em> use logarithmic scales</em> for both x and y axes.

<ol>

 <li>Comment on how the experimental results relate to the theoretical analysis and explain any discrepancies you note. Is your computational results match the theoretical     analysis you learned from class or textbook? Justify your answer. Also compare radix sort’s running time with the running time of four comparison-based algorithms.</li>

</ol>

We can see a correlation for between the theoretical and experimental results. For Selection Sort we notice that the BigO asymptotic function is<em> n </em><sup>2</sup>. From our results we can see that we have 4950 comparisons done on to sort our algorithm in all three cases. Even though this seems like only half of the time our comparisons will be done, we know from mathematics that the BigO function must be asymptotically larger than our function,            so our experimental value agrees with our results. Another algorithm we can analyze would be Bubble Sort. From the theoretical predictions we see that the BigO should be a case of O(n) for increasing lists and a O(<em>n   </em><sup>2</sup>) for the average and worst case. Our experimental results do follow this mathematical correlation with the best case being a run time of 0.598ms for the 10<sup>5</sup>inputs and 44540 and 49056 for the average and worst case.

The Radix Runt Time is significantly lower than the three comparison based algorithms but similar to the Shell Sort run times. For the average case, we do see that the Radix perform better than the Shell.

<ol start="2">

 <li>Give your observations and conclusion. For instance, which sorting algorithm seems to perform better on which case? Do the experimental results agree with the theoretical analysis you learned from class or textbook? What factors can affect your experimental results?</li>

</ol>

For the case of small input size (10<sup>2 </sup>and 10<sup>3</sup>), the Shell Sort and Radix Sort seems to be the best algorithms for the least number of comparisons.            The Shell Sort performs at a run time of milliseconds for small input sizes and the Radix sort performs on the millisecond range also. This agrees with our analysis of the BigO for OO(n<sup>2</sup>(logn)) for the average and worst cases for Shell Sort and O(n) for all the cases in Radix sort. When we begin to use larger data sets (10 <sup>4 </sup>and 10<sup>5</sup>), we see that the Radix Sort has the smallest values in Run Time for our inputs. This agrees with our theoretical analysis that states the worst case should be O(n). The factors that could be affecting our experimental results could be the fact that our Radix Sort was implemented with operations on the byte level, and so would be faster to compute than other arithmetic operations regardless of the inherent efficiency of the algorithm. Other factors could be varied computational load on the servers at the times that these algorithms were tested, or even the uncertainty that identical processors are handling our algorithms, given that the server is something of a black box.       One last factor could be the fact that we ran most of the comparisons on a laptop and not TAMU’s Unix servers. These discrepaciencs gave us different runtimes due to the hardware integrated into the seperate machines.