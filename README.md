# FPGA Hexadecimal Display

## Description:
The objective of this project was to use VHDL to create a useful component and implement it on an FPGA chip. I used Xilinx Vivado software to implement a generic 7-segment output component and used it to provide output for a 4-bit input. I then tested proper functionality of the circuit. The FPGA board's slide switches are used for inputting a 4-bit binary number, and the hexadecimal equivalent outputted on one of the seven segment displays.
 
## Testing:
Once the code had compiled successfully, I tested it by running it on a logic board. The sixteen possible combinations of the four inputs were tested in the following manner. I utilized the binary numbers from 0 to 15. Each number correlated to a possible test case. For example, 0 corresponded to a False position for each switch and 1 corresponded to a value of True for the rightmost switch only. This method allowed me to efficiently cycle through each test case without missing or repeating any.
On my first test, all test cases were incorrect except for the case in which an 8 was correctly displayed. Each switch combination corresponded to a different LED combination as it was supposed to, but the LED combinations did not form numbers and letters but instead formed nonsensical symbols. I realized that I had configured my code under the assumption that the most significant bit of my switch array represented the light marked as “a” in the LED diagram, with “f” in the least significant bit position. In fact, “a” was assigned to the least significant bit. I adjusted my code accordingly.
On my second test, all test cases were correct except for the case in which a 1 was incorrectly displayed as a 3. I realized that I had entered “0000110” instead of “1111001" to represent 1 on the display. I corrected this error.
On my third test, results were satisfactory in all cases. 
