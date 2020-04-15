## Combinational Circuits
Combinational Circuit consists of input variables(i/p), logic gates and output variables(o/p). They are a type of time independent circuits whose output depends upon the present combination of input variables. In other terms, each output is a pure function of input variables. The logic basically performs Boolean Algebra on inputs, where each output is expressed in terms of a combination of (say) n input variables or a Boolean function. The major steps for designing a combinational circuit include making a truth table defining the relationship followed by simplifying the expression using K-Map and hence making a logic diagram using Gates.The circuit does not use any memory or storage.
Some common examples include:
## Adder
 - **Half-Adder**
Half adder is a combinational arithmetic circuit designed to add two single bit numbers and produce a sum bit (S) and carry bit (C) as the output. Thus, 0 + 0 = 0 (S) and 0 (C), 0 + 1 = 1 (S) and 0 (C), 1 + 0 = 1 (S) and 0 (C), 1 + 1 = 0 (S) and 1 (C).  
Below is the truth table, schematic representation and realization of a half adder-

![halfAdder](https://user-images.githubusercontent.com/58358546/79316553-17046100-7f22-11ea-9708-38b22427255b.png)

Following is the K-Map for Half Adder:

![KMAP](https://user-images.githubusercontent.com/58358546/79317814-c857c680-7f23-11ea-86d6-7271e9d3f0f1.jpg)
From this it is clear that a half adder circuit can be easily constructed using one X-OR gate and one AND gate. If A and B are the input bits, then sum bit (S) is the X-OR of A and B and the carry bit (C) will be the AND of A and B.
- **Full-Adder**
Full Adder is an arithmetic circuit which adds three inputs and produces two outputs. The first two inputs are(say) A and B and the third input is an input carry(C-In). First, addition of inputs A and B is done followed by adding with input carry.

Truth Table for Full Adder-

![Full-Adder-truth-table](https://user-images.githubusercontent.com/58358546/79321172-9432d480-7f28-11ea-89b9-7d0e319e3df5.png)

Realisation of Circuit using AND and XOR gate-

![fulladder](https://user-images.githubusercontent.com/58358546/79320541-99dbea80-7f27-11ea-8a5f-8999b122127d.gif)

For Sum, output is the XOR of A,B and C-In, For C-Out, output is the combined OR of AND of A-B, AND of B-CIN and AND of Cin-A. A Full Adder can be constructed using two Half Adders and an OR gate.
- **Binary-Adder**
A Binary Adder is a digital circuit capable of finding the arithmetic sum of two binary numbers(B<sub>3</sub>B<sub>2</sub>B<sub>1</sub>B<sub>0</sub>) and (A<sub>3</sub>A<sub>2</sub>A<sub>1</sub>A<sub>0</sub>) that is greater than one bit(here,4) in length by operating on corresponding pairs of bits in parallel. It consists of full adders connected in a chain where the output carry from each full adder is connected to the carry input of the next higher order full adder and so on. For a four bit number, four full adders are needed to give an output of Sum(S<sub>3</sub>S<sub>2</sub>S<sub>1</sub>S<sub>0</sub>)and Carry-out(C<sub>4</sub>)

