# DM42
Programs for calculators: HP-42s, DM42 or Free42

This repository contains some programs I made in various fields: maths, aviation, etc.

## Programs
Programs are organized by folder named by fields. For each program, there is a folder which contains a binary raw file and a text file showing the instructions of the program. The fext file is decoded with the help of ![Swiwwmicros decoder for DM42](https://technical.swissmicros.com/decoders/dm42/index.php).

### Maths
`norm_vector/NORMVEC` computes the norm of a vector:
- After launching the program, the execution halts in order to get the input.
- Type the value for X component in X register and then select `X` component in the variable menu.
- Repeat previous step for Y and Z components.
- Type `R/S` to complete the course of the program 
- The norm is computed in the X register so you may use it for additional calculations.

`projection_segment/PROJ` projects a segment to X and Y axis and provides their projected length onto these axis:
- After launching the program, the execution halts in order to get the input.
- Type the value for the length of the segment in X register and then select `LENG` component in the variable menu.
- Type the value for the angle between the segment and X axis in X register and then select `ANGL` component in the variable menu.
- Type `R/S` to complete the course of the program 
- The Y projected length is stored in Y register and the X projected length in X register.

### Aviation
`aviation/DR34` computes the weight and balance of an aircraft. It is applicable for an aircraft with 2 rows of seats R1 and R2 and each row can have 1 or 2 seats. The total mass on row 1 is `MR1`, same for row 2 with `MR2`. If the mass on row 2 should not be considered, leave it to 0. The units does not matter as long as they are all consistent.
The  mass of luggages is `MBAG` and it is considered there is only one place for luggages. 
One fuel tank is always considered and an optional fuel tank can be used. For wing tanks you can add their masses as long as they have the same arm.
**Every time you launch the program, variables are set to 0 to avoid considering previous input** in case you run the program several times.
Some parameters are hard coded for Robin DR-300 and DR-400 in order to have less typing and less variables (it is recommended to hard code those suitable for your plane):
- arm for row 1: 0.41 units
- arm for row 2: 1.19 units
- arm for luggages: 1.9 units
- arm for fuel tank 1: 1.12 units
- take-off arm as a percentage of allowed arm stroke (0.359 units), meaning from front limit (0.205 units) to aft limit (0.205 + 0.359 units).
  
How to use the program:
- After launching the program, the execution halts in order to get the input.
- Type the value for empty mass in X register and then select `MV` in the variable menu. Same for empty mass arm `XV`.
- Type the value for the mass on seat row 1 in X register and then select `MR1`. Same for the mass on row 2 `MR2` if applicable.
- Type the value for the mass of luggages in X register and then select `MBAG` if applicable. Same for the mass of fuel tank 1 `MC1`.
- Type the value for mass of fuel tank 2 in X register and then select `MC2` in the variable menu, if appliicable. Same for its mass arm `XC2`.
- Type `R/S` to complete the course of the program 
- The total mass is stored in Y register and in `MD` and the take-off arm as a percentage of arm stroke is stored in X register and `XD`. So `XD` should be between 0 and 100% to be compliant. Note that only the integer part is kept for `XD`. 

