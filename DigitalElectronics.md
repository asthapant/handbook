## Digital Electronics

## Content
- [Introduction](#digitalsystems)
  - [Number Systems](#number)
  - [K-Map](#kmap)
   - [Filling and solving the K-map](#fillsolve)
- [Combinational Circuit](https://github.com/asthapant/handbook/blob/master/Combinational.md)
- [Sequential Circuit](https://github.com/asthapant/handbook/edit/master/Sequential.md)

<a name="digitalsystems"></a>
  
# Digital Systems

Digital Systems are designed to store, process, and communicate information in digital form. They are found in a wide range of applications, including process control, communication systems, digital instruments, and consumer products.These systems store data in a discrete way.

The simplest form of digital system is binary, with exactly two distinct values for inputs and outputs. Binary digital sys-tems form the basis of just about all hardware systems in existence today.

### Advantages of Digital System

The critical advantage of digital systems is their inherent ability to deal with electrical signals that have been degraded by transmission through circuits. Because of the discrete nature of the outputs, a slight variation in an input is translated into one of the correct output values. In analog circuits, a slight error at the input generates an error at the output. If analog circuits are wired together in series, the output of one feeding the input of the next, each stage adds its own small error. The sum of the errors over several stages becomes overwhelming. Digital components are considerably more accurate and reliable.

<p align="center">
<img src="https://cdn.sparkfun.com/assets/c/8/5/b/e/51c495ebce395f1b5a000000.png">
</p> 

<a name="number"></a>

## Number Systems


In digital electronics, the number system is used for representing the information. The number system has different bases and the most common of them are the decimal, binary, octal, and hexadecimal. The base or radix of the number system is the total number of the digit used in the number system. Suppose if the number system representing the digit from 0 to 9 then the base of the system is the 10. Types of Number System:

- Decimal Number System : The number system is having digit 0, 1, 2, 3, 4, 5, 6, 7, 8, 9; this number system is known as a     decimal number system because total ten digits are involved.The base of the decimal number system is 10.

- Binary Number System : The modern computers do not process decimal number; they work with another number system known as a binary number system which uses only two digits 0 and1.The base of binary number system is 2 because it has only two digit 0 and 1.The digital electronic equipments are works on the binary number system and hence the decimal number system is converted into binary system.

- Octal Number System : The base of a number system is equal to the number of
digits used, i.e., for decimal number system the base is ten while for the binary
system the base is two. The octal system has the base of eight as it uses eight digits
0, 1, 2, 3, 4, 5, 6, 7.

- Hexadecimal Number System : These numbers are used extensively in micropro-
cessor work.The hexadecimal number system has a base of 16, and hence it con-
sists of the following sixteen number of digits.

  0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F.

  The size of the hexadecimal is much shorter than the binary number which makes
  them easy to write and remember.
  
<a name="kmap"></a>

# K-Map
The main use of K maps is to simplify or reduce our circuit or to reduce the POS or SOP expression that we have made using logic gates(the ones previously told) and with our input signals thus arriving at the most optimal logic design 

Some of the two variable(input), three variable(input) and four variable(input) K-Maps look like:

<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79644871-530d1f80-81c9-11ea-8620-bf6c27fe4c90.png" height="300" width="700">
 </p>
 
Here note the order of variables-

like for the first one the signal expression would be represented as f(A,B) means the one which is first comes down and the next one up.

Similarly for the 3 variable Karnaugh map which is f(Z,X,Y), the first one Z down and the next two X,Y up.Do guess for the fouth one:)

I'm pretty sure you are confused by the order of 0's & 1's written on the top of table and on the side of the table.For now, just learn them up, you will get to know the intuition behind it afterwards.

The use of them is to fill the decimal numbers in the bottom right corner of each block of the table just like as was shown:

<a name="fillsolve"></a>

### Filling and Solving the K-Map

you could be given a circuit as F(A,B,C)=∑(1,3,6,7). So now in all those squares whose number is given in the expression, fill them with 1's and the other with 0's. 

Now we need to make groups of all the 1's if it is a SOP expression and all the 0's if it is a POS expression, but in only groups of the powers of 2 i.e. in (1,2,4,8,16....) and try to make the largest group possible and they should be continuous.

You can make groups in horizontal, vertical and in sideways (making groups of the **extreme left** and the **extreme right** **or** the **top** and the **bottom**).

like for the above example:

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/uploads/K-Map-Karnaugh-Map.png" height="350" width="450">
</p> 

Here, was only the possibility of pairs and no quads as there were no four 1's in line **horizontally**, **vertically** or as a **2x2 rubik's cube**.

Also keep in mind that if all the 1's of a pair or a quad or an octat is used in the foramtion of any other pair,quad, or octat, the former pair, quad or octat becomes **redundant** or **there's no use of it**.

Just like here the pair shown in blue becomes redundant as both of its 1's are used in the formation of two other pairs.

**Congrats** the hard part is now over and now writing the logical expression is left which is pretty easy. Look at the groups that you have formed as only they play a part in expression. In the groups look at the value of the variables A,B,C(Ya, you guessed it right the ones written as the headings). 

Now, look for if value of that variable is changing like from 1 to 0 or from 0 to 1. If it is happening , then that variable will not be taken into the expression. Only those variables will be taken whose value do not change **remains 0 or remains1**.In case of a pair ,one will be lost; for a quad, 2 will be lost ; for an octat,3 will be lost.

For this one , the red pair:  A'.C (as the value of B changes and value of A remains 0, C remains 1).  Since it is a **SOP** expression the value of each variable must be 1 when writing the expression hence complement of A is taken and C as it is + the fact is **SOP** (hence sum of products).

Similarly the green pair will be: A.B (the value of C changes and A:1, B:1).

Hence the reduced expression : A'.C + A.B

#### 4 variable Karnaugh Map:

F(P,Q,R,S)=∑(0,2,5,7,8,10,13,15)

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/uploads/K-Map-Karnaugh-Map-2-1.png" height="350" width="450">
</p> 

Here the **sideways grouping** is applicable and hence a quad is formed.

Green quad: Q'.S'( as the value of P and R changes with respect to the four blocks and the value of Q and S is 0).

Red quad: Q.S

Final expression: Q'.S' + Q.S

##### One more example-

F(A,B,C,D):∑(0,1,2,4,5,6,8,9,10,12,13)

<p align="center">
<img src="https://www.electricaltechnology.org/wp-content/uploads/2018/04/4-variable-k-map-Example.png" height="280" width="280">
</p>

Try to this on your own.

Final expression: A' + C'.B' + D'.B'


## POS Expression

For the POS expression all the things are same as the SOP expression but instead of 1's, you have to make the groups of 0's and during wriing the expression make sure that every variable's value is 0 , instead of 1 and if not take the complement of that variable. 

### 4 variable POS expression:

F(A,B,C,D) = π(3,5,7,8,10,11,12,13)

<p align = "center">
<img src = "https://media.geeksforgeeks.org/wp-content/uploads/K-Map-Karnaugh-Map-3.png", width = "300" height = "300">
</p> 

green pair = C+D'+B'

red pair = C'+D'+A

blue pair = A'+C+D

brown pair = A'+B+C'

Final Expression : (C+D'+B').(C'+D'+A).(A'+C+D).(A'+B+C')
