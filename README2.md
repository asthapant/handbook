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


 
 
 

 
 





















  


 










  















































