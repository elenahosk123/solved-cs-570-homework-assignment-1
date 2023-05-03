Download Link: https://assignmentchef.com/product/solved-cs-570-homework-assignment-1
<br>
<h1>1        Assignment Policies</h1>

<strong>Collaboration Policy. </strong>Homework will be done individually: each student must hand in their own answers. It is acceptable for students to collaborate in understanding the material but not in solving the problems or programming. Use of the Internet is allowed, but should not include searching for existing solutions.

<strong>Under absolutely no circumstances code can be exchanged between students. </strong>Excerpts of code presented in class can be used.

<strong>Your code must include a comment with your name.</strong>

<h1>2        Assignment</h1>

Define a class BinaryNumber that represents binary numbers and a few simple operations on them, as indicated below. An example of a binary number is

1011

Its <em>length </em>is 4. Note that its leftmost digit is the least significant one: it represents the decimal number 1∗2<sup>0 </sup>+0∗2<sup>1 </sup>+1∗2<sup>2 </sup>+1∗2<sup>3 </sup>= 13. This is called <em>little-endian </em>format. You may use <em>bigendian </em>if you prefer; in that case you must state so at the beginning of your code as part of the comment.

This assignment requests that a number of operations be supported. They are divided into two groups. The first is a set of basic operations, the second is slightly more challenging and addresses addition of binary numbers.

<h2>2.1       Basic operations</h2>

The following operations should be supported:

<ul>

 <li>A constructor BinaryNumber(int length) for creating a binary number of length length and consisting only of zeros.</li>

 <li>A constructor BinaryNumber(String str) for creating a binary number given a string. For example, given the string “1011”, the corresponding binary number should be created. For this exercise you will have to use some standard String operations. These are listed in the “Hints” section below.</li>

 <li>An operation int getLength() for determining the length of a binary number.</li>

 <li>An operation int getDigit(int index) for obtaining a digit of a binary number given an index. The starting index is 0. If the index is out of bounds, then a message should be printed on the screen indicating this fact.</li>

 <li>An operation int toDecimal() for transforming a binary number to its decimal notation (cf. the example given above).</li>

 <li>An operation void shiftR(int amount) for shifting all digits in a binary number any number of places to the right, as indicated by a parameter amountToShift. The new digit should be 0. For example, the result of shifting “1011” 3 places to the right should yield “0001011”.</li>

</ul>

<h2>2.2       Addition of Binary Numbers</h2>

Here is an example of how two binary numbers of the same length are added<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>.

<table width="410">

 <tbody>

  <tr>

   <td width="156"></td>

   <td width="23"></td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="24">1</td>

   <td width="43"></td>

   <td width="97">(carried digits)</td>

  </tr>

  <tr>

   <td width="156"></td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="24">0</td>

   <td width="43"></td>

   <td width="97"></td>

  </tr>

  <tr>

   <td width="156">                                 +</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="24">0</td>

   <td width="43"></td>

   <td width="97"></td>

  </tr>

  <tr>

   <td width="156">                                 =</td>

   <td width="23">0</td>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="24">1</td>

   <td width="43">= 20</td>

   <td width="97"></td>

  </tr>

 </tbody>

</table>

Note that it is possible for the addition of two numbers to yield a result which has a larger length than the summands. In that case, this should be flagged by an appropriate boolean data field. Here is such an example.

<table width="421">

 <tbody>

  <tr>

   <td width="144"></td>

   <td width="23"></td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="24">1</td>

   <td width="43"></td>

   <td width="97">(carried digits)</td>

  </tr>

  <tr>

   <td width="144"></td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="24"></td>

   <td width="43"></td>

   <td width="97"></td>

  </tr>

  <tr>

   <td width="144">                              +</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="24"></td>

   <td width="43"></td>

   <td width="97"></td>

  </tr>

  <tr>

   <td width="144">                              =</td>

   <td width="23">0</td>

   <td width="23">0</td>

   <td width="23">1</td>

   <td width="23">0</td>

   <td width="23">0</td>

   <td width="24">1</td>

   <td width="43">= 36</td>

   <td width="97"></td>

  </tr>

 </tbody>

</table>

This data field should be added to the data fields of the class BinaryNumber. Implement the following operations:

<ul>

 <li>void add(BinaryNumber aBinaryNumber) for adding two binary numbers, one is the binary number that receives the message and the other is given as a parameter. If the lengths of the binary numbers do not coincide, then a message should be printed on the screen indicating this fact. Otherwise, it modifies the receiving binary number with the result of the addition.</li>

 <li>An operation clearOverflow() that clears the overflow flag.</li>

 <li>An operation String toString() for transforming a binary number to a String. If the number is the result of an overflow, the string “Overflow” should be returned.</li>

</ul>

<h2>2.3       Hints</h2>

<ul>

 <li>For the BinaryNumber(String str) constructor, the following operations might come in handy:

  <ul>

   <li>char lang.String.charAt(int index), which returns the char value at the specified index. An index ranges from 0 to length() – 1. The first char value of the sequence is at index 0, the next at index 1, and so on, as for array indexing.</li>

   <li>int lang.Character.getNumericValue(char ch), which returns the int value that the specified Unicode character represents.</li>

  </ul></li>

 <li>For the shiftR(int amount) operation, it might be useful to define an auxiliary private method reallocate, that makes room for a new digit. This operation would in turn use int[] java.util.Arrays.copyOf(int[] original, int newLength), which copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.</li>

</ul>


