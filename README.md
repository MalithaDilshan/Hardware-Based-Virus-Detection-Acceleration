# Hardware-based-virus-detection-acceleration
Malitha Dilshan, Rangana De Silva, Iranga Naverathne

In this project repository has two main files folder as
1.'iverilog_files'
2.'Altera_Quartus_files'

In the folder "iverilog files" there are two folders that named as, 

1. 'base_processor' 
2. 'new_verilog_processor'

In the 'base_processor folder there are some Verilog files (. v files) and test folder that has the make 
file. You can run the base processor using the 'make' command (on Linux).
In the 'new_verilog_processor' folder consists of the new processor that runs using the iverilog commands.
This processor can take three inputs and execute advanced instructions of the hotspots that we 
identified in MD5 algorithm. (refer https://en.wikipedia.org/wiki/MD5 for more infomation about the MD5 hashing 
algotithm)

In the folder "Altera_Quartus_files" there are two folders that named as,

1.new_processor
2.old_processor

In the folder 'old_processor’, there are our old processor design files (base processor) that compiled 
on Altera Quartus-2 software. You can check this by opening the 'QPF' design file in Altera Quartus-2 software.
In the folder 'new_processor’, there are our new processor design files that compiled on Altera Quartus-2 
software. This also can be checked using Altera Quartus-2.


**** About the base processor that initially use to develop the new processor design ***
(Please refer the base processor implementation from 'https://github.com/jmahler/mips-cpu' ; Author) 


# DESCRIPTION

An implementation of a MIPS CPU written in Verilog.  This project is in
very early stages and currently only implements the most basic
functionality of a MIPS CPU.

 - 32-bit MIPS processor

 - implemented in Verilog

 - 5 stage pipeline

 - static branch not taken branch predictor

 - branch detection in decode (stage 2)

 - supports stalls to avoid read after write (RAW) and other hazards

 - can forward from memory (stage 4) and write back (stage 5)
   to avoid stalls

Much of the design was inspired by the book "Computer Organization and
Design" by David A. Patterson and John L. Hennessy (4th ed. 2008).

This project also includes a full set of test benches.  These are
invaluable as a quick check to verify that new changes have not
disrupted previously working functionality.

# REQUIREMENTS

This project requires a Verilog simulator, such as [Icarus][iverilog],
the Gcc compiler, and a Gcc MIPS cross compiler.  To check if your
system has the required programs installed run the `check-install.sh`
script.

    $ ./check-install.sh
    Checking for required programs...
      mips-linux-gnu-objcopy
      mips-linux-gnu-as
      iverilog
    Please install the missing programs and retry.

  [iverilog]: http://iverilog.icarus.com

# RUNNING TEST BENCHES

The tests are located in the `verilog/test/` directory.  Everything is
built and run using the `make` command.

    make

There are two parts to each test: the Verilog code, and the assembly
code.  The Verilog code uses a generic CPU test bench (`cpu_tb.v`) from
which a specific test is built using a specific assembled .hex file.
The .hex file is produced by assembling the .asm file using the Gcc MIPS
cross compiler and converting it to ASCII hex suitable for use with
Verilog.  Then the Verilog code, using a simulator such as
[Icarus Verilog][iverilog], can be run to execute the assembly
instructions and produce a dump of its output (.out).  Finally, the
output file (.out) can be diffed against a known good output file
(.check) to see if there are any differences.

For more information about these steps refer the Makefile in `verilog/test/`.




