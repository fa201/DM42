# DM42
Programs for calculators: HP-42s, DM42 or Free42

This repository contains some programs I made in various fields: maths, aviation, etc.

## Programs
Programs are organized by folder named by fields. For each program, there is a folder which contains a binary raw file and a text file showing the instructions of the program. The fext file is decoded with the help of ![Swiwwmicros decoder for DM42](https://technical.swissmicros.com/decoders/dm42/index.php).

### Maths
NORMVEC computes the norm of a vector:
- After launching the program, the execution halts in order to get the input.
- Type the value for X component in X register and then select `X` component in the variable menu.
- Repeat previous step for Y and Z components.
- Type `R/S` to complete the course of the program 
- The norm is computed in the X register so you may use it for additional calculations.

