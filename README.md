# E-club-handbook
Digital electronics part of E club handbook

# K-Map
The main use of K maps is to simplify or reduce our circuit or to reduce the POS or SOP expression that we have made using logic gates(the ones previously told) and with our input signals thus arriving at the most optimal logic design 

Some of the two variable(input), three variable(input) and four variable(input) K-Maps are:

<img src="https://www.dyclassroom.com/image/topic/boolean-algebra/k-map/05.png" width="350">           <img src="https://i.ytimg.com/vi/XO2oHLgR2Dg/hqdefault.jpg" height ="300"> 

<p align = "center">
<img src="https://3.bp.blogspot.com/-JkmyKT3baJ4/ULRmQq4tT3I/AAAAAAAAAI0/CwqzOYSaQ8c/s1600/4+var.kmap1.jpg" height = "300">
</p>

Here note the order of variables-

like for the first one the signal expression would be represented as f(A,B) means the one which is first comes down and the next one up.

Similarly for the 3 variable Karnaugh map which is f(Z,X,Y), the first one Z down and the next two X,Y up.Do guess for the fouth one:)

I'm pretty sure you are confused by the order of 0's & 1's written on the top of table and on the side of the table.For now, just learn them up, you will get to know the intuition behind it afterwards.

The use of them is to fill the decimal numbers in the bottom right corner of each block of the table just like as was shown:


### Filling and Solving the K-Map

you could be given a circuit as F(A,B,C)=∑(1,3,6,7). So now in all those squares whose number is given in the expression, fill them with 1's and the other with 0's. 

Now we need to make groups of all the 1's if it is a SOP expression and all the 0's if it is a POS expression, but in only groups of the powers of 2 i.e. in (1,2,4,8,16....) and try to make the largest group possible and they should be continuous.

You can make groups in horizontal, vertical and in sideways (making groups of the **extreme left** and the **extreme right** **or** the **top** and the **bottom**)

like for the above example:

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/uploads/K-Map-Karnaugh-Map.png">
</p> 

Here ,was only the possibility of pairs and no quads as there were no four 1's in line **horizontally**, **vertically** or as a **2x2 rubik's cube**.

Also keep in mind that if all the 1's of a pair or a quad or an octat is used in the foramtion of any other pair,quad, or octat, the former pair, quad or octat becomes **redundant** or **there's no use of it**.

Just like here the pair shown in blue becomes redundant as both of its 1's are used in the formation of two other pairs.

**Congrats** the hard part is now over and now writing the logical expression is left which is pretty easy. Look at the groups that you have formed as only they play a part in expression. In the groups look at the value of the variables A,B,C(Ya, you guessed it right the ones written as the headings). 

Now, look for if value of that variable is changing like from 1 to 0 or from 0 to 1. If it is happening , then that variable will not be taken into the expression. Only those variables will be taken whose value do not change **remains 0 or remains1**.In case of a pair ,one will be lost; for a quad, 2 will be lost ; for an octat,3 will be lost.

For this one , the red pair:  A'.C (as the value of B changes and value of A remains 0, C remains 1).  Since it is a **SOP** expression the value of each variable must be 1 when writing the expression hence complement of A is taken and C as it is + the fact is **SOP** (hence sum of products)

Similarly the green pair will be: A.B (the value of C changes and A:1,B:1)

Hence the reduced expression : A'.C + A.B

#### 4 variable karnaugh map

F(P,Q,R,S)=∑(0,2,5,7,8,10,13,15)

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/uploads/K-Map-Karnaugh-Map-2-1.png">
</p> 

Here the **sideways grouping** is applicable and hence a quad is formed

Green quad: Q'.S'( as the value of P and R changes with respect to the four blocks and the value of Q and S is 0)

Red quad: Q.S

Final expression: Q'.S' + Q.S

##### one more example

F(A,B,C,D):∑(0,1,2,4,5,6,8,9,10,12,13)

<p align="center">
<img src="https://www.electricaltechnology.org/wp-content/uploads/2018/04/4-variable-k-map-Example.png">
</p>

Try to this on your own

Final expression: A' + C'.B' + D'.B'


## POS Expression

For the POS expression all the things are same as the SOP expression but instead of 1's, you have to make the groups of 0's and during wriing the expression make sure that every variable's value is 0 , instead of 1 and if not take the complement of that variable. 

### 4 variable POS expression

F(A,B,C,D)=π(3,5,7,8,10,11,12,13)

<p align = "center">
<img src = "https://media.geeksforgeeks.org/wp-content/uploads/K-Map-Karnaugh-Map-3.png", width = "500" height = "400">
</p> 

green pair = C+D'+B'

red pair = C'+D'+A

blue pair = A'+C+D

brown pair = A'+B+C'

