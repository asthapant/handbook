## Registers

Till now we know that Flip Flops are a part of sequential circuits and can be used to store a single bit of binary data (1 or 0).
However, in order to store multiple bits of data, we need multiple flip flops. 

A **Register** is a device which is used to store such information. It is a **group of flip flops** connected in series and used to store multiple bits of data. The N-bit register consists of N number of Flip Flops and thus stores a N-bit number.

There are two types of registers: **parallel** and **serial** registers. They differ in the manner in which the binary data is loaded and retrieved from them. For serial form, one bit is input at a time(SI) and so we even receive a serial output(SO). For parallel form, data is entered individually to all the F/Fs(PI) and received as parallel outputs(PO).

<p align="center">
<image src="https://user-images.githubusercontent.com/58358546/79540291-89517e80-80a5-11ea-9f46-1ea052887b2c.png">
</p>

For a 4-bit register, we thus use 4 Flip-Flops. Since we just want data to be stored without toggling, we will use a D Flip-Flop. A clock is internally connected to all the four F/Fs to govern the operation. So, we are bound to follow the clock.

#### But this poses a problem!

Whatever input we give to the F/Fs gets changed after one time period of the clock. Here, for **negative trigerred** flip flops, value changes on reaching from one falling edge to another. Thus, for the next clock pulse, we will have different combination of bits stored.

Thereby, we use an independently controlled **Load**.

When we want register inputs to remain unchanged (even with clock changes), we can use a load control input. The load input determines whether the next pulse will accept new information or leave the information in the register intact. 

The Load input, when set at logic level 1 (high state), sets the four flip-flop data inputs to the register's four input bits. That is, we load the data into the register. 
When Load is at logic level 0 (low state), the four flip-flops have their outputs fed into their inputs. That is, the value stored doesn't change.

There is also an additional direct reset input named **CLEAR or RESET**. When CLEAR is 0 the flip flop is resetting,independent of clock and D values. It is useful because in digital systems when the power is turned on the state of flip-flops is unknown. Direct input CLEAR can bring all flip-flops to the known starting state prior to the clock operation.

There are two types of Registers namely:
 - **Shift Register**
 - **Storage Register**
 
For simplicity, we will elaborate only Shift Registers. 




  















































