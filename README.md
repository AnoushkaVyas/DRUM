# DRUM: A Dynamic Range Unbiased Multiplier for Approximate Applications

# Code Description

The source code is written in Verilog. 

* leading_one.v: Code for the Leading One Detector. The output of this block is a number with only one 1 showing the location of the leading one. 

* priority_encoder.v: A priority encoder encodes the output of LOD to Log(n) bits used to indicate the position of 1.

* multiplexer.v: The multiplexer responsible for selecting k-2 bits from each of the two operands, starting from most significant 1. 

* barrel_shifter.v: Shifts the results of the multiplications to the right index, therefore, generating the final result.

* approx_multiplication.v: This is top module which calls all the operations. It also contains the multiplier.

* drum.v: This is the topmost module which checks the signed or unsigned nature of the operands. If they are signed the 2's complement is taken.

* drumtb.v: This is the testbench to test the DRUM multiplier.

* error.py: This is the source code for calculating various errors and plotting them.

# Running the Code

* DRUM multiplier:
```
iverilog leading_one.v priority_encoder.v multiplexer.v barrel_shifter.v approx_multiplication.v drum.v drumtb.v
```

```
./a.out
```

To see the gtkwave

```
gtkwave dump.vcd
```

* Error calculations:

```
python3 error.py
```