Final Expression : (C+D'+B').(C'+D'+A).(A'+C+D).(A'+B+C')



## Combinational Circuits

Combinational Circuit consists of input variables(i/p), logic gates and output variables(o/p). They are a type of **time independent circuits** whose output depends upon the present combination of input variables. In other terms, each output is a pure function of input variables.
The logic basically performs Boolean Algebra on inputs, where each output is expressed in terms of a combination of (say) n input variables or a Boolean function. 

The major steps for designing a combinational circuit include making a truth table defining the relationship followed by simplifying the expression using K-Map and hence making a logic diagram using Gates.The circuit does not use any memory or storage.

Some common examples include:

# Adder and Subtractor

## Half-Adder

 Half adder is a combinational arithmetic circuit which simply adds two single bit numbers and produces a sum bit (S) and carry bit (C) as the output. Is just a simple addition of binary numbers! 
 
 So, 0 + 0 = 0 (S) and 0 (C), 0 + 1 = 1 (S) and 0 (C), 1 + 0 = 1 (S) and 0 (C), 1 + 1 = 0 (S) and 1 (C). 
 
We thus make the truth table, assuming A and B as inputs and S and C as outputs.


| A | B | S | C |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 1 | 0 | 1 |

Now moving to the realization of the circuit, we first make the KMap:


<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79317814-c857c680-7f23-11ea-86d6-7271e9d3f0f1.jpg">
 </p>
 

So we see the simplified expressions and conclude that: 
- Sum bit (S) is the X-OR of A and B 
- Carry bit (C) is the AND of A and B.
We can easily make the circuit using one XOR gate and one AND gate. 

So, here it is:

<p align="center">
<img src="">
 </p>
 
 
## Full-Adder

Full Adder is an arithmetic circuit which adds three inputs and produces two outputs. The first two inputs are(say) A and B and the third input is an input carry(C-in). First, addition of inputs A and B is done followed by adding with input carry.
- For example: For inputs A, B ,C-in as 1,1,1; A+B gives Sum 0 and C-out 1. Then further addition with 1 gives final Sum 1 and carry(got initially) which was 1.

So, we make the truth table for all possible cases:


| A  | B  | C-in  | S  |  C-out |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

We need to make the Kmap now for both Sum(S) and carry(C-in):


<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79634239-d6f1e800-8186-11ea-82c4-7a55d96f4b1f.jpg">
 </p>
 
We can very well notice that:
- For Sum, output is the XOR of A,B and C-In, 
- For C-Out, output is the combined OR of AND of A-B, AND of B-CIN and AND of Cin-A. 
Thus, a Full Adder can be constructed using three AND, one OR gate and one XOR gate.

<p align="center">
<img src="">
 </p>
 

## Binary-Adder

A Binary Adder is a digital circuit which finds the the arithmetic sum of two binary numbers that is greater than one bit in length by operating on corresponding pairs of bits in parallel For example, sum of four bit numbers:(B<sub>3</sub>B<sub>2</sub>B<sub>1</sub>B<sub>0</sub>) and (A<sub>3</sub>A<sub>2</sub>A<sub>1</sub>A<sub>0</sub>) 

It consists of **full adders connected in a chain** where the output carry from each full adder is connected to the carry input of the next higher order full adder and so on.
For a four bit number, four full adders are needed to give an output of Sum(S<sub>3</sub>S<sub>2</sub>S<sub>1</sub>S<sub>0</sub>)and Carry-out(C<sub>4</sub>)

### Working

- The LSB of both the inputs(A<sub>0</sub> and B<sub>0</sub>) are given to the first full adder. The initial carry is taken as 0.
- The full adder then adds the three inputs accordingly and generates a sum output S<sub>0</sub>, and a carry output C<sub>1</sub>.
- This C<sub>1</sub> is now the carry input to the second full adder, with other inputs A<sub>1</sub> and B<sub>1</sub>.
- So this addition continues till we finally obtain S<sub>3</sub> to make the sum output S<sub>3</sub>S<sub>2</sub>S<sub>1</sub>S<sub>0</sub> and carry-out(C<sub>4</sub>).

Figure shows the circuit diagram:

<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79324616-7e73de00-7f2d-11ea-8537-8e02d8bd5216.gif">
</p>

One limitation of a Binary adder is Gate Delay, due to the generation of four Carry-outs and Sums. Thus all outputs will be valid only after four Gate Delays, also known as Carry Propogation problem.


## Half-Subtractor

Half-Subtractor is another combinational logic circuit designed to perform subtraction of two single bits numbers. It has two inputs ( say A and B) and produces two outputs (Difference and Borrow-output). Just a simple subtraction of binary numbers!

So, 0 - 0 = 0 (D) and 0 (b), 0 - 1 = 1 (D) and 1 (b), 1 - 0 = 1 (D) and 0 (b), 1 - 1 = 0 (D) and 0 (b). 

So, the truth table is:

| A | B | D | b |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |

Moving to the Kmap, it is fairly simple to make:

<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79634234-d1949d80-8186-11ea-96a4-91ed474f9f55.jpg">
</p>

Circuit Diagram:

<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79633888-eec86c80-8184-11ea-9a56-73eb11dd8252.png" height="330" width="400">
</p>


## Full-Subtractor

Full-Adder is designed to perform subtraction of three single bits. It is given three inputs(say A, B, B-in) and produces two outputs (D, B-out). Here, A and B are called **Minuend** and **Subtrahend** bits. And, Bin is Borrow-In and Bout is Borrow-Out.

We thus make the truth table, after performing binary subtractions of three inputs:

| A | B | B-in | D | B-out |
|---|---|------|---|-------|
| 0 | 0 |   0  | 0 | 0     |
| 0 | 0 |   1  | 1 |   1   |
| 0 | 1 |   0  | 1 | 1     |
| 0 | 1 |   1  | 0 | 1     |
| 1 | 0 |   0  | 1 |   0   |
| 1 | 0 |   1  | 0 | 0     |
| 1 | 1 |   0  | 0 |   0   |
| 1 | 1 |   1  | 1 | 1     |

Moving forward to making the Kmap and getting the simplified expressions:

<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79634230-cf324380-8186-11ea-89cf-e3ffd8c6cc49.jpg">
</p>

First expression can be more simplified and written as D = ( A xor B xor B-in ). 

Now the circuit diagram can be easily made by
- Using XOR gate for getting Difference(D).
- Using NOT gate, followed by AND gate and finally an OR gate to obtain B-out.

<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79633894-f38d2080-8184-11ea-9e2d-3bf420242601.png" height="350" width="450">
</p>
 

## Binary-Subtractor

Binary Subtractor is a logic circuit that subtracts two binary numbers from each other. It is similar to adding two binary numbers, with the number to be subtracted expressed in 2's complement form. Reminder!(2's complement involves inverting all the bits and adding 1 to the Least Significant Bit(LSB)).

 <p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79327186-a06f5f80-7f31-11ea-94de-a3e5c4a93cd0.jpg">
 </p>


## Binary Adder/Subtractor

Binary Adder-Subtractor does both addition and subtraction of binary numbers in one circuit itself. The circuit consists of 4 full adders for operations on 4-bit numbers. 
There is a control signal(say K) that holds a binary value of either 0(adder) or 1(subtactor) which determines that the operation being carried out is addition or subtraction.

One of the binary numbers(say B) is the input on the XOR gate along with the control signal.(Such that:1+B=B', 0+B=B) For Adder, the resultant expression becomes {A+B+Cin}as B+K=B since K is equal to 0. For Subtractor. the resultant expression is {A+(1's complement if B)+Cin} as B+K=B' since Kis equal to 1.

<p align="center">
<img src="">
 </p>



## Decoder

A binary code of n bits is capable of representing 2^n coded information which is pretty huge.In terms of numbers a n bit code can represent numbers from -(2^n - 1) to 2^n - 1.

Decoder is a **combinational** circuit that converts binary information from **n input lines** to **2^n output lines**.
It represents the basic calculation of decimal number system from binary number system as mentioned before.

If a binary decoder receives n inputs it activates one and only one of its 2^n outputs based on that input with all other outputs deactivated.

A 3x8 binary decoder looks like this:

<img src="https://www.elprocus.com/wp-content/uploads/3-to-8-Decoder-circuit.jpg" width="400" height="400"> **OR** <img src ="https://www.elprocus.com/wp-content/uploads/decoder-block-diagram.jpg" width = "400" height = "400">

The intuition behind it is that the inputs can be supposed to be diiferent input switches and the output lines could be different LED's, so when a combination of input is given through the switches, only the LED with that combination glows and all the other LED's do not glow.

The truth table is as follows:

<p align ="center">
<img src = "https://www.electrical4u.com/images/february16/1460009218.PNG">
</p> 

When enable pin is 0 the circuit is not started and when it is 1, the circuit works in the original way.

Similarly there are 2x4 and 4x16 decoders also.



## Encoder

An encoder performs opposite operation to that of a decoder.It has 2^n or fewer input lines and n output lines.
Output lines generate binary code corresponding to the input values.

Only one input line should be high and corresponding to that a combination of output lines light up or are generated and the other remain low.

for example an octal to binary encoder:  has eight input lines(Y0-Y7) and three output lines(A0-A2)

<p align = "center">
<img src = "https://www.tutorialspoint.com/digital_circuits/images/octal_to_binary_encoder_circuit_diagram.jpg" height="400">
</p>

The truth table for it is as follows:

![](https://circuitdigest.com/sites/default/files/inlineimages/u/8-to-3-Encoder-Tuth-Table.png)

Since, A0 = Y1 + Y3 + Y5 + Y7    ,   A1 = Y2 + Y3 + Y6 + Y7   ,  A2 = Y4 + Y5 + Y6 + Y7

However ther's one **Anomally** with an encoder which is if all the ouptut lines are 0 , it could be if all the inputs are 0 or the least significant input is 0.



## Sequential Circuits

Sequential circuits are circuits in which the present output depend on the present input as well as the past output/outputs.
Basically, there's a memory element which stores the output and provides that as a feedback or another set of input to its own circuit to generate a new output.The basic difference between the sequential and combinational circuits are these memory blocks.

<p align ="center">
<img src="https://www.tutorialspoint.com/digital_circuits/images/sequential_circuit.jpg"/>)
</p>  

You can think of it as a counter which counts from 0 to 9 by adding 1 bit each time. So it adds 0+1=1, 1+1=2, 2+1=3...... and so it should know what the previous digit was or on what to add 1.Thus a memory element stores what the previous digit was.

These memory elements which are capable of storing one bit of information are known as **flip flops**.

Before coming to the flip flops, let's know about **latches** which are the most basic and primitive form of flip flops and used as memory elements.
Certain types of latches are:

  **SR Latch**
  
It is the Set Reset Latch and there are two forms of it using the NOR gate and the NAND gate.  

1. **NOR Latch**

<p align ="center">
<img src = "https://sub.allaboutcircuits.com/images/04173.png">
</p>  

  Two cross coupled NOR gates
  
  R:Reset ,S:Set , Q and Q' : Complementary outputs
  
* Q = 1 and Q' = 0 : Set state of the Latch

* Q = 0 and Q' = 1 : Reset state of the Latch

  Recall for NOR gates: any input if 1 will make the output 0 , output will be 1 only if all inputs are 0
  
Now let's look at the different cases:

Now make S = 1 ( keeping R = 0 )
=> Immediately Q' = 0 , and it is fed back to NOR1, which already has one of its input (R) = 0

=> Q = 1 (and Q' = 0 )
=> Set state of the latch

Now if we remove the inputs it should retain the output as it is working as a memory element. Thus making S=0 & R=0 and Q' = 0 will lead to Q remaining as 1 

When Q fed to second NOR it would let Q'=0 thus serving as memory storage.

Now make R = 1 ( keeping S = 0 ) immediately Q = 0 , and it is fed back to NOR2, which already has one of its i/p (S) = 0

=> Q' = 1 (and Q = 0 )

=>**Reset** state of the latch

Thus when now, R = 0 & S = 0, this would make no difference to the output. Hence **memory action**.

When S = 1 and R = 1 both Q = 0 and Q' = 0 irrespective of the previous inputs.

Thus now when S = 0 and R = 0 in memory state since both Q and Q' are 0, it would lead to making either Q or Q' equal to 1 whichever input reached faster the other NOR gate. Thus the purpose of storing the output is not served.

For NOR Latch, S= 1 & R = 1 condition is **Not Allowed**.

The truth table of NOR Latch is:

<p align ="center">
<img src = "https://electronicspost.com/wp-content/uploads/2015/05/24.png">
</p>

2. **NAND Latch**

Circuit Diagram:


<p align ="center">
<img src = "https://cdn.sparkfun.com/assets/learn_tutorials/2/1/6/34-sr-latch-nand.png" height="200" width="300">
</p>

* Two cross - coupled NAND gates

* Note the difference with NOR

Latch : Here, S drives the Q output and R drives the Q' output

=>Exactly opposite to that of NOR Latch

Recall : For NAND gates : Any (or both) input 0 will make the output 1 , for output to be 0, both inputs must be 1

Now, if S is made 0 ( with R at 1 ), Q becomes 1 , fed back to NAND2, and with R and Q both 1, Q' = 0 .The latch is now **Set**  

If now S is reverted to 1 with R = 1 , no change in the outputs (**memory action**)

Now if S = 1 and R = 0 , Q' becomes 1 , fed back to NAND1, and with S and Q' both 1, Q =0 .The latch is now **Reset**.

If now R is reverted to 1 and S = 1 , there's no change in the outputs (**memory action**)

Now if we make S = 0 , R = 0 , both Q and Q' become 1.    **The same inconsistency as the NOR latch**.

**Hence this combinaion is not allowed**

The truth table of NAND Latch is:

<p align ="center">
<img src = "https://www.electronicshub.org/wp-content/uploads/2013/12/4.jpg">
</p>

## Flip Flops

The basic difference between a latch and a flip flop is that laches are level triggered while flip flops are edge triggered.
There is a clock pulse attached with the flip flop and the flip flop works on the rising and falling edge of the clock.

<p align ="center">
<img src ="https://cs.nyu.edu/courses/fall01/V22.0436-001/lectures/figs/clock.png">
</p>

A clock is necessary because otherwise the inputs can change on their own and the storage of the previous output would not be made of much use.

Having understood the latches, flip flops are really easy to understand. Let's first go with the SR flip flop.

### SR Flip Flop

<p align ="center">
<img src = "https://www.gatevidyalay.com/wp-content/uploads/2018/06/Logic-Circuit-For-SR-Flip-Flop-Constructed-Using-NAND-Latch.png" height="400" width="400">
</p>

If the clock pulse is 0 above then the next part of the flip flop which is simply a NAND SR Latch corresponds to the memory state as both inputs would be 1 to the latch.

If the clock pulse is 1 then S correspnds to (S.clk(1))' = S' and R = R' and the truth table is:

| Clk | S | R |    Q   |   Q'   |                                                
|:---:|---|---|:------:|:------:|
|     |   |   |        |        |
|  0  | x | x | Memory | Memory |
|  1  | 0 | 0 | Memory | Memory |           
|  1  | 0 | 1 |    0   |    1   |            
|  1  | 1 | 0 |    1   |    0   |
|  1  | 1 | 1 |    -   |    -   |

**OR**

| Clk | S | R | Q(n+1) |
|:---:|:-:|:-:|:------:|
|  0  | x | x |  Q(n)  |
|  1  | 0 | 0 |  Q(n)  |
|  1  | 0 | 1 |    0   |
|  1  | 1 | 0 |    1   |
|  1  | 1 | 1 |    -   |

Here if S = 0 and R = 0 it would provide the SR latch with 1 and 1 hence the memory state.Similarly for others. If we look at the last case it would provide the SR Latch with 0 and 0 hence the forbidden condition which is an anomaly of the SR flip flop and this leads to the JK Flip Flop.

The characteristic table is:

| Q(n) | S | R | Q(n+1) |
|:----:|:-:|:-:|:------:|
|   0  | 0 | 0 |    0   |
|   0  | 0 | 1 |    0   |
|   0  | 1 | 0 |    1   |
|   0  | 1 | 1 |    -   |
|   1  | 0 | 0 |    1   |
|   1  | 0 | 1 |    0   |                
|   1  | 1 | 0 |    1   |
|   1  | 1 | 1 |    -   |

You don't need to memorize this , just by looking at the truth table you can make the characteristic table by looking at the values of S,R,Q(n) to find the value of Q(n+1) like for S = 0, R = 0, Q(n) = 0 => Q(n+1) = Q(n) = 0.

There is also one excitation table in which we have the outputs(Q(n) & Q(n+1)) with us and we need to compute the inputs (S,R) with it.

| Q(n) | Q(n+1) | S | R |
|:----:|:------:|:-:|:-:|
|   0  |    0   | 0 | x |
|   0  |    1   | 1 | 0 |
|   1  |    0   | 0 | 1 |
|   1  |    1   | x | 0 |             **x = don't care (can be 0 or 1)**


## J K Flip Flop:

Due to the shortcoming of the SR flip flop, JK flip flop in which for every set of input there is an output. It is completely similar to the SR flip flop just having an output value for the forbidden states also.

<p align = "center">
<img src = "https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/01/JK_flip.png" width="500" height="500">
</p>

The truth table shown above have just the order of inputs different. You can easily understand it by referring below.

#### Working:

The outputs Q and Q' are fed back as inputs which make the difference. Now when clk=J=K=1 and let's say Q =0 and Q'=1. Now when Q is fed to the NAND2 it would result 1, and when Q' is fed to NAND1 it would result 0. Thus comparing with the part2 which is the NAND latch it would result Q=1 and Q'=0.

Now when it is again given as feedback, this would result 1 from NAND1 and 0 from NAND2 thus changing the outputs Q=0 and Q'=1. So it feels as if it results in Q(n)' on every run.

| Clk | S | R | Q(n+1) |
|:---:|:-:|:-:|:------:|
|  0  | x | x |  Q(n)  |
|  1  | 0 | 0 |  Q(n)  |
|  1  | 0 | 1 |    0   |
|  1  | 1 | 0 |    1   |
|  1  | 1 | 1 |  Q(n)'   |     ----> This Q(n)' is known as **Toggling**  


#### The Race Around Problem

If J=K=1, and if clk=1 for a long period of time, then Q output will toggle as long as CLK is high, which makes the output of the flip-flop unstable or uncertain. This problem is called race around condition in J-K flip-flop.

<p align="center">
<img src = "https://3.bp.blogspot.com/-0hCoTTkoe58/UvOL-5QLo_I/AAAAAAAAANE/M1o4vVKoHhE/s1600/untitled.png" height="200" width="400">
</p>

This problem (Race Around Condition) can be avoided by ensuring that the clock input is at logic “1” only for a very short time. This introduced the concept of **Master Slave JK flip flop**.

#### Master Slave Condition

<p align="center">
<img src = "https://media.geeksforgeeks.org/wp-content/uploads/flipflop-1.jpg" height="300">
</p>

The two blocks refer to the actual structure of the J K filp flop. In the master-slave condition another JK flip flop is added and the ouput of the second flip flop is feedbacked as input to the first flip flop + the same clock is attached with a NOT gate.

The problem of race around arises when clk=J=K=1 , so let's discuss that case.First see this:

<p align="center">
<img src ="https://media.geeksforgeeks.org/wp-content/uploads/flipflop-diag-1.jpg" height="400" width="550">
</p>  

When the clock starts , master FF functions and the slave FF acts as a memory state as the clock signal is zero due to NOT gate. Now when J=1 and K=1 and on the rising edge of the clock , the Q signal becomes high of master FF and it would remain high till the second rising edge. 

On the falling edge of the clock the slave FF becomes active and the master FF acts as a memory state, thus it would remain high as said above.Now output of first FF is fed to slave FF which produces the same output as master FF thus it remains high till the second falling edge.

That output is fed back to master FF and on the second rising edge(means slave FF acts as memory state now), toggling takes place and thus the sginal Q(m) becomes low. Now, at the second falling edge, again the input is given to slave FF and toggling takes place and the process repeats itself.

**This makes the Master-Slave J-K flip flop a Synchronous device as it only passes data with the timing of the clock signal**


### D Flip Flop

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/01/D-logic-diag-300x123.png" height="200">
</p>  

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/01/D-flip-flop.png" width="200" height="200">
</p>


### T Flip Flop

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/01/T-logic-diag-300x143.png" height="200" width="300">
</p>  

<p align="center">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2017/01/T-flip-flop-300x127.png" height="200" width="300">
</p>  



## Registers

Till now we know that Flip Flops are a part of sequential circuits and can be used to store a single bit of binary data (1 or 0).
However, in order to store multiple bits of data, we need multiple flip flops. 

A **Register** is a device which is used to store such information. It is a **group of flip flops** connected in series and used to store multiple bits of data. The N-bit register consists of N number of Flip Flops and thus stores a N-bit number.

There are two types of registers: **parallel** and **serial** registers. They differ in the manner in which the binary data is loaded and retrieved from them. 

- For serial form, one bit is input at a time(SI) and so we even receive a serial output(SO). 
- For parallel form, data is entered individually to all the F/Fs(PI) and received as parallel outputs(PO).

<p align="center">
<image src="https://user-images.githubusercontent.com/58358546/79612383-3665de80-811a-11ea-9726-116f8fafc49e.png" width="550" height ="400">
</p>

For a 4-bit register, we thus use 4 Flip-Flops. Since we just want data to be stored without toggling, we will use a D Flip-Flop. A clock is internally connected to all the four F/Fs to govern the operation. So, we are bound to follow the clock.

#### But this poses a problem!

Whatever input we give to the F/Fs gets changed after one time period of the clock. Here, for **negative trigerred** flip flops, value changes on reaching from one falling edge to another. Thus, for the next clock pulse, we will have different combination of bits stored.

- Thereby, we use an independently controlled **Load**.

When we want register inputs to remain unchanged (even with clock changes), we can use a load control input. The load input determines whether the next pulse will accept new information or leave the information in the register intact. 

The Load input, when set at logic level 1 (high state), sets the four flip-flop data inputs to the register's four input bits. That is, we load the data into the register. 
When Load is at logic level 0 (low state), the four flip-flops have their outputs fed into their inputs. That is, the value stored doesn't change.

- There is also an additional direct reset input named **CLEAR or RESET**. When CLEAR is 0 the flip flop is resetting,independent of clock and D values. It is useful because in digital systems when the power is turned on the state of flip-flops is unknown. Direct input CLEAR can bring all flip-flops to the known starting state prior to the clock operation.

There are two types of Registers based on application, namely:
 - **Shift Register**
 - **Storage Register**
 
For simplicity, we will elaborate only Shift Registers. 


## Shift Register

A Shift register shifts its binary information in one or other direction. For example: by connecting the output of each D flip-flop to the input of another D flip flop in its right, each clock pulse shifts the content of the register, one bit position to the right.

The shift register, which allows serial input (one bit after the other through a single data line) and produces a serial output is known as **Serial-In Serial-Out (SISO)**.

For a Right shift register, the serial input determines what goes into the leftmost flip flop during the shift. The serial output is taken from the output of the rightmost flip flop.

The logic circuit given below shows a serial-in serial-out shift register. The circuit consists of four D flip-flops which are connected in a serial manner. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip flop.

So, it look like this:


<p align="center">
<img src="https://user-images.githubusercontent.com/58358546/79611910-3fa27b80-8119-11ea-90c4-d96d5dd06b32.png" width="750" height="250">
</p>


### Working

How does a shift register work? The working is simple.
- Lets assume that all the flip-flops (1 to 4) have just been RESET (CLEAR input) and that all the outputs Q<sub>0</sub> to Q<sub>3</sub> are at logic level 0. The input we want to store is 1111.
- If a logic 1 is connected to the serial input pin of first flip flop, then on the first clock pulse the output of first D flip flop,
and therefore the resulting Q<sub>3</sub> will be set HIGH to logic 1, with all the other outputs still remaining LOW at logic 0.
- Now, we give the next input 1. With D2 connected to Q3, D2 becomes 1 and so does Q2. So, now the resulting ouputs become 1100.
- In the similar way Q1 also becomes 1 and so does Q0 in the last step.
- Hence our stored data becomes 1111.

So, we draw the Table for the given data:

| Clock Pulse | Q<sub>3</sub>| Q<sub>2</sub>| Q<sub>1</sub>|  Q<sub>0</sub>|
|-------------|----|----|----|----|
| Initial     | 0  | 0  | 0  | 0  |
| First       | 1  | 0  | 0  | 0  |
| Second      | 1  | 1  | 0  | 0  |
| Third       | 1  | 1  | 1  | 0  |
| Fourth      | 1  | 1  | 1  | 1  |

Timing Diagram

<p align="center">
<image src="https://user-images.githubusercontent.com/58358546/79615120-9e6af380-811f-11ea-97dc-bcb72c5bcd70.jpg" width="500" height ="400">
</p>


## Counters


Counter is apparently the widest application of flip-flops. As the name suggests, they are used in digital electronics for counting purpose, that is, they can count specific event happening in the circuit, often in relationship to a clock signal. In layman terms, **counter counts the pulses**.

### Different types of Counters:

**UP counters** count upwards or incrementally. It increases count for every rising/falling edge of clock depending upon positive/negative edge triggering of the flip flops.

**Down counters** on the other hand, count downwards or in a decremental manner. 

Now an interesting point to be noted is that not only counting, a counter can follow a certain sequence based on our design, like any random sequence 0,1,3,2... !

Moving to the circuit design, counters are groups of flip-flops and as we know, flip-flops have a clock input, so depending on the type of clock input, counters are classified as:

 - **Asynchronous or ripple counters**
 - **Synchronous counters**
 
 Before moving forward, there are two major points to be considered:
 
 - A counter following binary number sequence is called Binary Counter. We'll be using this term hereby.
 - An n bit binary counter consists of n flip-flops and can count in binary from 0 to (2<sup>n</sup> – 1).
 
## Binary Ripple/ Asynchronous Counters


In an asynchronous counter we don’t use universal clock, only first flip flop is driven by main clock and the output of the first flip flop is the clock input of the second flip flop and so on. Since it is an UP Counter, it counts from a lower to higher value. 

They are of following types:
- N-bit asynchronous UP counter
- N-bit asynchronous DOWN counter
- N-bit asynchronous UP/DOWN counter

For simplicity and understanding, we will study **4-bit asynchronous UP counter** in detail:

### Design

For a 4-Bit Binary Asynchronous Counter, we use 4 JK flip flops(can also use T flip flops as when J=K=1), and it can count from 0 to (2<sup>4</sup>-1), 0 to 15. 

The output Q<sub>0</sub> of the first F/F is given as input clock to second F/F and output Q<sub>1</sub> of second is acting as clock for third F/F and so on.

<p align="center">
 <img src="https://user-images.githubusercontent.com/58358546/79570442-14973800-80d7-11ea-9fe1-108c9cc7e939.png" height="230" width="800">
 </p>



However, for a slight change, it uses 4 bits to count decimal numbers from 0 to 9 (0000 to 1001) and then goes back to 0. The rest of the numbers (10 to 15 (1010 to 1111) are DON'T CARE (X) in K map, and do not appear in Counters. 

A 4-bit asynchronous counter thus represents **10 states**.

**How does it work ?**

Since this is a 4-bit counter, we need to consider 16 stated of the clock. The flip flops are negative edge triggered, so we consider falling edges for the change in the timing diagram. 

Starting from output of the first F/F (Q<sub>0</sub>), initially it is 0 and it remains 0 till the first falling edge, then it is complemented due to toggling and remains high till the next falling edge, then again low and so on.

For output of the second F/F (Q<sub>0</sub>), Q<sub>0</sub> acts as a clock, and so we chnage state from low to high noticing the falling edge of Q<sub>0</sub>.

Following the process, we similarly draw diagrams for Q<sub>2</sub>and Q<sub>3</sub>.

<p align="center">
 <
 <img src="https://user-images.githubusercontent.com/58358546/79570458-1b25af80-80d7-11ea-9f6f-0ebb26c5e380.png" height="380" width="600">
 
 </p>


For the truth-table, Q<sub>0</sub> is the LSB and Q<sub>3</sub> is the MSB. Thus, we notice the states of all four outputs for 16 states and plot the table:


|Clock Pulse   |  Q<sub>3</sub> | Q<sub>2</sub>  | Q<sub>1</sub>  | Q<sub>0</sub>  |
|---|---|---|---|---|
|  0|  0|  0 | 0  | 0  |
|  1|  0|  0 | 0  |  1 |
|  2|  0|  0 | 1  |  0 |
|  3|  0|  0 |  1 |  1 |
|  4|  0 | 1  |  0 |  0 |
|  5|  0 |  1 |  0 |  1 |
|  6|  0 |  1 |  1 |  0 |
|  7|  0 |  1 |  1 |  1 |
|  8|  1 |  0 |  0 |  0 |
|  9|  1 |  0 |  0 |  1 |
| 10|  1 |  0 |  1 |  0 |
|  11|  1|  0 | 1  |  1 |
|  12|  1|  1 | 0  |  0 |
|  13|  1|  1 |  0 |  1 |
|  14|  1 | 1  |  1 |  0 |
|  15|  1 |  1 |  1 |  1|

## 4- bit asynchronous DOWN counter

As a simple modification of the UP counter. 4 bit DOWN counter will count numbers from 15 to 0, downwards. The output of the first flip flop will change, when the negative falling edge of clock signal occurs. Here every clock pulse at the input will reduce the count of the individual flip flop. So the down counter counts from 15, 14, 13...0 i.e.(1111 to 0000).

The block diagram of 4-bit Asynchronous binary down counter is similar to the block diagram of 4-bit Asynchronous binary up counter. But, the only difference is that instead of connecting the normal outputs of one stage flip-flop as clock signal for next stage flip-flop, connect the complemented outputs of one stage flip-flop as clock signal for next stage flip-flop. 


## BCD Ripple Counter/ Decade Counter

A Decade Counter is a serial digital counter which goes through 10 unique combinations of outputs and then resets as the clock proceeds. 
It uses 4 bits to count in **binary coded decimal** numbers from 0 to 9 (0000 to 1001) and then goes back to 0. The rest of the numbers from 10 to 15 (1010 to 1111) are DON'T CARE (X) in K map, and do not appear in BCD Counters.

The circuit is essentially, a ripple counter which counts up to 16. We desire however, a circuit operation in which the count advance from 0 to 9 and then reset to 0 for a new cycle. This reset is a accomplished at the desired count as follows:

- With counter REST count = 0000 the counter is ready to stage counter cycle.
- The counter then starts counting from 0 till it reaches 1001(decimal 9).
- The next count pulse advance the count to 10 count = 1010. Now, we have to reset our flip flops! 
- For this, we use 2 asynchronous inputs: **Preset (PR)** and **Clear (CLR)**. As we know, when CLR=0; Output=0(**RESET**) and when PST=0; Output=1(**SET**). But here we need RESET action, hence Preset is connected to Logic 1, so it has no effect on flip flops.
- To make CLR=0, a logic NAND gate decodes the count of 10 providing a level change at that time which then resets all counter stages.

Thus, the pulse after the counter is at count = 9, effectively results in the counter going to count = 0.

<p align="center">
 <img src="https://user-images.githubusercontent.com/58358546/79584399-f556d580-80eb-11ea-835b-9f70f0b9e6cc.jpg"
 width="630" height="360">
 </p>
 
 
 Truth Table of a BCD ripple Counter is:
 
 
|Clock Pulse   |  Q<sub>3</sub> | Q<sub>2</sub>  | Q<sub>1</sub>  | Q<sub>0</sub>  |
|---|---|---|---|---|
|  0|  0|  0 | 0  | 0  |
|  1|  0|  0 | 0  |  1 |
|  2|  0|  0 | 1  |  0 |
|  3|  0|  0 |  1 |  1 |
|  4|  0 | 1  |  0 |  0 |
|  5|  0 |  1 |  0 |  1 |
|  6|  0 |  1 |  1 |  0 |
|  7|  0 |  1 |  1 |  1 |
|  8|  1 |  0 |  0 |  0 |
|  9|  1 |  0 |  0 |  1 |
| 10|  0 |  0 |  0 |  0 |


## State Diagram of a Counter

### For a 3-bit Up Counter

A 3-bit flip flop starts from 000(decimal 0) to its maximum count (2<sup>3</sup>-1) which is equal to 111(decimal 7). 

The states are namely the counts of our counter and depicting them pictorially is a State diagram. We know that a counter changes states with every passing clock pulse, this change is indicated by arrows.

Following is the state diagram of a simple 3-bit Up counter:

<p align="center">
 <img src="https://user-images.githubusercontent.com/58358546/79588578-c3487200-80f1-11ea-9299-0d9613e98b9e.png"
width="500" height="300">
 </p>

Similarly, following is the state diagram of a BCD up Counter:

<p align="center">
 <img src="https://user-images.githubusercontent.com/58358546/79588588-c5aacc00-80f1-11ea-9929-1563dbd60a34.png"
 width="500" height="300">
 </p>


## Synchronous Counters


If the clock pulses are applied to all the flip-flops in a counter simultaneously, then such a counter is called as synchronous counter.
The one advantage of synchronous counter over asynchronous counter is that it can operate on a higher frequency than asynchronous counter as it does not have delay because of same clock given to each flip flop.

### Steps to design a Synchronous Counter

- Decide the number of Flip Flops.
- Draw the Excitation Table of the flip flop.
- Draw the state diagram of the counter and circuit excitation table.
- Obtain simplified equation using K-Map.
- Draw the logic diagram.

Here, lets complete these steps and design a 3-bit synchronous counter using JK flip flop.

### Excitation table for JK flip flop

We very well know how to make an excitation table for a JK flip flop.

| Q | Q* | J | K |
|---|----|---|---|                              
| 0 | 0  | 0 |  X |                                      
| 0 | 1  | 1 |  X |
| 1 | 0  |  X | 1 |
| 1 | 1  |  X | 0 |   

We've already seen the state dagram for 3-bit counter, so that step can be skipped.

### Circuit Excitation table

For 3-bit, there are 8 states(0 to 7). The present states will be indicated by Q<sub>2</sub>, Q<sub>1</sub>. Q<sub>0</sub> while the next state will be shown as Q<sub>2</sub>*, Q<sub>1</sub>*, Q<sub>0</sub>*.

It is very simple to write the next state of a counter using state diagram. The present state starts at 000 and the next state ends at 000.

To find the inputs of JK flip flop, we refer to the excitation table, notice the present and the next state and thus the generated input.

So, our circuit excitation table looks like this:


|    |    |    |    |    |    |    |    |    |    |    |    |
|----|----|----|----|----|----|----|----|----|----|----|----|
| Q<sub>2</sub> | Q<sub>1</sub> | Q<sub>0</sub> | Q<sub>2</sub>* | Q<sub>1</sub>* | Q<sub>0</sub>* | J<sub>2</sub> | K<sub><sub>2</sub> | J<sub>1</sub>| K<sub>1</sub> | J<sub>0</sub>| K<sub>0</sub> |
| 0  | 0  | 0  | 0  | 0  | 1  | 0  | X  | 0  | X  | 1  | X  |
| 0  | 0  | 1  | 0  | 1  | 0  | 0  | X  | 1  | X  | X  | 1  |
| 0  | 1  | 0  | 0  | 1  | 1  | 0  | X  | X  | 0  | 1  | X  |
| 0  | 1  | 1  | 1  | 0  | 0  | 1  | X  | X  | 1  | X  | 1  |
| 1  | 0  | 0  | 1  | 0  | 1  | X  | 0  | 0  | X  | 1  | X  |
| 1  | 0  | 1  | 1  | 1  | 0  | X  | 0  | 1  | X  | X  | 1  |
| 1  | 1  | 0  | 1  | 1  | 1  | X  | 0  | X  | 0  | 1  | X  |
| 1  | 1  | 1  | 0  | 0  | 0  | X  | 1  | X  | 1  | X  | 1  |
 
 
 ### K Map
 
 Now, we need to make K map for the same. For total 6 JK inputs, we need to make 6 eight cells K maps, one for each input. We know that the DON'T CARE value(X) can be grouped with 1, so making possible groups and writing the expressions that follow, we obtain:
 
 
 <p align="center">
 <img src="https://user-images.githubusercontent.com/58358546/79607318-a4a5a380-8110-11ea-9657-f1980bc69642.png"
      height="400" width="670">
 </p>
 
 
 ### Logic Diagram
 
 Having made the Kmap, we can easily design the logic diagram now.
  - J<sub>0</sub> and K<sub>0</sub> are 1, so we connect them to logic value 1.
  - J<sub>1</sub> and K<sub>1</sub> are equal to Q<sub>0</sub>, so output of first flip flop is input to second.
  - J<sub>2</sub> and K<sub>2</sub> are aquired through the AND of Q<sub>0</sub> and Q<sub>1</sub>.
  
  **Thus, our logic diagram is ready !**
  
  
 <p align="center">
 <img src="https://user-images.githubusercontent.com/58358546/79606909-f13caf00-810f-11ea-9133-1842015c8d8c.jpg">
 </p>
 
 
## Modulo-m counters

- 2-bit up/down ripple counter is MOD-4 or modulus 4 counter.
- 3-bit up/down ripple counter is MOD-8 or modulus 8 counter.
MOD number is equal to the number of bits,(2<sub>n</sub>).

Now, an important point to be discussed here is, making a counter count to a particular value. A Modulo-m counter can also be
made a Modulo-p counter, with p < m. Example: A Modulo-8 counter can be made to count only from 0 to 5, and thus, it becomesa Modulo-6 counter.

This is done using PRESET and CLR input, and with the use of NAND gate. We've already discussed something similar in a decade counter.


 
 
 

 
 













